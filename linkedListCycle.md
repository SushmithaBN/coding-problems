---
title: 'Check if linked list has cycle'
tags: [javascript]
order: 5
section: Lists
createdAt: 2021-10-20
---

Welcome back to my weekly Web Basics, a series on essential programming topics every web developer should absolutely know!

Using 2 pointer method
```javascript

/**
 * Definition for singly-linked list.
 * function ListNode(val) {
 *     this.val = val;
 *     this.next = null;
 * }
 */

/**
 * @param {ListNode} head
 * @return {boolean}
 */
var hasCycle = function(head) {
    if (head === null)
        return false
    let slow = head;
    let fast = head;
    while(fast !== null && fast.next !== null){
        slow = slow.next;
        fast = fast.next.next;
        if(slow === fast){
            return true
        }
    }
    return false
}
```
Using HashMap
```javascript

/**
 * Definition for singly-linked list.
 * function ListNode(val) {
 *     this.val = val;
 *     this.next = null;
 * }
 */

/**
 * @param {ListNode} head
 * @return {boolean}
 */
var hasCycle = function(head) {
    let map = {}
    let curr = head;
    let count = 0;
    while(curr !== null){
      if(Object.values(map).includes(curr)){
        return true;
      }
      map[count] = curr
      curr = curr.next
      count++;
    }
    return false
}
```

## Examples

Input: head = [3,2,0,-4], pos = 1
Output: true

Explanation: There is a cycle in the linked list, where the tail connects to the 1st node (0-indexed).

Input: head = [1,2], pos = 0
Output: true

Explanation: There is a cycle in the linked list, where the tail connects to the 0th node.


Input: head = [1], pos = -1
Output: false

Explanation: There is no cycle in the linked list.
