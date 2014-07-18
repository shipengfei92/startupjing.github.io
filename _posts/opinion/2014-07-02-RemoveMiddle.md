---
layout: post
title:  "CC150 Problem 2.3"
date:   2014-07-02
categories: coding_problems
---

# Remove middle element in a list

Implement an algorithm to delete a node in the middle of a singly linked list, given only access to that node.
EXAMPLE
Input: the node c from the linked list a->b->c->d->e
Result: nothing isreturned, but the new linked list looks like a- >b- >d->e



{% highlight ruby %}

public class RemoveMiddle {

	public static void main(String[] args) {
		MyList<Integer> l1 = new MyList<Integer>(new Integer[]{1,2,3,4,5});
		MyList<Integer> l2 = new MyList<Integer>(new Integer[]{1,2,3});
		
		l1.print();
		removeMiddle(l1.head.next.next);
		System.out.println("Middle element deleted...");
		l1.print();
		
		l2.print();
		removeMiddle(l2.head.next);
		System.out.println("Middle element deleted...");
		l2.print();

	}
	
	/**
	 * delete the middle element
	 * @param mid
	 */
	public static void removeMiddle(Node<Integer> mid){
		if(mid == null || mid.next == null){
			return;
		}
		mid.val = mid.next.val;
		mid.next = mid.next.next;
	}

}
{% endhighlight %}

