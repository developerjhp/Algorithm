제발 그만 까먹자 배열의 '' 을 지 울 땐  **Array.filter(Boolean)** !!!


# Q.
Description:
The marketing team is spending way too much time typing in hashtags.
Let's help them with our own Hashtag Generator!

Here's the deal:

It must start with a hashtag (#).
All words must have their first letter capitalized.
If the final result is longer than 140 chars it must return false.
If the input or the result is an empty string it must return false.
Examples
" Hello there thanks for trying my Kata"  =>  "#HelloThereThanksForTryingMyKata"
"    Hello     World   "                  =>  "#HelloWorld"
""                                        =>  false
# A)
```js
function generateHashtag (str) {
  str = str.trim()
  if (str.length === 0) return false
  let toArr = str.split(' ')
  toArr = toArr.filter(Boolean)
  toArr = toArr.map(el => {
    el = el.split('')
    el[0] = el[0].toUpperCase()
    return el.join('')
  })
  let res = '#' + toArr.join('') 
  if (res.length === 1) return false
  if (res.length > 140) return false
  return res
}
```

리팩토링 ( 이라 쓰고 글자 수 줄이기 라고 읽는다..)

```js
function generateHashtag (str) {
  let toArr = str.split(' ')
  toArr = toArr.filter(Boolean).map(el => 
  {
    el = el.split('')
    el[0] = el[0].toUpperCase()
    return el.join('')
  })
  let res = '#' + toArr.join('') 
  return res.length === 1 || res.length > 140 ? false : res
}
```
