# Q.
Given an integer array nums, find the contiguous subarray (containing at least one number) which has the largest sum and return its sum.

 

Example 1:

Input: nums = [-2,1,-3,4,-1,2,1,-5,4]
Output: 6
Explanation: [4,-1,2,1] has the largest sum = 6.
Example 2:

Input: nums = [1]
Output: 1
Example 3:

Input: nums = [5,4,-1,7,8]
Output: 23
 

Constraints:

1 <= nums.length <= 3 * 104
-105 <= nums[i] <= 105

# A)
```js
/**
 * @param {number[]} nums
 * @return {number}
 */
var maxSubArray = function(nums) {
  let sumArr = [];
  let sum = 0;
  if(nums.length === 1) {
    return nums[0]
  }
  for (i=0;i<nums.length;i++) {
      sum = nums[i]
    for (j=i+1;j<nums.length;j++) {
        sum += nums[j]
        sumArr.push(sum);
      }
    }
  return Math.max(...sumArr)
};
```
계속 예외케이스 하나가 통과가 안돼서 하나하나 뜯어고치다가 내 알고리즘에 오류가 있다는걸 깨달았다. 그래서 다시 처음부터 갈아엎었다.

```js

var maxSubArray = function(nums) {
  let max = nums[0]
  let isMax = nums[0]
  for(i=1;i<nums.length;i++) {
    isMax = Math.max(isMax + nums[i] ,nums[i])
    if(isMax > max) {
      max = isMax
    }
  }
  return max
}
```
Runtime: 72 ms, faster than 95.36% of JavaScript online submissions for Maximum Subarray.
Memory Usage: 40.1 MB, less than 51.27% of JavaScript online submissions for Maximum Subarray.
