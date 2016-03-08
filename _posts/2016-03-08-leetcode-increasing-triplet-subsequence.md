---
layout: post
title: Google Protocol Buffer
category: LEETCODE
tags: default
---
##Increasing Triplet Subsequence
###Brief:
Given an unsorted array return whether an increasing subsequence of length 3 exists or not in the array.

Formally the function should:

> Return true if there exists i, j, k  such that arr[i] < arr[j] <
> arr[k] given 0 ≤ i < j < k ≤ n-1 else return false.

Your algorithm should run in O(n) time complexity and O(1) space complexity.

###Examples:

> Given [1, 2, 3, 4, 5], return true.
> 
> Given [5, 4, 3, 2, 1], return false.


----------
###Answer:

> Find the minimum and second ones, then the third comes out, return
> True.

    class Solution(object):
        def increasingTriplet(self, nums):
            """
            :type nums: List[int]
            :rtype: bool
            """
            if len(nums) <= 2:
                return False
    
            top_min = sed_min = None
            for n in nums:
                if top_min is None or top_min >= n:
                    top_min = n
                elif sed_min is None or sed_min >= n:
                    sed_min = n
                else:
                    return True
            return False
