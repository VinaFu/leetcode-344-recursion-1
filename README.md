# leetcode-344-recursion-1

这一题主要考recursion，但也可以用stack和swap回答。
recursion在最后一步。需要练习好多遍呀～

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
        
2. stack method

        class Solution:
            def reverseString(self, s: List[str]) -> None:
                """
                Do not return anything, modify s in-place instead.
                """
                stack = []
                for c in s:
                    stack.append(c)
                print(stack) 
                    # 建一个Stack，这样待会就可以从后面取value。
                
                i = 0
                while stack:
                      s[i] = stack.pop()
                      i+=1
                        # 题目要求从list里面改，所以改index。每一个index和值对应。
             
3. recursion method

        class Solution:
            def reverseString(self, s: List[str]) -> None:
                """
                Do not return anything, modify s in-place instead.
                """
                def reverse(l,r):
                    if l < r:
                        s[l], s[r] = s[r], s[l]
                        reverse(l+1, r-1)
                        # recursion指的是先写一个单独情况，再运用到剩下的元素
                        # define一个函数=换位置，然后用自己处理剩余的（line53）
                        # 剩余部分即是缩短range：±1
                reverse(0, len(s)-1)
                        # 在什么范围里叫函数。

