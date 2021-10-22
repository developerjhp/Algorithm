# Q.
Enough is enough!
Alice and Bob were on a holiday. Both of them took many pictures of the places they've been, and now they want to show Charlie their entire collection. However, Charlie doesn't like these sessions, since the motive usually repeats. He isn't fond of seeing the Eiffel tower 40 times. He tells them that he will only sit during the session if they show the same motive at most N times. Luckily, Alice and Bob are able to encode the motive as a number. Can you help them to remove numbers such that their list contains each number only up to N times, without changing the order?

Task
Given a list lst and a number N, create a new list that contains each number of lst at most N times without reordering. For example if N = 2, and the input is [1,2,3,1,2,1,2,3], you take [1,2,3,1,2], drop the next [1,2] since this would lead to 1 and 2 being in the result 3 times, and then take 3, which leads to [1,2,3,1,2,3].

Example
  deleteNth ([1,1,1,1],2) // return [1,1]
  
  deleteNth ([20,37,20,21],1) // return [20,37,21]
# A)
```js
function deleteNth(arr,n){
  // ...
  const obj = {};
  const res = [];
  for (let el of arr) {
    if(!(el in obj)) {
      obj[el] = 1;
      res.push(el)
    }
    else {
      obj[el]++
      obj[el] > n ? null : res.push(el)
    }
  }
  return res
}

```

아래 코드를 보면 생각할게 많아진다. 내가 저렇게 길게 쓴 코드를 아래처럼 짧게 쓸 수 있다.

```js
function deleteNth(arr,x) {
  var cache = {};
  return arr.filter(function(n) {
    cache[n] = (cache[n]||0) + 1;
    return cache[n] <= x;
  });
}
```
cache[n] = (cache[n]||0) +1 은 cache[n]이 undefined면 0으로 만들고 1을 더한다는 소리다. 
그러고 나서 n이 한번 더 나오면 cache[n] = cache[n] +1 이 된다. 
이 과정을 다 돌고나서 cache[n] <= x 인 친구들만 filter를 통해 보내주게 된다. 신박한 코드다
