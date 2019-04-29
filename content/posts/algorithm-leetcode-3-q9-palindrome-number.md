---
title: "leetcode系列2 q9 Palindrome Number"
date: 2019-04-30T02:25:20+08:00
draft: false
categories: "algorithm"
tags: ["algorithm","leetcode","palindrome","revert"]
description: "这是一个leetcode系列第二篇，翻转int数字"
bigimg: [{src: "https://res.cloudinary.com/dfynefyys/image/upload/v1553708995/personal%20website/leetcode/1-two-sum.png", desc: "Nanjing China|Mar 28,2019"}]
nocomment: false
postmeta: false
notoc: ture
subtitle: "作者：王呈飞"
---


###这题是回文数判断，最可能想到的字符串翻转比对，但是题目限制了不要使用字符串

[leetcode问题链接](https://leetcode.com/problems/palindrome-number/ "leetcode问题链接")
#### \#1. Palindrome Number
CATEGORY:EASY

Determine whether an integer is a palindrome. An integer is a palindrome when it reads the same backward as forward.

Example 1:

Input: 121
Output: true
Example 2:

Input: -121
Output: false
Explanation: From left to right, it reads -121. From right to left, it becomes 121-. Therefore it is not a palindrome.
Example 3:

Input: 10
Output: false
Explanation: Reads 01 from right to left. Therefore it is not a palindrome.
Follow up:

Coud you solve it without converting the integer to a string?

##### 我的答案：
```java
class Solution {
    public boolean isPalindrome(int x) {
		//负数不可能是回文数,10的倍数且不为零的数不可能是回文数
        if(x<0||(x%10==0 && x!=0)){
            return false;
        }
        
        int revertedNumber = 0;
		//当未翻转数x大于已经翻转的数时，继续从x的尾数开始翻转
        while(x>revertedNumber){
            revertedNumber = revertedNumber*10 + x%10;
            x /= 10;
        }
        
		//当输入为偶数位时，未翻转数和翻转数两者相等时即输入为回文数，当输入为奇数位时，翻转数比未翻转数多一个中间位的尾数，翻转数/10后再对比
        return x==revertedNumber||x==revertedNumber/10;
        
    }
}
```
思路:参考leecode给出的答案，先过滤一定不是回文数的值，例如负数和非0的10的倍数；然后通过只翻转一半，来避免翻转数字越界，接下来只要对比这已经翻转的一半和未翻转的一半是否相等即可，判断是否翻转一半的条件是剩余未翻转的数是否比翻转的数字大，需要注意的是，在输入值得位数是偶数和奇数的情况下处理逻辑稍有不同。

