# Q.
Description:
Write a function that takes a string of parentheses, and determines if the order of the parentheses is valid. The function should return true if the string is valid, and false if it's invalid.

Examples
"()"              =>  true
")(()))"          =>  false
"("               =>  false
"(())((()())())"  =>  true
Constraints
0 <= input.length <= 100
# A)
```js
function validParentheses(parens){
  //TODO 
  let count = 0;
  for (let i = 0; i < parens.length; i++) {
    if (parens[i] === '(') count++
    else count--
    if (count < 0) return false
  }
  return count === 0 ? true : false
}
```

이렇게 쉬운문제가 왜 5kyu에 있지? 하고 풀어봤는데 edge case를 생각하기까지 30분이나 걸렸다. 
