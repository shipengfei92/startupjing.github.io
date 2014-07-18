---
layout: post
title:  "CC150 Problem 2.1"
date:   2014-07-02
categories: coding_problems
---

# Remove duplicate in a list


Write code to remove duplicates from an unsorted linked list.
FOLLOW UP
How would you solve this problem if a temporary buffer is not allowed?

{% highlight ruby %}

import java.util.*;

public class RemoveDuplicate {

	public static void main(String[] args) {
		MyList<Integer> l1 = new MyList<Integer>(new Integer[]{2,7,5,4,2,2,4,6,6});
		MyList<Integer> l2 = new MyList<Integer>(new Integer[]{2,7,5,4,2,2,4,6,6});
		
		System.out.println("Using hashset to remove duplicate...");
		l1.print();
		removeDupTwo(l1.head);
		l1.print();
		
		System.out.println("No memory buffer used to remove duplicate...");
		l2.print();
		removeDupTwo(l2.head);
		l2.print();

	}
	
	
	public static void removeDupOne(Node<Integer> head){
		//check simple case
		if(head == null || head.next == null){
			return;
		}
		
		Set<Integer> contents = new HashSet<Integer>();
		
		Node<Integer> p = head;
		
		//traverse the list
		while(p != null){
			//if duplicate exists, remove the node
			if(contents.contains(p.val)){
				p.prev.next = p.next;
				if(p.next != null){
					p.next.prev = p.prev;
				}
			}else{
				contents.add(p.val);
			}
			p = p.next;
		}
	}
	
	
	public static void removeDupTwo(Node<Integer> head){
		//check simple case
		if(head == null || head.next == null){
			return;
		}
		
		//two points
		Node<Integer> p1 = head;
		Node<Integer> p2 = head;
		
		//one pointer to traverse every element and another to 
		//traverse the rest of list every time to check duplicate
		while(p1 != null){
			p2 = p1.next;
			while(p2 != null){
				if(p1.val == p2.val){
					p2.prev.next = p2.next;
					if(p2.next != null){
						p2.next.prev = p2.prev;
					}
				}
				p2 = p2.next;
			}
			p1 = p1.next;
		}
	}
	
	

}


{% endhighlight %}

