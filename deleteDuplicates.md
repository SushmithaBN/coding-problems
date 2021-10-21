---
title: 'Rotate Lists'
tags: [javascript]
order: 2
section: Lists
createdAt: 2021-10-18
---

Welcome back to my weekly Web Basics, a series on essential programming topics every web developer should absolutely know!

```javascript
/**
 * Definition for singly-linked list.
 * function ListNode(val, next) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.next = (next===undefined ? null : next)
 * }
 */
/**
 * @param {ListNode} head
 * @return {ListNode}
 */
var deleteDuplicates = function(head) {
    if(!head) return null
    var current = head
    while(current) {
        if(current.next !== null && current.val == current.next.val) {
            current.next = current.next.next;
        } else {
            current = current.next;
        }
    }
    
    return head;
};
```

## Examples
Input: head = [1,1,2,3,3]
Output: [1,2,3]


![alt text](https://github.com/SushmithaBN/coding-problems/blob/dummy/list2.jpeg)

## Resources

- [MDN Web Docs: join](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join)
