---
title: 'Add 2 numbers using linked list'
tags: [javascript]
order: 4
section: Lists
createdAt: 2021-10-20
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
 * @param {ListNode} l1
 * @param {ListNode} l2
 * @return {ListNode}
 */
var addTwoNumbers = function(l1, l2) {
    var curr1 = l1
    var curr2 = l2
    var carry = 0;
    var sum=0;
    var resHead = new ListNode(0);
    var res = resHead;
    while(curr1 !== null || curr2 !== null || sum>0){
        if(curr1 !== null) {
            sum = sum + curr1.val 
            curr1 = curr1.next
        }
        if(curr2 !== null) {
            sum = sum + curr2.val
            curr2 = curr2.next
        }
        if(sum >= 10){
            sum = sum - 10
            carry = 1
        }
        res.next = new ListNode(sum)
        res = res.next
        sum = carry
        carry =0 
    }
    return resHead.next;
};
```
Example 1
Input: l1 = [2,4,3], l2 = [5,6,4]
Output: [7,0,8]
Explanation: 342 + 465 = 807.


![alt text](https://github.com/SushmithaBN/coding-problems/blob/dummy/addtwonumber1.jpeg)

Example 2
Input: l1 = [0], l2 = [0]
Output: [0]


Example 3
Input: l1 = [9,9,9,9,9,9,9], l2 = [9,9,9,9]
Output: [8,9,9,9,0,0,0,1]

## Resources

- [MDN Web Docs: join](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join)
