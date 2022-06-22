---
title: "selection sort"
date: 2022-02-13T11:48:42-06:00
draft: false
tags:
- algorithms
- sorting
---

{{< youtube id="92BfuxHn2XE">}}

Runtime: O(n^2)

Space: O(1)

Selection sort is an elementary sorting algorithm that works by comparing each element in an array to every subsequent element in the array to find the next minimum value, swapping the minimum value with the current index for each index.

Let's take the following array for example:

`[5, 1, 8, 3, 2, 1]`

Selection sort starts at element 0, which is `5`, setting the minimum index value to the current element's index, `0`. We then compare the next element, index `1`, and find that it's value is smaller than the value at index `0`. We then update the minimum index to `1`. No smaller element values are found in indices `2`, `3`, `4` and so on, so after all elements are evaluated, elements in position `0` and `1` and swapped:

`[1, 5, 8, 3, 2, 1]`

The sequence is repeated for each element in the array, so the next iteration would compare the value at index `1` against index `2`, then `3`, which is lesser than the values at index `1`, so it would then compare index `3` to index `4`, which is lesser than the value at index `3`. Then, it would compare index `4` to index `5`, which is lesser than the value at index `4`. Finally, since no other elements remain for comparison, elements `1` and `5` are swapped:

`[1, 1, 8, 3, 2, 5]`

This continues for the element in index `2`, swapping indexes `2` and `4`:

`[1, 1, 2, 3, 8, 5]`

The next iteration then swaps elements `3` with `3`, leaving the array in the same order. Finally, index `4` and `5` are swapped, leaving no further comparisons to be made, resulting in our sorted array:

`[1, 1, 2, 3, 5, 8]`

## Notes

As you can see in the video, selection sort, due to its runtime, is not optimal for large sets of data. It can be beneficial in partially sorted datasets, however this is an elementary and inefficient sorting algorightm over all.
