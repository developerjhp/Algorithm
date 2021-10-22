# Q.
Write a function that takes in a string of one or more words, and returns the same string, but with all five or more letter words reversed (like the name of this kata).

Strings passed in will consist of only letters and spaces.
Spaces will be included only when more than one word is present.
Examples:

spinWords("Hey fellow warriors") => "Hey wollef sroirraw" 
spinWords("This is a test") => "This is a test" 
spinWords("This is another test") => "This is rehtona test"
# A)
```js
function spinWords(string){
  //TODO Have fun :)
  let arr = string.split(' ');
  let result = [];
  for (let key of arr) {
    if (key.length >= 5) {
      result.push(key.split('').reverse().join(''));
    }
    else {
      result.push(key);
    }
  }
  return result.join(' ');
}
```
