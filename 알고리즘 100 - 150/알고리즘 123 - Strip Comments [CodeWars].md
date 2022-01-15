# Q.
```js
Complete the solution so that it strips all text that follows any of a set of comment markers passed in. Any whitespace at the end of the line should also be stripped out.

Example:

Given an input string of:

apples, pears # and bananas
grapes
bananas !apples
The output expected would be:

apples, pears
grapes
bananas
The code would be called like so:

var result = solution("apples, pears # and bananas\ngrapes\nbananas !apples", ["#", "!"])
// result should == "apples, pears\ngrapes\nbananas"

```

# A)
```js
function solution(input, markers) {
  const myFunction = (input,index) => {
    return input.map((el) => {
      if(el.indexOf(markers[index]) >= 1) {
        return el.slice(0, el.indexOf(markers[index])).trim()
      }
      return el
    })
  }
  
  return myFunction(myFunction(input.split('\n'),0),1).join('\n')
};
```

오랜만에 4kyu문제 풀려니까 좀 오래걸린다. 뇌를 더 굴려야지...!!!!
