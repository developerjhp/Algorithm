# Q.
Build Tower
Build Tower by the following given argument:
number of floors (integer and always greater than 0).

Tower block is represented as *

Python: return a list;
JavaScript: returns an Array;
C#: returns a string[];
PHP: returns an array;
C++: returns a vector<string>;
Haskell: returns a [String];
Ruby: returns an Array;
Lua: returns a Table;
Have fun!

for example, a tower of 3 floors looks like below
```js
[
  '  *  ', 
  ' *** ', 
  '*****'
]
```
and a tower of 6 floors looks like below
```js
[
  '     *     ', 
  '    ***    ', 
  '   *****   ', 
  '  *******  ', 
  ' ********* ', 
  '***********'
]
```
# A)
  ```js
  function towerBuilder(nFloors) {
  // build here
  let res = [];
  for (let i = 1; i <= nFloors ; i++) {
    let str = '*'.repeat((2*i)-1)
    let space = ' '.repeat(((2*nFloors)-(2*i))/2)
    res.push(space+str+space)
  }
  return res
}
```
                             
                             
