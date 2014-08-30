---
layout: page
title: 【LeetCode】Maximal Rectangle
---
{% include JB/setup %}



**思路** 　这个题目可以利用最大直方图的做法，遍历每一行O(n)，把每一行看成以这一行为底的直方图，如

1 0 0 1 1

1 0 1 1 1

0 1 0 1 0

　　第一行可以看成 height = [1,0,0.1,1] 的直方图，第二行看成 height = [2,0,1.2,2]，第三行看成height = [0,1,0,3,0] 。这样就可以利用求最大直方图的算法来解决。算法复杂度为 O(n)*O(n)=O(n2)。

　　在把二维数组matrix转化为height的二维数组时，根据matrix[i][j]=='0'进行转化，不是想当然的加和。