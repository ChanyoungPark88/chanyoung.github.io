---
layout: single
title: "Blind75 - Valid Parentheses / Balanced Brackets"
categories: CodingInterview
tag: [Python, Algorithm, Coding, Blind75]
toc: true
toc_sticky: true
toc_label: Syllabus
author_profile: false
---

## Question

Given a string s containing just the characters `'(', ')', '{', '}', '[' and ']'`, determine if the input string is valid.

An input string is valid if:

- Open brackets must be closed by the same type of brackets.
- Open brackets must be closed in the correct order.
- Every close bracket has a corresponding open bracket of the same type.

<**Example 1**>

```
Input: s = "()"
Output: true
```

<**Example 2**>

```
Input: s = "()[]{}"
Output: true
```

<**Example 3**>

```
Input: s = "(]"
Output: false
```

<**Constraints**>

- 1 <= s.length <= 104
- s consists of parentheses only '()[]{}'.

## Solution

```python
def isValid(s):
    closing = {')':'(', '}':'{', ']':'['}
    stack = []
    # Iterate parameter variation
    for bracket in s:
        if bracket not in closing:
            stack.append(bracket)
        else:
            if not stack or closing[bracket] != stack[-1]:
                return False
            else:
                stack.pop()
    return len(stack) == 0
```

## Time/Space Complexity

- Time Complexity: O(n)
- Space Complexity: O(n)
