class Solution:
    def isSubsetSum(self, arr, target):
        # dp[j] will be True if sum 'j' is reachable
        dp = [False] * (target + 1)
        
        # Base case: A sum of 0 is always possible (empty subset)
        dp[0] = True
        
        for num in arr:
            # Iterate backwards to ensure each element is used only once.
            # If we went forward, we might use the same element multiple times.
            for j in range(target, num - 1, -1):
                if dp[j - num]:
                    dp[j] = True
        
        return dp[target]
# Data-structures-
