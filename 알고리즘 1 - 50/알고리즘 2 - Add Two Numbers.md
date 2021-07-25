Q)
You are given two non-empty linked lists representing two non-negative integers. The digits are stored in reverse order, and each of their nodes contains a single digit. Add the two numbers and return the sum as a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.

Example 1:


Input: l1 = [2,4,3], l2 = [5,6,4]
Output: [7,0,8]
Explanation: 342 + 465 = 807.
Example 2:

Input: l1 = [0], l2 = [0]
Output: [0]
Example 3:

Input: l1 = [9,9,9,9,9,9,9], l2 = [9,9,9,9]
Output: [8,9,9,9,0,0,0,1]

Constraints:

The number of nodes in each linked list is in the range [1, 100].
0 <= Node.val <= 9
It is guaranteed that the list represents a number that does not have leading zeros.

A)
var addTwoNumbers = function(l1, l2) {
  
  return ((+l1.reverse().join(''))+(+l2.reverse().join(''))).toString().split('').reverse()
    
};
.reverse is not a function 에러가 떳다. 뭐지.. 사이트오류인가..? 그래서 reverse 메서드를 spread연산자와 map,pop을 통해 풀어봤다.

var addTwoNumbers = function(l1, l2) {
  let reverse=a=>[...a].map(a.pop,a)
  return ((+reverse(l1).join(''))+(+reverse(l2).join(''))).toString().split('').reverse()
    
};
이번엔 아래와 같은 에러가 떳다..


아.. 뭐가 문제인지 곰곰이 생각하다가 문제를 다시 봤더니 노드를 사용하라는거였다... 아직 안배웠기에 패스 ㅠㅠ
