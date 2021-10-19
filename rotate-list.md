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
 * @param {number} k
 * @return {ListNode}
 */
var rotateRight = function(head, k) {
  if (head === null || head.next === null || k === 0) return head;
  let length = 0;
    var curr = head
    var n=1;
    while(curr.next !== null){
        curr = curr.next;
        n++
    }
    curr.next = head 
    
    var new_tail = head
    for(var i = 0; i< n - k % n - 1; i++){
        new_tail = new_tail.next
    }
    var new_head = new_tail.next
    new_tail.next = null
    return new_head
}
```

## Examples

![alt text](https://github.com/SushmithaBN/coding-problems/blob/dummy/list.png)

## Resources

- [MDN Web Docs: join](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join)
