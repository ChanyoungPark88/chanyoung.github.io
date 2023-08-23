---
layout: single
title: "Blind75 - Reverse Linked List"
categories: CodingInterview
tag: [Python, Algorithm, Coding, Blind75]
toc: true
toc_sticky: true
toc_label: Syllabus
author_profile: false
---

## Question

Given the `head` of a singly linked list, reversed the list, and return _the reversed list_

<**Example 1**>

```
Input:  head = [1, 2, 3, 4, 5]
Output: [5, 4, 3, 2, 1]
```

<**Example 2**>

```
Input:  head = [1, 2]
Output: [2, 1]
```

<**Example 3**>

```
Input:  head = []
Output: []
```

<**Constraints**>

- The number of nodes in the list is the range `[0, 5000]`.
- `-5000 <= Node.val <= 5000`

## Solution

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def reverseList(self, head: Optional[ListNode]) -> Optional[ListNode]:
        prev, curr = None, head

        while curr:
            next_curr = curr.next
            curr.next = prev
            prev = curr
            curr = next_curr
        return prev

```

## Time/Space Complexity

- Time Complexity: O(n)
- Space Complexity: O(1)
