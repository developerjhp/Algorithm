# Q.
Description:
Given the triangle of consecutive odd numbers:
```
             1
          3     5
       7     9    11
   13    15    17    19
21    23    25    27    29
```
...
Calculate the sum of the numbers in the nth row of this triangle (starting at index 1) e.g.:

rowSumOddNumbers(1); // 1
rowSumOddNumbers(2); // 3 + 5 = 8
# A)
```js
function rowSumOddNumbers(n) {
	// TODO
  let res = 0;
  let j = 1;
  for (i=0;i<n;i++) {
    res += n*(n-1)+j
    j+=2
  }
  return res
}
```

n**3 하면 결과값이 나온다. 나는 뭘 한걸까 ㅋㅋㅋㅋㅋㅋ
