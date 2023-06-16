Link: https://leetcode.cn/problems/two-sum-ii-input-array-is-sorted/

Description: 

Given a 1-indexed array of integers numbers that is already sorted in non-decreasing order, find two numbers such that they add up to a specific target number. Let these two numbers be numbers[index1] and numbers[index2] where 1 <= index1 < index2 < numbers.length.

Return the indices of the two numbers, index1 and index2, added by one as an integer array [index1, index2] of length 2.

The tests are generated such that there is exactly one solution. You may not use the same element twice.

Your solution must use only constant extra space.

思路：使用双指针left和right，其中left从头开始往右，而right从右开始往左。若left和right所指向的值的和小于target，则left++，反之right--，直到所和等于target。

```c++
vector<int> twoSum(vector<int>& numbers, int target) {
        int left = 0, right = numbers.size() - 1;
        vector<int> res;
        while(left < right) {
            int temp = numbers[left] + numbers[right];
            if(temp == target) {
                res.emplace_back(left + 1);
                res.emplace_back(right + 1);
                return res;
            }
            temp < target ? left++ : right--;
        }
        return res;
    }
```

Time: O(n)

Space: O(1)
