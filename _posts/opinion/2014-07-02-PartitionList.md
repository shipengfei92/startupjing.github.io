---
layout: post
title:  "CC150 Problem 2.4"
date:   2014-07-02
categories: coding_problems
---

# Partition the list using given value

Write code to partition a linked list around a value x, such that all nodes less than x come before all nodes greater than or equal to x.


{% highlight ruby %}
public class PartitionList {
	public static void main(String[] args) {
		MyList<Integer> l1 = new MyList<Integer>(new Integer[]{6,4,3,1,2,9,0});
		int k = 2;
		l1.print();
		partition(l1, k);
		System.out.println("partition the list...");
		l1.print();
	}
	
	/**
	 * partition the list with the given value k
	 * traverse the list, if see a node with val <= k, then move it to the front
	 * @param l
	 * @param k
	 */
	public static void partition(MyList<Integer> l, int k){
		Node<Integer> p = l.head;
		while(p != null){
			Node<Integer> temp = p.next;
			//move node to the front
			if(p.val <= k){
				temp = p.next;
				if(p.prev == null){
					return;
				}
		
				p.prev.next = p.next;
				if(p.next != null){
					p.next.prev = p.prev;
				}
				
				l.head.prev = p;
				p.next = l.head;
				l.head = p;
			}
			p = temp;
		}
			
	}
}
{% endhighlight %}

