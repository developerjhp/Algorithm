# Q.
Given a string s containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

An input string is valid if:

Open brackets must be closed by the same type of brackets.
Open brackets must be closed in the correct order.
 

Example 1:

Input: s = "()"
Output: true
Example 2:

Input: s = "()[]{}"
Output: true
Example 3:

Input: s = "(]"
Output: false
Example 4:

Input: s = "([)]"
Output: false
Example 5:

Input: s = "{[]}"
Output: true
 

Constraints:

1 <= s.length <= 104
s consists of parentheses only '()[]{}'.

# a)

```js
var isValid = function(s) {
    let pair = {
      '(' : ')',
      '{' : '}',
      '[' : ']'
    } ;
    const result = [];
    for(let i=0;i<s.length;i++) {
      if ( s[i] in pair) {
        result.push(s[i])
      }
      else if (pair[result.pop()] !== s[i]) {
        return false;
      }
    }
    return result.length === 0;
};

```


Runtime: 68 ms, faster than 96.05% of JavaScript online submissions for Valid Parentheses.
Memory Usage: 38.7 MB, less than 76.21% of JavaScript online submissions for Valid Parentheses.



