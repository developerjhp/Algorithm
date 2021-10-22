덕분에 Number()의 최대 자리수와 BigInt의 계산법 까지 알게된 문제
# Q.
Given a non-empty array of decimal digits representing a non-negative integer, increment one to the integer.

The digits are stored such that the most significant digit is at the head of the list, and each element in the array contains a single digit.

You may assume the integer does not contain any leading zero, except the number 0 itself.

 

Example 1:

Input: digits = [1,2,3]
Output: [1,2,4]
Explanation: The array represents the integer 123.
Example 2:

Input: digits = [4,3,2,1]
Output: [4,3,2,2]
Explanation: The array represents the integer 4321.
Example 3:

Input: digits = [0]
Output: [1]
 

Constraints:

1 <= digits.length <= 100
0 <= digits[i] <= 9

# A)
```js
var plusOne = function(digits) {
  let toStr = '';
  for (i=0;i<digits.length;i++) {
    toStr += digits[i].toString();
  }
  return (BigInt(toStr)+1n).toString().split('')
};
```

Runtime: 68 ms, faster than 93.84% of JavaScript online submissions for Plus One.
Memory Usage: 39.2 MB, less than 10.17% of JavaScript online submissions for Plus One.
