# Q.
Given a non-negative integer x, compute and return the square root of x.

Since the return type is an integer, the decimal digits are truncated, and only the integer part of the result is returned.

Note: You are not allowed to use any built-in exponent function or operator, such as pow(x, 0.5) or x ** 0.5.

 

Example 1:

Input: x = 4
Output: 2
Example 2:

Input: x = 8
Output: 2
Explanation: The square root of 8 is 2.82842..., and since the decimal part is truncated, 2 is returned.
 

Constraints:

0 <= x <= 231 - 1
# A)
```js
var mySqrt = function(x) {
  for ( i=0 ; i<=x ; i++ ) {
    if( x >= i*i && x < (i+1)*(i+1)){
      return i
    }
  }
};
```
Runtime: 172 ms, faster than 8.01% of JavaScript online submissions for Sqrt(x).
Memory Usage: 40.4 MB, less than 32.86% of JavaScript online submissions for Sqrt(x).

내가 풀었던 문제중에 런타임이 가장 낮게나온 문제
