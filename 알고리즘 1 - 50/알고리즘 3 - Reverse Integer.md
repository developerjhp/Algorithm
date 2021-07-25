# Q)
Given a signed 32-bit integer x, return x with its digits reversed. If reversing x causes the value to go outside the signed 32-bit integer range [-231, 231 - 1], then return 0.

Assume the environment does not allow you to store 64-bit integers (signed or unsigned).

 

Example 1:

Input: x = 123
Output: 321
Example 2:

Input: x = -123
Output: -321
Example 3:

Input: x = 120
Output: 21
Example 4:

Input: x = 0
Output: 0
 

Constraints:

-231 <= x <= 231 - 1



# A.
```js
var reverse = function(x) {
  let maxnum = Math.pow(2,31)
  let result = String(x).split('').reverse()
  if(x < 0) {
    result.unshift(result.pop())
    let final =  result.join('')
    if( final < -maxnum ) {
      return 0
    }
    else {
      return final
    }
  }
  else {
    let final = result.join('')
    if(final > maxnum-1) {
      return 0
    }
    else {
      return final
    }
  }
    
};
```

Runtime: 64 ms, faster than 99.98% of JavaScript online submissions for Reverse Integer.
Memory Usage: 40.3 MB, less than 50.48% of JavaScript online submissions for Reverse Integer.


생각보다 생각할게 조금은 있었던 문제같다.
