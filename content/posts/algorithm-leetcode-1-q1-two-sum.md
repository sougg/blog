---
title: "leetcode系列1 q1 Two Sum"
date: 2019-03-28T01:43:20+08:00
draft: false
categories: "algorithm"
tags: ["algorithm","leetcode","hashmap"]
description: "这是一个新的系列，主要记录一些自己在leetcode上的刷题记录，个人水平有限，难度先从easy开始"
bigimg: [{src: "https://res.cloudinary.com/dfynefyys/image/upload/v1553708995/personal%20website/leetcode/1-two-sum.png", desc: "Nanjing China|Mar 28,2019"}]
nocomment: false
postmeta: false
notoc: ture
subtitle: "万事开头难，所以从简单的开始"
---


### 这是一个新的系列，主要记录一些自己在leetcode上的刷题记录，个人水平有限，难度先从easy开始

[leetcode问题链接](https://leetcode.com/problems/two-sum/ "leetcode问题链接")
#### \#1. Two Sum
CATEGORY:EASY

Given an array of integers, return indices of the two numbers such that they add up to a specific target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

Example:

Given nums = [2, 7, 11, 15], target = 9,

Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1].

##### 我的答案：
```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        HashMap<String> hashMap = new HashMap();
        for(int i=0;i<nums.length;i++){
            if(hashMap.contains(target-nums[i])){
                return new int[]{hashMap.get(target-nums[i]),i};
            }
            hashMap.put(nums[i],i);
        }
        throw Exception("not found!");
    }
}
```
思路:主要利用hashmap的快速查找能力

