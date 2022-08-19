# leetcode-344-recursion-1


1. swap method 

        class Solution:
            def reverseString(self, s: List[str]) -> None:
                """
                Do not return anything, modify s in-place instead.
                """
                l = 0
                r = len(s)-1
                while l < r:
                    s[l], s[r] = s[r],s[l]
                    l+=1
                    r-=1
                    
           Tips:
           1） 最左、最右交换：列出来换位置
           2） 同时两边缩小到下一位
        
2. recursion method


