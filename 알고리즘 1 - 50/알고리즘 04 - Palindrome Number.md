# Q.
Given an integer x, return true if x is palindrome integer.

An integer is a palindrome when it reads the same backward as forward. For example, 121 is palindrome while 123 is not.

 

Example 1:

Input: x = 121
Output: true
Example 2:

Input: x = -121
Output: false
Explanation: From left to right, it reads -121. From right to left, it becomes 121-. Therefore it is not a palindrome.
Example 3:

Input: x = 10
Output: false
Explanation: Reads 01 from right to left. Therefore it is not a palindrome.
Example 4:

Input: x = -101
Output: false
 

Constraints:

-231 <= x <= 231 - 1
 

Follow up: Could you solve it without converting the integer to a string?

# A)
```js
var isPalindrome = function(x) {
    //  
    // length / 2 해서 앞부분을 a배열에 담고 뒷부분 b는 리버스해서 배열에 담은후  a 와 b를 스트링으로 비교하기
    let xToStr = String(x)
    let frontOfX = xToStr.split('',xToStr.length/2)
    let reverseX = String(x).split('').reverse().join('')
    let backOfX = reverseX.split('',reverseX.length/2)
        
    return frontOfX.join('') === backOfX.join('')
}
```

Runtime: 220 ms, faster than 46.33% of JavaScript online submissions for Palindrome Number.
Memory Usage: 48.5 MB, less than 59.05% of JavaScript online submissions for Palindrome Number.
