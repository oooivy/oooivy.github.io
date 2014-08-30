---
layout: page
title: 【leetcode】 Reverse digits of an integer
---
{% include JB/setup %}

**题目**
Example1: x = 123, return 321
Example2: x = -123, return -321

click to show spoilers.

Have you thought about this?
Here are some good questions to ask before coding. Bonus points for you if you have already thought through this!

If the integer's last digit is 0, what should the output be? ie, cases such as 10, 100.

Did you notice that the reversed integer might overflow? Assume the input is a 32-bit integer, then the reverse of 1000000003 overflows. How should you handle such cases?

Throw an exception? Good, but what if throwing an exception is not an option? You would then have to re-design the function (ie, add an extra parameter).

----------
**思路**比较简单的题目，尾数是0没有问题，但是题目提示的超过能表示的范围没有考虑，不过也A掉了。

class Solution {
public:
    int reverse(int x) {
        // Note: The Solution object is instantiated only once and is reused by each test case.
        int flag=1;
        if(x<0)
            flag=-1;
        int X=abs(x);
        int result=0;
        while(X>0){
            result=result*10+X%10;
            X=X/10;
        }
        return flag*result;
    }
};