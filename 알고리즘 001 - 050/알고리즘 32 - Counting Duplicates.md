# Q. 
Count the number of Duplicates
Write a function that will return the count of distinct case-insensitive alphabetic characters and numeric digits that occur more than once in the input string. The input string can be assumed to contain only alphabets (both uppercase and lowercase) and numeric digits.

Example
"abcde" -> 0 # no characters repeats more than once
"aabbcde" -> 2 # 'a' and 'b'
"aabBcde" -> 2 # 'a' occurs twice and 'b' twice (`b` and `B`)
"indivisibility" -> 1 # 'i' occurs six times
"Indivisibilities" -> 2 # 'i' occurs seven times and 's' occurs twice
"aA11" -> 2 # 'a' and '1'
"ABBA" -> 2 # 'A' and 'B' each occur twice
# A)
```js
function duplicateCount(text){
  //...
  text = text.toLowerCase();
  let obj = {};
  let count = 0;
  for (i=0;i<text.length;i++) {
    let key = text[i];
    key in obj ? obj[key]++ : obj[key] = 1;
  }
  for (let key2 in obj) {
    obj[key2] >= 2 ? count++ : null ;
  }
  return count;
}
```

삼항연산자에서 skip하고싶으면 null을 넣으면 된다.
