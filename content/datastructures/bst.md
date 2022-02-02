---
title: "Binary Search Tree"
date: 2022-01-31T20:45:33-06:00
draft: false
---


Alvin's [Binary Tree Algorithms for Technical Interviews](https://www.youtube.com/watch?v=fAAZixBzIAI) is a great resource for learning about trees, specifically binary trees, or `binary search trees` (BSTs), which are used somewhat commonly in interviews, but have other applications such as searching or sorting.

It can be helpful to think of the recursive call stack in something like [`mergesort`](../algorithms/mergesort.md)

{{<youtube id="fAAZixBzIAI">}}

A binary search is comprised of nodes, sometimes refered to as `leaf`s when they have no child nodes attached to them. By convention, `binary` search trees can have at max 2 children.

```
     1
    / \
   2   3
    \   \
     5   4
```

An implementation of a binary search tree might look like:

```golang
type Node struct {
  value int
  left *Node
  right *Node
}
```

The above example might be codified as:

```golang
tree := &Node{
  val: 1,
  left: &Node{
    val: 2,
    right: &Node: {
      val: 5,
    }
  },
  right: &Node{
    val: 3,
    right: &Node{
      val: 4,
    }
  }
}
```

A binary search tree can be iterated through in 2 important traversal methods:
- Deep first search
- Breadth first search

## Depth first traversal

Depth first traversal can be done either iteratively or recursively.

### Iterative

```golang

```

## Breadth first search

To search a tree breadth first, you must visit all child nodes of equal iterations from the root node, before continuing deeper in the tree.

To do this, we enlist the help of a `queue`: `[]`. In a `queue`, things enter the back of the queue, and the front of the queue gets iterated from.

Consider a queue at a food truck, the following queue represents the order that the guests arrived to the line:

`[1, 2, 3, 4, 5, 6, 7, 8]`

As we iterate through our tree, we can track visited elements, or iterate until we find our search term.

```golang
package main

import (
  "fmt"
)

type Node struct {
  val int
  left *Node
  right *Node
}

// Runtime: O(n)
// Space: O(n)
func BFS(node *Node) []int {
  queue := []*Node{node}
  var current *Node
  visited := []int{}

  for len(queue) > 0 {
    current = queue[0]
    visited = append(visited, current.val)

    queue = queue[1:]

    if current.left != nil {
      queue = append(queue, current.left)
    }

    if current.right != nil {
      queue = append(queue, current.right)
    }
  }

  return visited
}

func main() {
  tree := &Node{
    val: 1,
    left: &Node{
      val: 2,
      left: &Node{
        val: 4,
      },
      right: &Node{
        val: 5,
      },
    },
    right: &Node{
      val: 3,
      left: &Node{
        val: 6,
        left: &Node{
          val: 8,
        },
        right: &Node{
          val: 9,
        },
      },
      right: &Node{
        val: 7,
        right: &Node{
          val: 10,
          right: &Node{
            val: 11,
          },
        },
      },
    },
  }

  fmt.Println("visited: %v", BFS(tree))
}
```
