# Q.
Description:
Your task is to sort a given string. Each word in the string will contain a single number. This number is the position the word should have in the result.

Note: Numbers can be from 1 to 9. So 1 will be the first word (not 0).

If the input string is empty, return an empty string. The words in the input String will only contain valid consecutive numbers.

Examples
"is2 Thi1s T4est 3a"  -->  "Thi1s is2 3a T4est"
"4of Fo1r pe6ople g3ood th5e the2"  -->  "Fo1r the2 g3ood 4of th5e pe6ople"
""  -->  ""
# A)
```js
// function order(words){
//   // ...
//   let toArr = words.split(' ')
//   let res = [];
//   while(res.length <= word.length) {
//     for(let i = 0; i < toArr.length ; i++) {
//       for(let j = 0; j <toArr[i].length; j++) {
//         if (toArr[i][j] === (res.length+1).toString()) res.push(toArr[i])
//       }
//     }
//     }
// return res.join(' ')

// }

function order(words){
  // ...
  // 글자에서 숫자 뽑아내서 배열애 넣고 그 배열안의 el대소에 따라서 클론된 toArr를 순서대로 붙임
  let toArr = words.split(' ')
  let resClone = [];
  let res = [];
   for(let i = 0; i < toArr.length ; i++) {
      for(let j = 0; j <toArr[i].length; j++) {
        if (!isNaN(toArr[i][j])) resClone.push(toArr[i][j])
      }
    }
  let idx = 1;
  for(let k=0 ; k<resClone.length; k++) {
    for(let j = 0 ; j <resClone.length; j++) {
    if(+resClone[j] === idx) {
      res.push(toArr[j])
      idx++
    }
  }
 }
return res.join(' ')

}
```
너무 복잡하게 풀었다.toArr의 el중 숫자를 포함하면 res에 넣으려고 했는데 ij를 잘못줘서 this1만 나오고 종료되었다. ij위치만 바꿔주면 풀리는 문제였는데 그걸 생각못하고 더 복잡하게 풀게 되었다. 하다가 안되면 반대로도 생각해보는 자세가 필요할 것 같다.  확실히 6kyu부터는 생각을 조금은 요하는 것 같다. 
