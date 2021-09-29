# Q.
Write an algorithm that takes an array and moves all of the zeros to the end, preserving the order of the other elements.

moveZeros([false,1,0,1,2,0,1,3,"a"]) // returns[false,1,1,2,1,3,"a",0,0]
# A)
```js
var moveZeros = function (arr) {
  let front = [];
  let rear = [];
  arr.forEach(el => el === 0 ? rear.push(el) : front.push(el))
  return [...front,...rear]
}
```

자료구조 Queue에 대해서 안배웠다면   0을 발견할때마다 newArr = 0인덱스 전 + 0인덱스 후 슬라이스한걸 넣은 후 0의 개수 만큼 newArr에 push했을 것 같다. Queue짱짱맨 
