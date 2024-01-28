Insertion sort is a simple sorting algorithm that builds the final sorted array one element at a time. It is much less efficient on large lists than more advanced algorithms such as quicksort, heapsort, or merge sort. However, it has several advantages, making it suitable for certain situations:

1. **Algorithm Description:**
   - Start with the assumption that the first element in the list is already sorted.
   - Take each subsequent element in the list and insert it into its correct position within the sorted portion of the array.

2. **Sorting Process:**
   - Compare the current element with the elements in the sorted portion of the array.
   - If the current element is smaller, shift the larger elements to the right to make space for the current element.
   - Repeat this process until the correct position for the current element is found within the sorted portion.

3. **Repeat for Each Element:**
   - Continue this process for each element in the unsorted portion of the array until the entire array is sorted.

4. **Example:**
   Consider the list `[5, 2, 4, 6, 1, 3]`:
   - Start with `[5]` (the first element is considered sorted).
   - Insert `2` into its correct position, resulting in `[2, 5]`.
   - Insert `4` into its correct position, resulting in `[2, 4, 5]`.
   - Continue this process until the entire list is sorted: `[1, 2, 3, 4, 5, 6]`.

Here's a simple implementation of insertion sort in Python:

```python
def insertion_sort(arr):
    for i in range(1, len(arr)):
        key = arr[i]
        j = i - 1

        # Move elements of arr[0..i-1] that are greater than key to one position ahead of their current position
        while j >= 0 and key < arr[j]:
            arr[j + 1] = arr[j]
            j -= 1

        arr[j + 1] = key

# Example usage:
my_list = [12, 11, 13, 5, 6]
insertion_sort(my_list)

print("Sorted array:", my_list)
```

Insertion sort has a time complexity of O(n^2) in the worst case, but its simplicity and efficiency for small datasets make it a reasonable choice in certain scenarios.
