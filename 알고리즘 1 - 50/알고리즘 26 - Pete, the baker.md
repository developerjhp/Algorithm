# Q.
Pete likes to bake some cakes. He has some recipes and ingredients. Unfortunately he is not good in maths. Can you help him to find out, how many cakes he could bake considering his recipes?

Write a function cakes(), which takes the recipe (object) and the available ingredients (also an object) and returns the maximum number of cakes Pete can bake (integer). For simplicity there are no units for the amounts (e.g. 1 lb of flour or 200 g of sugar are simply 1 or 200). Ingredients that are not present in the objects, can be considered as 0.
```
Examples:

// must return 2
cakes({flour: 500, sugar: 200, eggs: 1}, {flour: 1200, sugar: 1200, eggs: 5, milk: 200}); 
// must return 0
cakes({apples: 3, flour: 300, sugar: 150, milk: 100, oil: 100}, {sugar: 500, flour: 2000, milk: 2000}); 
```
# A)

```js
function cakes(recipe, available) {
  // a키 / r키 한 것 을 배열에 담아서 제일 작은 수 리턴
  //r 은 레시피의 key 
  // a 는 어베일러블의 key
  const resultArr = [];
  for (let r in recipe) {
     if( r in available) {
        resultArr.push(Math.floor(available[r] / recipe[r]))
         }
      else {
        return 0
      }
        }
  return Math.min(...resultArr)
}
```

처음엔 
```js
for (let r in recipe) {
  for (let a in available) {
    if ( available[r] >= recipe[r] ) { 
      어쩌구~~
```
로 알고리즘을 짯었는데 생각해보니까 r키를 공유하니까 이중포문을 쓸 이유가 없어서 if key in 을 사용했다. 
       
   
 
