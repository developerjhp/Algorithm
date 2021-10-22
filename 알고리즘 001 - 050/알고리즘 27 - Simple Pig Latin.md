# Q.
Move the first letter of each word to the end of it, then add "ay" to the end of the word. Leave punctuation marks untouched.

Examples
pigIt('Pig latin is cool'); // igPay atinlay siay oolcay
pigIt('Hello world !');     // elloHay orldway !

# A)
```js
function pigIt(str){
  //Code here
  // 스페이스로 문자열을 나눠서 배열에 담는다
  // 만약 str이 !를 포함하고 있다면 마지막 배열을 지운다
  // 포문으로 배열에서 하나하나 꺼낸 후 ''로 스플릿해주고,
  // 리버스해준 후 join('')+ay를 해준 후 result배열에 push한다.
  // str이 !를 포함했다면 ' !'을 더해주고 아니라면 그대로 리턴한다. 
  
  let resultArr = []
  let arr = str.split(' ');
  if (str.includes('!')) {
    arr.pop;
  }
  for (i=0;i<arr.length;i++) {
    resultArr.push(arr[i].split('').reverse().join('')+'ay')
  }
  if(str.includes('!')) {
    return resultArr.join(' ')+ ' !'
  }
  else {
    return resultArr.join(' ')
  }
}

```

엥..통과가 안된다..!? 다시 문제를 읽어보니 Move the `first letter` of each word to the end of it ㅋㅋㅋ 첫글자만 옮기는거였네..아 ㅋㅋㅋ  날이 갈수록 멍청해지는 것 같다ㅠㅠ
```js
function pigIt(str){
  //Code here
  // ' '으로 구분해서 배열에 담음
  // for문으로 각 배열에서 shift한 것을 push하고 arr을 shift하고 push함
  // ' ' 로 스트링으로 합쳐서 리턴
  let resultArr = [];
  let arr = str.split(' ');
  for (i=0;i<arr.length;i++) {
    let prop = arr[i].split('');
    prop.push(prop.shift());
    resultArr.push(prop.join('')+'ay')
  }
  if( str[str.length-1] === '!' || str[str.length-1] === '?') {
     return resultArr.join(' ').replace(str[str.length-1]+'ay',str[str.length-1])
     }
  return resultArr.join(' ')
}
```

문자열을 수정하라고 하는 경우는 대부분 regex로 풀리니까 다음부턴 regex로 풀기 
