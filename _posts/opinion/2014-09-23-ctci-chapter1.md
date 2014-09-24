---
layout: post
title: CTCI chapter 1
description: What I learned from chapter 1
categories: opinion
---

## Beginning
I have completed CTCI chapter 1 problems today.
This chapter is about arrays and strings.

## Solutions
Please come to my [Github repo][2] and see my solutions

## What I learned

### Some useful structure

#### Hash Table
No need to say more ... but

* Implementation: 

Using array: collision may occur
Using linkedlist: get the object with key first and then search corresponding linkedlist
Using BST: O(logn) lookup time for balanced tree, less space

* Usage

`HashMap<Object, Object> map = new HashMap<Object, Object>()`

`map.put(key,val)`

`more ...`

#### ArrayList
No need to say more...

#### StringBuffer

* Why

Each string concatenation makes a new copy every time, O(n^2) time.

StringBuffer is a better choice

* Usage
`StringBuffer buff = new StringBuffer()`

`buff.append(str)`

`String s = buff.toString`

### Something to consider before solving problems

* What kind of characters does the string contain? ASCII? or sth else?
* Use comparison of length, check null or invalid string to get immediate result
* Case sensitive? Whitespace significant?

### Problems

* For char problems, think about ASCII table and using of int[] or boolean[] of length 256
* To check unique char, consider bitwise operation, flags and masks 
* Sometimes(check permutation) it might be useful to sort the strings first and then compare
* Traversing and processing backwards might be a better choice because it might not corrupt your chars
* Matrix rotation: rotate layer by layer, or think about flip
* String rotation: s1=xy, s2=yx, if s2 is substring of s1s1, then s2 is rotation of s1

## Ending
I will keep updating if more useful tricks are found.
Begin chapter 2 tomorrow!


[startupjing]:    http://startupjing.github.io  "startupjing"
[1]:    {{ page.url}}  ({{ page.title }})
[2]: https://github.com/startupjing/cc150/tree/master/chap1




