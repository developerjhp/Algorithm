# Q.
Description:
Task
You will be given an array of numbers. You have to sort the odd numbers in ascending order while leaving the even numbers at their original positions.

Examples
[7, 1]  =>  [1, 7]
[5, 8, 6, 3, 4]  =>  [3, 8, 6, 5, 4]
[9, 8, 7, 6, 5, 4, 3, 2, 1, 0]  =>  [1, 8, 3, 6, 5, 4, 7, 2, 9, 0]

# A)
```js
function sortArray(array) {
  console.log(array)
  // Return a sorted array.
 let odd = [...array.filter(el => Math.abs(el)%2 ===1).sort((a,b) => a-b)];
  console.log(odd)
  let count = 0;
 for (let i = 0; i < array.length; i++) {
   if (Math.abs(array[i]) % 2 === 1) {
     array[i] = odd[count]
     count++
   }
 }
  return array
}
```
