# LeetCode 295 - Find Median from Data Stream

## Problem Statement

Design a data structure that supports:

* Adding an integer to the data structure.
* Finding the median of all numbers added so far.

The median is the middle value when the numbers are sorted.

If there are an even number of values, the median is the average of the two middle values.

## Example

### Input

```text
addNum(1)
addNum(2)
findMedian()
addNum(3)
findMedian()
```

### Output

```text
1.5
2.0
```

## Approach

We use **two heaps**:

* `small` is a max heap containing the smaller half of the numbers.
* `large` is a min heap containing the larger half.

Python provides a min heap, so negative values are used to simulate a max heap for `small`.

We keep both heaps balanced so that their sizes differ by at most one.

## Algorithm

```text
Add the number to the smaller half.

If the largest value in the smaller half
is greater than the smallest value in the larger half:
    Move the value to the correct heap.

Balance the two heaps.

If there are more elements in small:
    Median = top of small

Otherwise:
    Median = average of the two heap tops
```

## Time Complexity

* `addNum()` → `O(log n)`
* `findMedian()` → `O(1)`

## Space Complexity

`O(n)`

## Author

T. Nandhini
