# Q.

Jaden Smith, the son of Will Smith, is the star of films such as The Karate Kid (2010) and After Earth (2013). Jaden is also known for some of his philosophy that he delivers via Twitter. When writing on Twitter, he is known for almost always capitalizing every word. For simplicity, you'll have to capitalize each word, check out how contractions are expected to be in the example below.

Your task is to convert strings to how they would be written by Jaden Smith. The strings are actual quotes from Jaden Smith, but they are not capitalized in the same way he originally typed them.

Example:

Not Jaden-Cased: "How can mirrors be real if our eyes aren't real"
Jaden-Cased:     "How Can Mirrors Be Real If Our Eyes Aren't Real"


# A)

```js
  String.prototype.toJadenCase = function () {
  //...
  let arr = this.split(' ')
  for(i=0;i<arr.length;i++) {
      arr[i] = arr[i][0].toUpperCase() + arr[i].substr(1)
    }      
    str = arr.join(' ')
  return str
  };
```
  split으로 풀기
  
  
  
```js
String.prototype.toJadenCase = function () {
  //...
  return this.split(' ').map( el => el[0].toUpperCase() + el.slice(1)).join(' ')
};
```
map으로 간단하게 풀기
