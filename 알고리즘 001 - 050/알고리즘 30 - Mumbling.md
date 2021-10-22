# Q.
This time no story, no theory. The examples below show you how to write function accum:

Examples:

accum("abcd") -> "A-Bb-Ccc-Dddd"
accum("RqaEzty") -> "R-Qq-Aaa-Eeee-Zzzzz-Tttttt-Yyyyyyy"
accum("cwAt") -> "C-Ww-Aaa-Tttt"
The parameter of accum is a string which includes only letters from a..z and A..Z.
# A)
```js
function accum(s) {
	// your code
  let res = '';
  for (i=0;i<s.length;i++) {
    res += s[i].toUpperCase();
    for(j=1;j<=i;j++) {
      res += s[i].toLowerCase();
    }
    i !== s.length-1 ? res += '-' : res = res
  }
  return res
}
```
