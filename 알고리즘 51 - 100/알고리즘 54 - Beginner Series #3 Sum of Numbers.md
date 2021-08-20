# Q.
Given two integers a and b, which can be positive or negative, find the sum of all the integers between and including them and return it. If the two numbers are equal return a or b.

Note: a and b are not ordered!

Examples
GetSum(1, 0) == 1   // 1 + 0 = 1
GetSum(1, 2) == 3   // 1 + 2 = 3
GetSum(0, 1) == 1   // 0 + 1 = 1
GetSum(1, 1) == 1   // 1 Since both are same
GetSum(-1, 0) == -1 // -1 + 0 = -1
GetSum(-1, 2) == 2  // -1 + 0 + 1 + 2 = 2
# A)
```js
function getSum( a,b )
{ 
  if(a===b) return a
  let max
  let min
  if (a >b) {
     max = a
     min = b
  }
  else {
     max = b
     min = a
  }
 
  let res = max+min
  let i = 1;
  while( min+i < max) {
    res += min+i
    i++
  }
  return res
}
```
