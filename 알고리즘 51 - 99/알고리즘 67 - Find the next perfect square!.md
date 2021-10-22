# Q.
Description:
You might know some pretty large perfect squares. But what about the NEXT one?

Complete the findNextSquare method that finds the next integral perfect square after the one passed as a parameter. Recall that an integral perfect square is an integer n such that sqrt(n) is also an integer.

If the parameter is itself not a perfect square then -1 should be returned. You may assume the parameter is non-negative.

Examples:

findNextSquare(121) --> returns 144
findNextSquare(625) --> returns 676
findNextSquare(114) --> returns -1 since 114 is not a perfect square
# A)
```js
function findNextSquare(sq) {
  return Number.isInteger(Math.sqrt(sq)) ? (Math.sqrt(sq)+1)**2 : -1
}
```
# 새로 알게된 것
숫자가 정수인지, 실수인지 체크하는 2가지 방법
+ Number.isInteger()
+ 나머지 연산자(%)
