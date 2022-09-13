
#flashcards 
## Description
You are given an array `prices` where `prices[i]` is the price of a given stock on the `ith` day.
You want to maximize your profit by choosing a **single day** to buy one stock and choosing a **different day in the future** to sell that stock.
Return _the maximum profit you can achieve from this transaction_. If you cannot achieve any profit, return `0`.
## Example
```
**Input:** prices = [7,1,5,3,6,4]
**Output:** 5
**Explanation:** Buy on day 2 (price = 1) and sell on day 5 (price = 6), profit = 6-1 = 5.
Note that buying on day 2 and selling on day 1 is not allowed because you must buy before you sell.
```
?
## Two Pointers Sliding Window
**TC:** ``O(n)
**SC:** ``O(1) 
1. Check if left pointer (buy) is greater than right pointer (sell) indicating a bad trade
2. If a bad trade shift left pointer to the position of right pointer (new lowest point)
3. If not, shift right pointer to attempt to find new highest point
4. Track the maximum difference between two points in a variable
5. at the end of the loop, print the maximum
## Code
```python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        l, r = 0, 1
        currentMax = 0
        while r < len(prices):
            newMax = prices[r] - prices[l]
            if newMax > currentMax:
                currentMax = newMax
            #if the buy is higher, move l pointer to r
            if prices[l] > prices[r]:
                l = r
            #else, increment right pointer to find more highs    
            else:
                r += 1
        return currentMax
```
![[Pasted image 20220907172715.png]]