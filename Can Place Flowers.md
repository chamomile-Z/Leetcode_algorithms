# Leetcode Solution( Single Scan)
```Python
    def canPlaceFlowers(self, flowerbed: List[int], n: int) -> bool:
        l = len(flowerbed)
        count = 0
        
        for i in range(l):
            if flowerbed[i] == 0 and (i == 0 or flowerbed[i-1] == 0) and (i == l-1 or flowerbed[i + 1] == 0):
                flowerbed[i] = 1
                count += 1
                
        return count >= n
```
## Method
- Time Complexity: O(n)
- Space Complexity: O(1)
