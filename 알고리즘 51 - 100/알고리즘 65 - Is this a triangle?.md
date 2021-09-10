# Q.
Description:
Implement a method that accepts 3 integer values a, b, c. The method should return true if a triangle can be built with the sides of given length and false in any other case.

(In this case, all triangles must have surface greater than 0 to be accepted).
# A)
```js
function isTriangle(a,b,c)
{ 
  let [max,...rest] = [a,b,c].sort((a,b) => b-a);
  return max < rest.reduce((a,b) => a+b) ? true : false
}
```

근데 굳이 이렇게 풀었어야 했을까? 요즘들어 쉽게 풀 수 있는 문제도 무조건 어렵게 풀려고 하는 것 같다. 
