# Q.
Welcome.

In this kata you are required to, given a string, replace every letter with its position in the alphabet.

If anything in the text isn't a letter, ignore it and don't return it.

"a" = 1, "b" = 2, etc.

Example
alphabetPosition("The sunset sets at twelve o' clock.")
Should return "20 8 5 19 21 14 19 5 20 19 5 20 19 1 20 20 23 5 12 22 5 15 3 12 15 3 11" (as a string)
# A)
```js
function alphabetPosition(text) {
  let res = '';
  // 모든 띄어쓰기 없애기
  // text를 소문자화
  text = text.toLowerCase();
  // charCodeAt에서 a는 1 이니까 96을 빼주면 값이나옴
  for(let i=0;i<text.length;i++) {
    let rep = text[i].charCodeAt() - 96
    if(rep >26 || rep <1) continue
    res += rep + ' '
  }
  res = res.slice(0,-1)
  return res
}
```

# 새로 배운 것

charCodeAt의 반대 메소드가 있었다는 것 
String.fromCharCode(유니코드 숫자들) 

////////////////////////////////////////////////////////////

문자열에서 모든 공백 제거는
str1.replace(/(\s*)/g, "")
자주사용하니까 쓸때마다 찾아보지말고 외우자
