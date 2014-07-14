---
layout: post
title: Post Format Test
description: this post is simply used for test
categories: blog
---

## This is a header 

### This is a sub-topic

Try the following links:

* you can have some listings here
* try [baidu][2] and what do you see
* ry [yahoo][3] and what do you see



### This is another sub-topic

Please see the following **java code**

Note that some text are **highlighted**

{% highlight java %}
public static void main(String[] args){
	Scanner input = new Scanner(System.in);
	System.out.println("Please enter a string (q to quit): ");  	
	System.out.println("The compressed string is " + compress(userStr));
	System.out.println();
	System.out.println("Please enter another string (q to quit): ");
}
{% endhighlight %}


You can make texts into fill-in form, such as `aaa` and `bbb`


> You can quote something in this form
>
> This is the second line of your quote



### This is the last topic

Please see some `pics` in the **following order**

* Here is a list for some pics

* photo one

![test1](/images/test/test1.PNG)

* photo two

![test2](/images/test/test2.jpeg)


## Ending
I have **nothing** more to say


[startupjing]:    http://startupjing.github.io  "startupjing"
[1]:    {{ page.url}}  ({{ page.title }})
[2]: http://www.baidu.com
[3]: https://www.yahoo.com


