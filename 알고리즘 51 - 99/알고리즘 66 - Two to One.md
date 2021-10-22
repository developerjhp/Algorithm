# Q.
Take 2 strings s1 and s2 including only letters from ato z. Return a new sorted string, the longest possible, containing distinct letters - each taken only once - coming from s1 or s2.

Examples:
a = "xyaabbbccccdefww"
b = "xxxxyyyyabklmopq"
longest(a, b) -> "abcdefklmopqwxy"

a = "abcdefghijklmnopqrstuvwxyz"
longest(a, a) -> "abcdefghijklmnopqrstuvwxyz"
# A)
```js
function longest(s1, s2) {
  // your code
  let sumStr = s1 + s2;
  let res = new Set([...sumStr])
  return  [...res].sort().join('')  
}
```
⬇️
```js
function longest(s1, s2) {
  // your code
  return [...new Set(s1+s2)].sort().join('')
}
```


new Set으로 중복을 제거하고 스프레드연산자로 set객체를 합치면 된다.

# 새로 알게된 것
str,arr의 중복문자 제거는 new Set(array)을 사용하면 좋다. 다만 결과값이 set객체로 나온다는 것을 꼭 인지해야된다. 
Set객체를 배열로 변환하기 
https://hianna.tistory.com/421
