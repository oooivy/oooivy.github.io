---
layout: page
title: 【LeetCode】Largest Rectangle in Histogram
tagline: leetcode
---
{% include JB/setup %}



**题目** Given n non-negative integers representing the histogram's bar height where the width of each bar is 1, find the area of largest rectangle in the histogram.
![enter image description here](http://www.leetcode.com/wp-content/uploads/2012/04/histogram.png)
Above is a histogram where width of each bar is 1, given height = [2,1,5,6,2,3].
![enter image description here](http://www.leetcode.com/wp-content/uploads/2012/04/histogram_area.png)
The largest rectangle is shown in the shaded area, which has area = 10 unit.

For example,
Given height = [2,1,5,6,2,3],
return 10.

----------


思路
-------------

 1. 最后得到的最大长方形，一定是从图表的某一条X1到图表的另一条X2，高度为X1至X2中最小的。可以写出O(n2)的解法如下：

		public int largestRectangleArea(int[] height) {
        // Start typing your Java solution below
        // DO NOT write main() function
        int[] min = new int[height.length];
        int maxArea = 0;
        for(int i = 0; i < height.length; i++){
            if(height[i] != 0 && maxArea/height[i] >= (height.length - i)) {
                continue;
            }
            for(int j = i; j < height.length; j++){
                if(i == j) min[j] = height[j];
                else {
                    if(height[j] < min[j - 1]) {
                        min[j] = height[j];
                    }else min[j] = min[j-1];
                }
                int temp = min[j] * (j - i + 1);
                if(temp > maxArea) {
                    maxArea = tentativeArea;
                }
            }
        }
        return maxArea;
        }
    
其中
```
if(height[i] != 0 && maxArea/height[i] >=(height.length - i)) {
	                continue;
	 }
```
if语句的判断可以加速找到构成最大长方形的 [i,j]。

  2.在网上看到一个更好的代码,看了挺久才理解。主要思路是最后得到的最大长方形，必定包含某个完整的柱子，最大面积是n个连续的柱子中，最低的那个柱子的高度乘以n。
  循环一遍，可以就可以得到最大的长方形是以哪个柱子为最低柱子的。故算法复杂度为O（n）。

>注意以下几点：

>（1）给柱状图的每个柱子一个索引，从0到height.length-1，共height.length个柱子。

>（2）int[] h = new int[height.length + 1];  是加上height[length]=0。

>（3）用栈来存储单调递增的索引。

>（4）如果当前栈是空的或者栈顶元素的高度比目前索引指向的柱子高度低，则当前索引入栈。索引 i 继续往前走。 否则，索引 i 不动。挨个弹栈计算最大面积，并与全局变量maxArea作比较，取大的数做为maxArea。直到栈空或者栈顶元素stack.peek() 的高度小于当前 i 的高度。

>（5）由于栈内存放的元素是递增的，所以长方形中最矮的柱子如果是出栈的第t个柱子，它的宽度应该是当前索引 i - stack.peek() - 1。

```
public int largestRectangleArea(int[] height) {
        Stack<Integer> stack = new Stack<Integer>();
        int i = 0;
        int maxArea = 0;
        int[] h = new int[height.length + 1];
        h = Arrays.copyOf(height, height.length + 1);
        while(i < h.length){
            if(stack.isEmpty() || h[stack.peek()] <= h[i]){
                stack.push(i++);
            }else {
                int t = stack.pop();
                maxArea = Math.max(maxArea, h[t] * (stack.isEmpty() ? i : i - stack.peek() - 1));
            }
        }
        return maxArea;
    }
```


#### <i class="icon-pencil"></i> Feeling
 会用栈的解法都好巧妙啊！
