## 2. Reverse Integer
Given a 32-bit signed integer, reverse digits of an integer.  

**Example 1**

Input: 123  
Output: 321

**Example 2**

Input: -123   
Output: -321

**Note**
Assume we are dealing with an environment which could only store integers within the 32-bit signed integer range: [−231,  231 − 1]. 
For the purpose of this problem, assume that your function returns 0 when the reversed integer overflows.

## Solutions
### Approach 1: 
```python
def reverse(self, x:int) -> int:
  minr = - pow(2, 31)
  maxr = pow(2, 31) - 1

  sign = 1 if x >= 0 else -1
  x_new, x = 0, abs(x)

  while x:
    digit = x % 10
    x //= 10
    x_new = x_new * 10 + digit

   x_new = sign * x_new

   return(x_new) if x_new in range(minr, maxr) else 0
```

### Approach 2:
```python
def reverse(self, x:int) -> int:
  minr = pow(-2, 31)
  maxr = pow(2, 31) - 1
  if x >= 0:
    x_new = int(str(x)[::-1])
  else:
    x = abs(x)
    x_new = -1 * int(str(x)[::-1])
  if x_new in range(minr, maxr):
    return(x_new)
  else:
    return(0)
```
