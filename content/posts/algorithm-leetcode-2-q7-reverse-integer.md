---
title: "leetcode系列2 q7 Reverse Integer"
date: 2019-03-30T02:25:20+08:00
draft: false
categories: "algorithm"
tags: ["algorithm","leetcode","integer","overflow"]
description: "这是一个leetcode系列第二篇，翻转int数字"
bigimg: [{src: "https://res.cloudinary.com/dfynefyys/image/upload/v1553708995/personal%20website/leetcode/1-two-sum.png", desc: "Nanjing China|Mar 28,2019"}]
nocomment: false
postmeta: false
notoc: ture
subtitle: "万事开头难，所以从简单的开始"
---


### 这是一个新的系列，主要记录一些自己在leetcode上的刷题记录，个人水平有限，难度先从easy开始

[leetcode问题链接](https://leetcode.com/problems/reverse-integer/ "leetcode问题链接")
#### \#1. Reverse Integer
CATEGORY:EASY

Given a 32-bit signed integer, reverse digits of an integer.

Example 1:

Input: 123
Output: 321
Example 2:

Input: -123
Output: -321
Example 3:

Input: 120
Output: 21
Note:
Assume we are dealing with an environment which could only store integers within the 32-bit signed integer range: [−231,  231 − 1]. For the purpose of this problem, assume that your function returns 0 when the reversed integer overflows.

##### 我的答案：
```java
class Solution {
    public int reverse(int x) {
        int z = 0;
        int y = 0;
       
        if(x==0){
            return 0;
        }
        while(x!=0){
            y = x%10;
            x = x/10;
            
            
            
            if(z>(Integer.MAX_VALUE/10)||(z==Integer.MAX_VALUE/10&&y>7)){//正数情况下的越界判断
                return 0;
            }
            if(z<(Integer.MIN_VALUE/10)||(z==Integer.MIN_VALUE/10&&y<-8)){//负数情况下的越界判断
                return 0;
            }
            z = z*10+y;
        }
        return z;

        
    }
}
```
思路:对输入的int数字从尾部开始处理，判断在生成目标结果的过程中的中间态数值是否计算后越界，越界判断的逻辑如上述代码所示，这里的逻辑参看leetcode原题里面的solution解释，，我在写的时候也参看了它。

