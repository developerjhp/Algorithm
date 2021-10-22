# Q.
Description:
Write a function that takes a string of braces, and determines if the order of the braces is valid. It should return true if the string is valid, and false if it's invalid.

This Kata is similar to the Valid Parentheses Kata, but introduces new characters: brackets [], and curly braces {}. Thanks to @arnedag for the idea!

All input strings will be nonempty, and will only consist of parentheses, brackets and curly braces: ()[]{}.

What is considered Valid?
A string of braces is considered valid if all braces are matched with the correct brace.

Examples
"(){}[]"   =>  True
"([{}])"   =>  True
"(}"       =>  False
"[(])"     =>  False
"[({})](]" =>  False
# A)
```js
function validBraces(braces){
  //TODO 
  let braket = {
    '(' : ')',
    '[' : ']',
    '{' : '}'
  }
  
  let storage = []
 
  for (let i = 0; i < braces.length; i++) {
    if (braces[i] in braket) storage.push(braces[i])
    else {
      if (braket[storage.pop()] !== braces[i]) {
        return false
      }
    }
  }
  return storage.length === 0;
}
```

저번에 leetcode에서 풀었던 것 같은데 codewars에도 있네
핵심은 짝을 비교할 수 있는 객체를 생성하는 것
