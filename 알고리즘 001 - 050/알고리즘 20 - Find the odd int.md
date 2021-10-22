# Q.
Given an array of integers, find the one that appears an odd number of times.

There will always be only one integer that appears an odd number of times.

```
describe('Example tests', function() {
  doTest([20,1,-1,2,-2,3,3,5,5,1,2,4,20,4,-1,-2,5], 5);
  doTest([1,1,2,-2,5,2,4,4,-1,-2,5], -1);
  doTest([20,1,1,2,2,3,3,5,5,4,20,4,5], 5);
  doTest([10], 10);
  doTest([1,1,1,1,1,1,10,1,1,1,1], 10);
  doTest([5,4,3,2,1,5,4,3,2,10,10], 1);
});
```

# A)
```js
function findOdd(A) {
  //happy coding!
  // 배열을 하나씩 검사해서 중복되어 나오는 수를 객체에 담은 후 카운트
  // 카운트 된 수가 홀수일 경우 그 수를 리턴
  const obj = {};
  
  for (let i = 0; i<A.length ; i++) {
    let key = A[i]
    if (key in obj) {
      obj[key]++
    }
    else if (!(key in obj)) {
      obj[key] = 1
    }
  }
  
  for (count in obj) {
    if (obj[count]%2 === 1) {
      return +count
    }
  }
  
  
  return 0;
}
```
