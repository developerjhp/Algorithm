# Q.
Given two binary strings a and b, return their sum as a binary string.

 

Example 1:

Input: a = "11", b = "1"
Output: "100"
Example 2:

Input: a = "1010", b = "1011"
Output: "10101"
 

Constraints:

1 <= a.length, b.length <= 104
a and b consist only of '0' or '1' characters.
Each string does not contain leading zeros except for the zero itself.
# A)
```js
var addBinary = function(a, b) {
  return (BigInt(`0b${a}`) + BigInt(`0b${b}`)).toString(2)
};
```

Runtime: 72 ms, faster than 97.11% of JavaScript online submissions for Add Binary.
Memory Usage: 40.2 MB, less than 75.26% of JavaScript online submissions for Add Binary.



https://developer.mozilla.org/ko/docs/Web/JavaScript/Guide/Numbers_and_dates

오 이런 기능이 있었다니.. 2진수로 나타내고 싶으면 0b 를 붙이면된다!!
