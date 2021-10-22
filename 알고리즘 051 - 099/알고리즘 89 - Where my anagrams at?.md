# Q.
Description:
What is an anagram? Well, two words are anagrams of each other if they both contain the same letters. For example:

'abba' & 'baab' == true

'abba' & 'bbaa' == true

'abba' & 'abbba' == false

'abba' & 'abca' == false
Write a function that will find all the anagrams of a word from a list. You will be given two inputs a word and an array with words. You should return an array of all the anagrams or an empty array if there are none. For example:

anagrams('abba', ['aabb', 'abcd', 'bbaa', 'dada']) => ['aabb', 'bbaa']

anagrams('racer', ['crazer', 'carer', 'racar', 'caers', 'racer']) => ['carer', 'racer']

anagrams('laser', ['lazing', 'lazy',  'lacer']) => []
Note for Go
For Go: Empty string slice is expected when there are no anagrams found.

# A)
```js
function anagrams(word, words) {
  word = word.split('').sort()
  let res = [];
  let controll = [];
  let comp = [];
  for (let i = 0; i < words.length; i++) {
    comp = words[i].split('').sort()
    if (comp.length > word.length) continue
    controll = []
    for (let j = 0; j < words[i].length; j++) {
      if (word[j] === comp[j]) controll.push(j)
    }
    if(word.length === controll.length) res.push(words[i])
  }
  return res
}
```

아래와 같이 최적화 했다. 

```js
function anagrams(word, words) {
  let res = [];
  word = word.split('').sort().join('')
  let words2 = words.map(el => el.split('').sort().join(''))
  for (let i = 0; i < words.length; i++) {
    if(word === words2[i]) res.push(words[i])
  }
  return res
}
```

그리고 다시 풀어서 최종적으로 최적화 하였다. filter안에서 el을 수정하지 않으니까 사용가능한 것 같다.
```js
function anagrams(word, words) {
  let res = [];
  word = word.split('').sort().join('')
  return words.filter(el => word === el.split('').sort().join(''))
}
```
