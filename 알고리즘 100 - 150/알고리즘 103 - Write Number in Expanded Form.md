# Q.
Write Number in Expanded Form
You will be given a number and you will need to return it as a string in Expanded Form. For example:

expandedForm(12); // Should return '10 + 2'
expandedForm(42); // Should return '40 + 2'
expandedForm(70304); // Should return '70000 + 300 + 4'
NOTE: All numbers will be whole numbers greater than 0.


# A)
```js
function expandedForm(num) {
  // Your code here
  let toStr = num.toString()
  let res = '';
  for (let i = 0; i < toStr.length; i++) {
    if (toStr[i] !== '0') {
      res += +toStr[i] * 10**(toStr.length-(i+1)) + ' + '
    }
  }
  return res.slice(0,-3)
}
```
