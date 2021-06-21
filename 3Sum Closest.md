Given an array nums of n integers and an integer target, find three integers in nums such that the sum is closest to target. Return the sum of the three integers. You may assume that each input would have exactly one solution.

 

Example 1:

Input: nums = [-1,2,1,-4], target = 1
Output: 2
Explanation: The sum that is closest to the target is 2. (-1 + 2 + 1 = 2).

```csharp
public class Solution {
    public int ThreeSumClosest(int[] nums, int target) {
        Array.Sort(nums);
        var n = nums.Length;

        var globalClosest = int.MaxValue;
        var globalSum = 0;
        for (int i = 0; i < n; i++) {
            var left = i + 1;
            var right = n - 1;

            while (left < right) {
                var sum = nums[i] + nums[left] + nums[right];
                var localClosest = Math.Abs(sum - target);
                if (sum == target) {
                    return target;
                } else if (sum < target) {
                    left++;
                } else {
                    right--;
                }

                if (globalClosest > localClosest) {
                    globalClosest = localClosest;
                    globalSum = sum;
                }
            }

        }

        return globalSum;
    }
}
```
