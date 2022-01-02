# Q.
Description:
Write a program that will calculate the number of trailing zeros in a factorial of a given number.

N! = 1 * 2 * 3 * ... * N

Be careful 1000! has 2568 digits...

For more info, see: http://mathworld.wolfram.com/Factorial.html

Examples
zeros(6) = 1
# 6! = 1 * 2 * 3 * 4 * 5 * 6 = 720 --> 1 trailing zero

zeros(12) = 2
# 12! = 479001600 --> 2 trailing zeros
Hint: You're not meant to calculate the factorial. Find another way to find the number of zeros.
# A)
```js
function zeros (n) {
  
  if (n===0) return 0;
  let count = 0
  for (let i = 5; Math.floor(n/i)>=1; i*=5)
    count += Math.floor(n / i)
  
  return count
}
```
