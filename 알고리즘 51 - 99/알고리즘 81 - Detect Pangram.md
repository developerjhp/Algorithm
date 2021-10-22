# Q.
Description:
A pangram is a sentence that contains every single letter of the alphabet at least once. For example, the sentence "The quick brown fox jumps over the lazy dog" is a pangram, because it uses the letters A-Z at least once (case is irrelevant).

Given a string, detect whether or not it is a pangram. Return True if it is, False if not. Ignore numbers and punctuation.
# A)
```js
function isPangram(string){
  //...
  let str = string.toLowerCase().replace(/[^a-z]/g,'')
  const toArr = [...new Set(str)]
  return toArr.length === 26 ? true : false
}
```

1. string을 소문자로 만든다
2. regex를 이용하여 a-z가 아닌 수는 제외한다.
3. new Set을 이용하여 중복문자를 거른다.
4. 알파벳수는 26개니까 26개인지 확인하고 T/F 반환.

