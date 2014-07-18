---
layout: post
title:  "CC150 Problem 2.6"
date:   2014-07-02
categories: blog
---

# Find the beginning of a loop in a circular linked list


Given a circular linked list, implement an algorithm which returns the node at the beginning of the loop.
DEFINITION
Circular linked list: A (corrupt) linked list in which a node's next pointer points to an earlier node, so as to make a loop in the linked list.
EXAMPLE
Input:A ->B->C->D->E-> C[thesameCasearlier] 
Output:C



{% highlight ruby %}

import java.util.*;

public class SumList {

	public static void main(String[] args) {
		MySingleList<Integer> l1 = new MySingleList<Integer>(new Integer[] {7,1,6});
		MySingleList<Integer> l2 = new MySingleList<Integer>(new Integer[] {5,9,2});
		MySingleList<Integer> l3 = new MySingleList<Integer>(new Integer[] {6,1,7});
		MySingleList<Integer> l4 = new MySingleList<Integer>(new Integer[] {2,9,5});
		
		MySingleList<Integer> l5 = new MySingleList<Integer>(new Integer[] {6,1,7,1});
		MySingleList<Integer> l6 = new MySingleList<Integer>(new Integer[] {2,9,5});
		MySingleList<Integer> l7 = new MySingleList<Integer>(new Integer[] {1,7,1,6});
		MySingleList<Integer> l8 = new MySingleList<Integer>(new Integer[] {5,9,2});
		
		System.out.println("reverse addition...");
		l1.print();
		l2.print();
		reverseSum(l1,l2).print();
		
		System.out.println();
		System.out.println("inorder addition...");
		l3.print();
		l4.print();
		orderSum(l3,l4).print();
		
		System.out.println();
		System.out.println("reverse addition...");
		l5.print();
		l6.print();
		reverseSum(l5,l6).print();
		
		System.out.println();
		System.out.println("inorder addition...");
		l7.print();
		l8.print();
		orderSum(l7,l8).print();
		
	}
	
	/**
	 * sum two lists in reverse order
	 * @param l1
	 * @param l2
	 * @return sum as a list
	 */
	public static MySingleList<Integer> reverseSum(MySingleList<Integer> l1, MySingleList<Integer> l2){
		int sum = reverseNum(l1) + reverseNum(l2);
		return sumIntoList(sum);
	}
	
	/**
	 * sum two lists in order
	 * @param l1
	 * @param l2
	 * @return sum as a list
	 */
    public static MySingleList<Integer> orderSum(MySingleList<Integer> l1, MySingleList<Integer> l2){
		int sum = orderNum(l1) + orderNum(l2);
		return reverseList(sumIntoList(sum));
	}
    
    /**
     * read numbers in reverse
     * @param l
     * @return number in the list
     */
    public static int reverseNum(MySingleList<Integer> l){
    	int num = 0;
    	int count = 0;
    	Node<Integer> curr = l.head;
    	while(curr != null){
    		num = num + curr.val * (int)Math.pow(10, count);
    		count ++;
    		curr = curr.next;
    	}
    	return num;
    }
    
    /**
     * read numbers in order
     * @param l
     * @return number in the list
     */
    public static int orderNum(MySingleList<Integer> l){
    	int num = l.head.val;
    	Node<Integer> curr = l.head.next;
    	while(curr != null){
    		num = num*10 + curr.val;
    		curr = curr.next;
    	}
    	return num;
    }
    
    /**
     * use a stack to reverse a single linked list
     * @param l
     * @return reversed list
     */
    public static MySingleList<Integer> reverseList(MySingleList<Integer> l){
    	Stack<Integer> s = new Stack<Integer>();
    	Node<Integer> p = l.head;
    	while(p != null){
    		s.push(p.val);
    		p = p.next;
    	}
    	p = l.head;
    	while(p != null){
    		p.val = s.pop();
    		p = p.next;
    	}
    	return l;
    } 
    
    /**
     * represent a number as a list
     * @param sum
     * @return list representing the number
     */
    public static MySingleList<Integer> sumIntoList(int sum){
    	int temp = sum;
		int len = 0;
		while(temp != 0){
		   temp = (temp - (temp % 10))/10;
		   len++;	
		}
		Integer[] arr = new Integer[len];
		for(int i=0; i<len; i++){
		   arr[i] = sum % 10;
		   sum = (sum - arr[i])/10;
		}
		return new MySingleList<Integer>(arr);
    }
    
}



{% endhighlight %}

