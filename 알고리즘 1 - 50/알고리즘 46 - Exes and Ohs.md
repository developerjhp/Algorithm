# Q.
Check to see if a string has the same amount of 'x's and 'o's. The method must return a boolean and be case insensitive. The string can contain any char.

Examples input/output:

XO("ooxx") => true
XO("xooxx") => false
XO("ooxXm") => true
XO("zpzpzpp") => true // when no 'x' and 'o' is present should return true
XO("zzoo") => false

# A)
```js
function XO(str) {
  if (str.length === 0) {
    return true
  }
   let a = str.match(/o/gi)
   let b =str.match(/x/gi)
   if(a === null || b === null ){
     return false
   }
  return a.length === b.length
}
```
