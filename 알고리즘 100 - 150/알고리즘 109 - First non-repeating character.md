# Q)
Write a function named first_non_repeating_letter that takes a string input, and returns the first character that is not repeated anywhere in the string.

For example, if given the input 'stress', the function should return 't', since the letter t only occurs once in the string, and occurs first in the string.

As an added challenge, upper- and lowercase letters are considered the same character, but the function should return the correct case for the initial letter. For example, the input 'sTreSS' should return 'T'.

If a string contains all repeating characters, it should return an empty string ("") or None -- see sample tests.
# A.
```js
function firstNonRepeatingLetter(s) {
  // Add your code here
  let res = []
  for (let i = 0; i < s.length; i++) {
    for (let j = i+1; j < s.length; j++) {
      if (s[i].toLowerCase() === s[j].toLowerCase()) res.push(s[i])
    }
  }
  let notInclude = [];
  return s.split('').filter( el => !(res.includes(el)))[0] === undefined ? '' : s.split('').filter( el => !(res.includes(el) ))[0]
}
```


그냥 indexOf랑 lastIndexOf 랑 같으거 리턴하면 되는데 왜 이렇게 풀었는지 모르겠다. 
