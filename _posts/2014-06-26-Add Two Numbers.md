
---
layout: page
title: 【LeetCode】Add Two Numbers
---
{% include JB/setup %}



**题目**You are given two linked lists representing two non-negative numbers. The digits are stored in reverse order and each of their nodes contain a single digit. Add the two numbers and return it as a linked list.

Input: (2 -> 4 -> 3) + (5 -> 6 -> 4)
Output: 7 -> 0 -> 8

----------

** 思路**
这题比较简单，注意链表相关操作就可以了。
		if (temp != 0) {  
				           ret.next = new ListNode(0);  
				           ret.next.val = temp;  
				}

刚开始想复杂了，它本来就是倒置的，直接从头开始加就可以，不用再倒置了。注意最后的进位判断，否则会出错。

		
		/**
		 * Definition for singly-linked list.
		 * public class ListNode {
		 *     int val;
		 *     ListNode next;
		 *     ListNode(int x) {
		 *         val = x;
		 *         next = null;
		 *     }
		 * }
		 */
		public class Solution {
		    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
		        // Start typing your Java solution below
		        // DO NOT write main() function
		        ListNode ret=new ListNode(0);
		        ListNode start=ret;
		        int l1v=0;
		        int l2v=0;
		        int temp=0;
		        ListNode t1 = l1;  
		        ListNode t2 = l2;  
		        while(t1!=null||t2!=null){
		            ret.next=new ListNode(0);
		            ret=ret.next;
		            if(t1==null){
		                l1v=0;
		            }else{
		                l1v=t1.val;
		                t1=t1.next;
		            }
		            if(t2==null){
		                l2v=0;
		            }else{
		                l2v=t2.val;
		                t2=t2.next;
		            }
		            ret.val=(l1v+l2v+temp)%10;
		            temp=(l1v+l2v+temp)/10;
		        }
		        if (temp != 0) {  
		            ret.next = new ListNode(0);  
		            ret.next.val = temp;  
		        }  
		        return start.next;
		    }
		}