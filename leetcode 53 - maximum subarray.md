观察:

1) 一个最大和子序列,除非整个序列都是负数,不然一定有正数,而且头尾一定为证数 (否则不如继续缩减)

由此,

从左边开始,检查到第一个正数时开始计算最大和,遇到下一个正数时检查最大和,

如果这时的最大和大于0,说明前面这一段有正向作用,保留.否则从下一个正数开始

如果找不到下一个正数,返回当前最大值


代码:


    class Solution:

    def maxSubArray(self, nums: List[int]) -> int:

        
        if(max(nums)<=0):
            return max(nums)
        
        summ = 0
        big = 0
        
        for i in range(0,len(nums)):
            if nums[i] >= 0 and summ <= 0:  # drop previous sequence
                summ = nums[i]
                big = max(big,summ)
                
            elif nums[i] >=0 and summ > 0:  # meet next positive number, add to sum
                summ += nums[i]
                big = max(big,summ)
                
            elif nums[i] < 0:
                summ += nums[i]
            
            # print(summ)
        
        return max(summ, big)
            
