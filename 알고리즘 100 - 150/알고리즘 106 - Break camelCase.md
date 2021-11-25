# Q.
Description:
Complete the solution so that the function will break up camel casing, using a space between words.

Example
"camelCasing"  =>  "camel Casing"
"identifier"   =>  "identifier"
""             =>  ""
# A)
```js
// complete the function
function solution(string) {
  let toArr = string.split('')
  for (let i = 0; i < toArr.length; i++) {
    if (toArr[i] === toArr[i].toUpperCase()) {
      toArr.splice(i,1," " +toArr[i])
    }
  }
  return toArr.join('')
}
```
