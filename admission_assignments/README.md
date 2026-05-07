
# Debugging Assignment

This repository contains short explanations for each debugging exercise.  
For each exercise, I answered two questions:

1. What is going wrong?
2. How could this be fixed?

---

## Exercise 1: Fruit ID Lookup

### 1. What is going wrong?

The function tries to return a fruit by index, but the fruits are stored in a Python `set`.

A `set` does not preserve order, so its elements do not have fixed indices. This means that the result can be unpredictable. For example, index `1` is not guaranteed to return `"orange"`.

The issue is not only in the loop itself, but in the choice of data structure.

```python
for fruit in fruits:
    if fruit_id == idx:
        return fruit
```

This logic is unreliable when `fruits` is a set.

### 2. How could this be fixed?

Use an ordered data structure such as a `list` instead of a `set`.

```python
def id_to_fruit(fruit_id: int, fruits: list[str]) -> str:
    return fruits[fruit_id]
```

Example:

```python
fruits = ["apple", "orange", "melon", "kiwi", "strawberry"]

name1 = id_to_fruit(1, fruits)
name3 = id_to_fruit(3, fruits)
name4 = id_to_fruit(4, fruits)
```

This works because lists preserve order and support direct indexing.

---

## Exercise 2: Swapping Bounding Box Coordinates

### 1. What is going wrong?

The function is supposed to swap the x and y coordinates of bounding boxes.

The input format is:

```python
[x1, y1, x2, y2, class_id]
```

The expected output format is:

```python
[y1, x1, y2, x2, class_id]
```

The original code contains an incorrect assignment:

```python
coords[:, 0], coords[:, 1], coords[:, 2], coords[:, 3] = coords[:, 1], coords[:, 1], coords[:, 3], coords[:, 2]
```

The problem is that `coords[:, 1]` is used twice:

```python
coords[:, 1], coords[:, 1]
```

So the original `x1` values are lost instead of being swapped with `y1`.

Another issue is that the function modifies the original input array directly, which can cause unwanted side effects.

### 2. How could this be fixed?

Create a copy of the input array and assign the swapped values using the original array.

```python
def swap(coords: np.ndarray) -> np.ndarray:
    swapped = coords.copy()

    swapped[:, 0] = coords[:, 1]
    swapped[:, 1] = coords[:, 0]
    swapped[:, 2] = coords[:, 3]
    swapped[:, 3] = coords[:, 2]

    return swapped
```

This keeps the original array unchanged and correctly swaps the coordinate columns.

---

## Exercise 3: Plotting Precision-Recall Data

### 1. What is going wrong?

The function is supposed to plot precision on the x-axis and recall on the y-axis.

The CSV file contains:

```text
precision, recall
```

However, there are two problems.

First, values read from a CSV file are strings by default. For example:

```python
"0.013"
```

is read as text, not as a numeric value.

Second, the original code plots the columns in the wrong order:

```python
plt.plot(results[:, 1], results[:, 0])
```

This puts recall on the x-axis and precision on the y-axis, which is the opposite of what the function description says.

There may also be empty rows in the CSV file, especially on Windows if the file is not written with `newline=""`.

### 2. How could this be fixed?

Convert the CSV values to floats and plot the correct columns.

```python
results = np.array(results, dtype=float)

precision = results[:, 0]
recall = results[:, 1]

plt.plot(precision, recall)
plt.xlabel("Precision")
plt.ylabel("Recall")
```

When writing the CSV file, use:

```python
open("data_file.csv", "w", newline="")
```

When reading the CSV file, empty rows can also be skipped:

```python
for row in csv_reader:
    if row:
        results.append(row)
```

This makes sure the data has the correct type and shape before plotting.

---

## Exercise 4: GAN Training Batch Size Bug

### 1. What is going wrong?

The GAN training code assumes that every batch from the PyTorch `DataLoader` has exactly the same size as the selected `batch_size`.

The original code creates tensors using the fixed `batch_size` value:

```python
real_samples_labels = torch.ones((batch_size, 1)).to(device=device)
generated_samples_labels = torch.zeros((batch_size, 1)).to(device=device)
latent_space_samples = torch.randn((batch_size, 100)).to(device=device)
```

This can fail because the last batch in a dataset may be smaller than the requested batch size.

For example, if `batch_size=64`, the final batch may contain fewer than 64 real images. Then the number of samples, generated images, labels, and discriminator outputs may not match.

This causes a shape mismatch error during loss calculation.


There is also a typo in the documentation: `Generater` should be `Generator`.

### 2. How could this be fixed?

Use the actual size of the current batch instead of the fixed `batch_size` value.

```python
current_batch_size = real_samples.size(0)
```

Then create labels and latent vectors using `current_batch_size`.

```python
real_samples_labels = torch.ones((current_batch_size, 1)).to(device=device)
generated_samples_labels = torch.zeros((current_batch_size, 1)).to(device=device)
latent_space_samples = torch.randn((current_batch_size, 100)).to(device=device)
```

This ensures that the labels and model outputs have matching shapes, even when the final batch is smaller.


