# Q.
Write a function that takes an integer as input, and returns the number of bits that are equal to one in the binary representation of that number. You can guarantee that input is non-negative.

Example: The binary representation of 1234 is 10011010010, so the function should return 5 in this case
# A)
```js
var countBits = function(n) {
  // Program Me
  let start = n
  let res = [];
  while (start !== 1) {
    res.unshift(start%2)
    start = parseInt(start/2)
  }
  if (start === 1) {
   res.unshift(start)
  }
  return res.filter(el => el === 1).length
};
```
이렇게 하면 개발자도구에선 잘 뜨는데 테스트환경에선 timed out이 나온다. 

```js
var countBits = function(n) {
  // Program Me
  let start = n
  let res = [];
  for(i=0;i<n;i++) {
    res.unshift(start%2)
    start = parseInt(start/2)
    if(start === 1) {
      break;
    }
  }
  if (start === 1) {
   res.unshift(start)
  }
  return res.filter(el => el === 1).length
};
```
그래서 for문으로 n까지 돌리고 start가 1이나오면 break를 통해서 빠져나오게 만들었더니 통과가 되었다. 

아니면
```js
var countBits = function(n) {
  // Program Me
  return n.toString(2).split('0').join('').length
};
```


간단하게 toString() 메서드로 2진법으로 간단히 바꿀 수 있다. (10진법은 parseInt사용 )
