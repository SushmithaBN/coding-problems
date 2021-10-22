---
title: 'Reverse Linked List'
tags: [javascript]
order: 6
section: Lists
createdAt: 2021-10-21
---

Welcome back to my weekly Web Basics, a series on essential programming topics every web developer should absolutely know!

Iterative Approach

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
var reverseList = function(head) {
    var prev = null;
    var curr = head;
    while(curr !== null){
        temp = curr.next;
        curr.next = prev;
        prev = curr;
        curr = temp;
    }
    return prev
};
```

Recursive Approach

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
var reverseList(head) {
    if (head == null || head.next == null) return head;
    let p = reverseList(head.next);
    head.next.next = head;
    head.next = null;
    return p;
}
```



## Examples
Input: head = [1,2,3,4,5]
Output: [5,4,3,2,1]


![alt text](https://github.com/SushmithaBN/coding-problems/blob/dummy/revlist.jpeg)

## Resources

- [MDN Web Docs: join](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join)
