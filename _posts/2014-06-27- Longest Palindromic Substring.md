---
layout: page
title: 【LeetCode】Longest Palindromic Substring
---
{% include JB/setup %}
**题目**Given a string S, find the longest palindromic substring in S. You may assume that the maximum length of S is 1000, and there exists one unique longest palindromic substring.


----------
 思路
-------------
自己只想到了O(n2)的算法，遍历每个字符，然后从中间向两旁扩，寻找最长子串。显示的结果一直是pending...

[此处](http://www.felix021.com/blog/read.php?2040)有O(n)的算法

 

		public class Solution {

		    public String longestPalindrome(String s) {
		        // Start typing your Java solution below
		        // DO NOT write main() function
		        StringBuilder sb = new StringBuilder();
		        sb.append('#');
		        for (int i = 0; i < s.length(); i++)
		        {
		            sb.append(s.charAt(i));
		            sb.append('#');
		        }
		         
		        String ss = sb.toString();
		        int[] p = new int[ss.length()];
		        int mx = 0;
		        int id = 0;
		        for (int i = 0; i < ss.length(); i++)
		        {
		            p[i] = mx > i ? Math.min(p[id * 2 -i], mx - i) : 1;
		            while (i+p[i] < ss.length() && i - p[i] >=0)
		            {
		                if (ss.charAt(i + p[i]) == ss.charAt(i-p[i]))
		                {
		                    p[i]++;
		                }
		                else
		                {
		                    break;
		                }
		            }
		            if (i + p[i] > mx)
		            {
		                mx = i + p[i];
		                id = i;
		            }
		        }
		         
		        // process result
		        int maxIndex = 0;
		        int maxLen = 0;
		        for (int i = 0; i < ss.length(); i++)
		        {
		            if( p[i] > maxLen)
		            {
		                maxLen = p[i];
		                maxIndex = i;
		            }
		        }
		        StringBuilder r = new StringBuilder();
		        for (int i = maxIndex - p[maxIndex] + 1; i <= maxIndex + p[maxIndex] - 1; i++)
		        {
		            if(ss.charAt(i) != '#')
		            {
		                r.append(ss.charAt(i));
		            }
		        }
		        return r.toString();
		    }
		}