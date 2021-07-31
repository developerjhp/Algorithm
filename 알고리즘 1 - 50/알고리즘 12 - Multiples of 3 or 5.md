# Q.
If we list all the natural numbers below 10 that are multiples of 3 or 5, we get 3, 5, 6 and 9. The sum of these multiples is 23.

Finish the solution so that it returns the sum of all the multiples of 3 or 5 below the number passed in.

Note: If the number is a multiple of both 3 and 5, only count it once. Also, if a number is negative, return 0(for languages that do have them)

# A)
```js
function solution(number){ 
  
  if(number <= 0 ) {
    return 0
  }
  
  let result = 0
  
  for(i=1;i<number;i++) {
    if( i % 15 === 0) {
      result += i
    }
    else if ( i %3 === 0 || i % 5 === 0) {
      result += i
    }
  }
  return result
}
```

엥..왜 이런 문제가 6kyu에....? 
