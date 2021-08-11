# Q.
Welcome. In this kata, you are asked to square every digit of a number and concatenate them.

For example, if we run 9119 through the function, 811181 will come out, because 92 is 81 and 12 is 1.

Note: The function accepts an integer and returns an integer


# A)
```js
function squareDigits(num){
  //may the code be with you
  let arr = num.toString().split('');
  let res = [];
  for (numbers of arr) {
    res.push(numbers**2)
  }
  return +res.join('')
}
```
