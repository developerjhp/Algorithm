# Q.
Write a function to find the longest common prefix string amongst an array of strings.

If there is no common prefix, return an empty string "".

 

Example 1:

Input: strs = ["flower","flow","flight"]
Output: "fl"
Example 2:

Input: strs = ["dog","racecar","car"]
Output: ""
Explanation: There is no common prefix among the input strings.
 

Constraints:

1 <= strs.length <= 200
0 <= strs[i].length <= 200
strs[i] consists of only lower-case English letters.

# A)
```js
var longestCommonPrefix = function(strs) {
  let result = ''
  if (strs.length === 0) return result
  for (i=0; i<strs[0].length ; i++) {
    const standard = strs[0][i]
    for(j=0; j < strs.length ; j++ ) {
      if(strs[j][i] !== standard) {
        return result
      }
    }
   result = result + standard
  }
  return result
};  
```
Runtime: 88 ms, faster than 42.16% of JavaScript online submissions for Longest Common Prefix.
Memory Usage: 38.9 MB, less than 86.26% of JavaScript online submissions for Longest Common Prefix.

