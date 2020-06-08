## 1. Two Sum
Given an array of integers, return indices of the two numbers such that they add up to a specific target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

## Solutions
### Approach 1: Brute Force
Loop through each element x and find if there is another value that equals to target - x.  

**Complexity Analysis**
- Time complexity: O(n^2). 
- Space complexity: O(1).

### Approach 2: Two-pass Hash Table
A simple implementation uses two iterations. In the first iteration, we add each element's value and its index 
to the table. Then, in the second iteration we check if each element's complement exists in the table. 

**Complexity Analysis**
- Time complexity: O(n) (we traverse the list containing n elements exactly twice. Since the hash 
table reduces the look up time to O(1), the time complexity is O(n).
- Space complexity: O(n) (trading space for speed)

**Code 1**  

```python 
def twoSum(self, nums: List[int], target: int) -> List[int]:
  dict = {}
  for i in range(len(nums)):
    if target - nums[i] in dict:
      return[i, dict[target - nums[i]]]
    else:
      dict[nums[i]] = i
```

**Code 2**

```python
def twoSum(self, nums: List[int], target: int) -> List[int]:
  """
  Arguments: nums - List[int] 
             target - int
  Returns: List[int]
  """
  
  h = {}
  for i, num in enumerate(nums):
    n = target - num

```






