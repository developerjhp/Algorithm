# Q.
Your goal in this kata is to implement a difference function, which subtracts one list from another and returns the result.

It should remove all values from list a, which are present in list b keeping their order.

arrayDiff([1,2],[1]) == [2]
If a value is present in b, all of its occurrences must be removed from the other:

arrayDiff([1,2,2,2,3],[2]) == [1,3]

# A)
```js
function arrayDiff(a, b) {
  let copyA = [...a]
   for (aEl of a) {
    for (bEl of b) {
      if (aEl === bEl) {
        copyA.splice(copyA.indexOf(aEl),1)
      }
    }
  }
  return copyA
}
```
incldues를 쓰면 간편하게 풀 수 있다
```js
function arrayDiff(a, b) {
  return a.filter( el => !b.includes(el))
}
```
