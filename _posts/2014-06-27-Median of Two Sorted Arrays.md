
---
layout: page
title: 【leetcode】 Median of Two Sorted Arrays
---
{% include JB/setup %}

**题目**
There are two sorted arrays A and B of size m and n respectively. Find the median of the two sorted arrays. The overall run time complexity should be O(log (m+n)).


----------

1、如果把A和B合并成C，再取中位数。复杂度应该是O(m+n)，不满足要求。

2、要清楚的一个概念是：如果(m+n)为偶数，中位数应该是(m+n)个数排序后，位于中间的两个数的加和除以2.0。

3、没有思路……

用了[这篇](http://www.cnblogs.com/lautsie/p/3183086.html )里提供的解法，[主要算法参考](http://www2.myoops.org/course_material/mit/NR/rdonlyres/Electrical-Engineering-and-Computer-Science/6-046JFall-2005/30C68118-E436-4FE3-8C79-6BAFBB07D935/0/ps9sol.pdf)

思路
-------------

若（m+n）为奇数，只需找到一个中位数即为所求解;
　　　若（m+n）为偶数，找到第一个中位数后还应再找第二个，加和除以2.0。
　　寻找第一个中位数时，先在数组A中寻找中位数，如果找不到再在数组B中寻找。
　　findMedFromFirstArray寻找第一个中位数的思路：total表示第一个中位数之前应该有几个数字，在A中用二分查找A[mid], idx=total-mid,表示如果此时的A[mid]是第一个中位数的话，B中应该有且仅有idx个数小于A[mid]，即B[idx] <= A[mid] && A[mid] <= B[idx + 1] ，这是在A中找到第一个中位数的终止条件。不满足这个终止条件，则需调整la和ra，取新的mid，作相同的判断。
(idx < 0 && (idx + 1) >= 0 && A[mid] <= B[idx + 1]) 的情况是：idx=-1 A[mid]<=B[0]
　　在二分查找的同时要注意idx的取值应该是有意义的。如果没有意义也应该相应调整la和ra。

　　找到第一个中位数A[mid]后，如（m+n）为偶，需要找第二个中位数，第二个中位数应该是A[mid+1] 及B[total+1-mid]中较小的一个。total+1表示第二个中位数之前应该有几个数字。如果第一个中位数在B数组中，也是一样的，所以不妨把第一个中位数所在的数组命名为A。这就是findMed2的思路。

	
class Result
{
    public int[] array;
    public int index;
}
  
public class Solution {
    public double findMedianSortedArrays(int A[], int B[]) {
        // Start typing your Java solution below
        // DO NOT write main() function
          
        // special cases
        if (A.length == 0){
            if (B.length % 2 == 0)
            {
                return (B[B.length / 2 - 1] + B[B.length / 2]) / 2.0;
            }
            else
            {
                return B[B.length / 2];
            }
        }
        else if (B.length == 0)
        {
            if (A.length % 2 == 0)
            {
                return (A[A.length / 2 - 1] + A[A.length / 2]) / 2.0;
            }
            else
            {
                return A[A.length / 2];
            }
        }
        else if (A.length == 1 && B.length == 1)
        {
            return (A[0] + B[0]) / 2.0;
        }
  
        Result r = findMedFromFirstArray(A, B);
        if (r.index == Integer.MIN_VALUE){
            r = findMedFromFirstArray(B, A);
        }
        if (( A.length + B.length) % 2 == 0) // need to find med2
        {
            int med2 = findMed2(r, A, B);
            return (r.array[r.index] + med2) / 2.0;
        }
        else
        {
            return r.array[r.index];
        }
  
    }
  
    private Result findMedFromFirstArray(int A[], int B[])
    {
        int la = 0;
        int ra = A.length - 1;
        int total = 0;
        if (( A.length + B.length) % 2 == 0)
        {
            total = (A.length + B.length)/2 - 2;
        }
        else
        {
            total = (A.length + B.length)/2 - 1;
        }
        while (la <= ra)
        {
            int mid = (la + ra) / 2;
            int idx =  total - mid;
  
            if ((idx < 0 && (idx + 1) >= 0 && A[mid] <= B[idx + 1]) ||
                    (idx >= 0 && idx < B.length && idx + 1 >= B.length && B[idx] <= A[mid]) ||
                    (idx >= 0 && idx + 1 < B.length && B[idx] <= A[mid] && A[mid] <= B[idx + 1]))
            {
                    Result r = new Result();
                    r.index = mid;
                    r.array = A;
                    return r;
            }
            if (idx >= B.length)
            {
                la = mid+1;
            }
            else if (idx < 0)
            {
                ra = mid-1;
            }
            else if (B[idx] > A[mid])
            {
                la = mid + 1;
            }
            else
            {
                ra = mid - 1;
            }
        }
        Result r = new Result();
        r.index = Integer.MIN_VALUE; // this means not find
        r.array = A;
        return r;
    }
      
    private int findMed2(Result r, int ArrayA[], int ArrayB[])
    {
        int target1 = Integer.MAX_VALUE;
        int target2 = Integer.MAX_VALUE;
        int[] A = ArrayA;
        int[] B = ArrayB;
        if (r.array == B)
        {
            A = ArrayB;
            B = ArrayA;
        }
        {
            if (r.index + 1 < A.length)
            {
                target1 = A[r.index + 1];
            }
            int idx = ( A.length + B.length) / 2 - 2 - r.index + 1;
            if (idx >= 0 && idx < B.length)
            {
                target2 = B[idx];
            }
              
            if (target1 < target2)
            {
                return target1;
            }
            else
            {
                return target2;
            }
        }
    }
          
}