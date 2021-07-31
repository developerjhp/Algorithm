# Q.
An isogram is a word that has no repeating letters, consecutive or non-consecutive. Implement a function that determines whether a string that contains only letters is an isogram. Assume the empty string is an isogram. Ignore letter case.
```
isIsogram("Dermatoglyphics") == true
isIsogram("aba") == false
isIsogram("moOse") == false // -- ignore letter case
```

# A)

```js
function isIsogram(str) {
  // TODO: 여기에 코드를 작성합니다.
  if(str.length === 0) {
    return true;
  }
  str = str.toLowerCase();
  for (i=0;i<str.length;i++) {
    for (j=i+1;j<str.length;j++) {
      if(str[i] === str[j]) {
        return false
      }
    }
  }
  return true
}
```
