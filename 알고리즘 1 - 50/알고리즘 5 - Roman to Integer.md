# Q.
Roman numerals are represented by seven different symbols: I, V, X, L, C, D and M.

Symbol       Value
I             1
V             5
X             10
L             50
C             100
D             500
M             1000

For example, 2 is written as II in Roman numeral, just two one's added together. 12 is written as XII, which is simply X + II. The number 27 is written as XXVII, which is XX + V + II.

Roman numerals are usually written largest to smallest from left to right. However, the numeral for four is not IIII. Instead, the number four is written as IV. Because the one is before the five we subtract it making four. The same principle applies to the number nine, which is written as IX. There are six instances where subtraction is used:

I can be placed before V (5) and X (10) to make 4 and 9. 
X can be placed before L (50) and C (100) to make 40 and 90. 
C can be placed before D (500) and M (1000) to make 400 and 900.
Given a roman numeral, convert it to an integer.

 

Example 1:

Input: s = "III"
Output: 3
Example 2:

Input: s = "IV"
Output: 4
Example 3:

Input: s = "IX"
Output: 9
Example 4:

Input: s = "LVIII"
Output: 58
Explanation: L = 50, V= 5, III = 3.
Example 5:

Input: s = "MCMXCIV"
Output: 1994
Explanation: M = 1000, CM = 900, XC = 90 and IV = 4.
 

Constraints:

1 <= s.length <= 15
s contains only the characters ('I', 'V', 'X', 'L', 'C', 'D', 'M').
It is guaranteed that s is a valid roman numeral in the range [1, 3999].
# A)
```js
var romanToInt = function(s) {
  const romaArr = {
        I : 1 , V : 5, X : 10 , L : 50, C: 100 , D : 500, M : 1000 
  }
  let result = 0
  for(i=0;i<s.length;i++) {  
    first = romaArr[s[i]]
    second = romaArr[s[i+1]]
    if(first === second) {
      result = result + romaArr[s[i]] + romaArr[s[i+1]]
      i++
    }
    else if(second > first ) {
      result = result + romaArr[s[i+1]] -romaArr[s[i]]
      i++
    }
    else {
      result = result + romaArr[s[i]]
    }
  }  
      return result
  
};
```

Runtime: 140 ms, faster than 91.32% of JavaScript online submissions for Roman to Integer.
Memory Usage: 44.6 MB, less than 75.63% of JavaScript online submissions for Roman to Integer.


이번문제는 어려웠다. 문제의 'Roman numerals are usually written largest to smallest from left to right. ' 에서 힌트를 얻어서 왼쪽 > 오른쪽 이면 오른쪽-왼쪽 을 결과값에 더하고 아니라면 왼쪽값만 더해줬더니 'III'같은 로마숫자는 5가 나왔다. 그래서 i++를 마지막으로 돌려서 (2)+(1+undefined)가 나오게 했다.  else if 문에서 i++를 한 것도 MCM 같은 수가 나오면 M 한번 C 한번 M 한번씩 for문을 수행하게 되어서 원하는 수가 안나왔다. 그래서  M 한번 CM한번 으로 묶으려고 넣었다.  처음엔 s.length가 홀수/짝수일때로 나눠서 하려고 했지만 시간복잡도를 고려해서 i++로 해결했다. 
