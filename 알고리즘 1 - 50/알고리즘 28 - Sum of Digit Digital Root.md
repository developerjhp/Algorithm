# Q.
[Digital root](https://en.wikipedia.org/wiki/Digital_root) is the recursive sum of all the digits in a number.

Given n, take the sum of the digits of n. If that value has more than one digit, continue reducing in this way until a single-digit number is produced. The input will be a non-negative integer.

Examples
    16  -->  1 + 6 = 7
   942  -->  9 + 4 + 2 = 15  -->  1 + 5 = 6
132189  -->  1 + 3 + 2 + 1 + 8 + 9 = 24  -->  2 + 4 = 6
493193  -->  4 + 9 + 3 + 1 + 9 + 3 = 29  -->  2 + 9 = 11  -->  1 + 1 = 2
# A)
```js
function digital_root(n) {
  // ...
  let result = n.toString().split('')
  result = result.reduce((a,b) => (+a)+(b))
  while(result.toString().length>1) {
    result = result.toString().split('').reduce((a,b) => (+a)+(+b))
  }
 return +result
 }
```


생각하기 좋은 문제인 것 같다 
