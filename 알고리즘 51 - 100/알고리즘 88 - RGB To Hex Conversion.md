# Q.
Description:
The rgb function is incomplete. Complete it so that passing in RGB decimal values will result in a hexadecimal representation being returned. Valid decimal values for RGB are 0 - 255. Any values that fall out of that range must be rounded to the closest valid value.

Note: Your answer should always be 6 characters long, the shorthand with 3 will not work here.

The following are examples of expected output values:

rgb(255, 255, 255) // returns FFFFFF
rgb(255, 255, 300) // returns FFFFFF
rgb(0,0,0) // returns 000000
rgb(148, 0, 211) // returns 9400D3
# A)
```js
function rgb(r, g, b){
  // complete this function  
 const convert = (color) => {
   if (color.toString(16).length === 1 ) return '0' + color.toString(16).toUpperCase()
   if (color < 0) return '00'
   if (color >= 255 ) return 'FF'
   return color.toString(16).toUpperCase()
   }
 return convert(r) + convert(g) + convert(b)
}
```

보조함수 안에 첫번째 if문은 리턴문에 slice를 줘서 없앨 수 있다.
한자릿수면 00으로 둘다 가져가고, 두자릿수면 000이 들어와서 뒤에 2자리만 빼간다.
```js
function rgb(r, g, b){
  // complete this function  
 const convert = (color) => {
   //if (color.toString(16).length === 1 ) return '0' + color.toString(16).toUpperCase()
   if (color < 0) return '00'
   if (color >= 255 ) return 'FF'
   return ('0' + color.toString(16).toUpperCase()).slice(-2)
   }
 return convert(r) + convert(g) + convert(b)
}
```
