---
title: "insertion sort"
date: 2022-02-13T11:48:49-06:00
draft: false
---

{{< youtube id="8oJS1BMKE64">}}

Runtime: O(n^2)

Space: O(1)

Insertion sort is an elementary sorting algorithm, that works by starting at an index `1`, with a lookback period of `1`, continually comparing the current index against the previous. If the current index is lesser than the previous index, they are swapped, and we then compare the previous index with it's previous index, swapping them if they are unordered, so that we continue swapping our value's position, until it is greater than the position before it.

If that was confusing, let's look at an example:

`[5, 5, 5, 1]`

In our example, we would start at index `1`. Since the value of index `1` is not lesser than the value at index `0`, we would proceed to index `2` to likewise evalute the preceding index. Since those are also in order, we would finally arrive at index `3`.

Index `3` is less than index `2`, so we would swap those:

`[5, 5, 1, 5]`

Since a swap occured, we now want to iterate backward until either no preceding element exists, or the preceding element is less than our value, so we compare index `2` against index `1` and they are swapped:

`[5, 1, 5, 5]`

We again compare our value, which is now at index `1` against the preceding index, `0`, and find that index `1` is lesser than index `0`, so they are swapped.

`[1, 5, 5, 5]`

We now have no indicies left for comparison to the left, so we look to continue to the right, but likewise have no further elements for comparison, and so we are done.