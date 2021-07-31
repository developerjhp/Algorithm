# Q.
Simple, given a string of words, return the length of the shortest word(s).

String will never be empty and you do not need to account for different data types.

# A)
```js
function findShort(s){
  let arr = s.split(' ')
  return arr.reduce((a,b) => {
    if(a.length < b.length) {
      return a
      }
    else {
      return b
    }
  }).length
}
```
