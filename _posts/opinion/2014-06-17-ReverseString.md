---
layout: post
title:  "CC150 Problem 1.2"
date:   2014-06-17
categories: coding_problems
---

# Reverse a String

Implement a function void reverse(char* str) in C or C++ which reverses a null-terminated string.


{% highlight ruby %}

import java.util.Scanner;

public class ReverseStr {
	
	/**
	 * ask for user input and reverse the input string
	 * @param args
	 */
    public static void main(String[] args){
    	Scanner input = new Scanner(System.in);
    	System.out.println("Please enter a string (q to quit): ");
    	
    	while(input.hasNextLine()){
    		String userStr = input.nextLine();
    		if(userStr.equals("q")){
    			System.out.println("quit...");
    			System.exit(0);
    		}
    		System.out.println("The reversed string is " + reverse(userStr));
    		System.out.println();
    		System.out.println("Please enter another string (q to quit): ");
    		
    	}
    }
    
    /**
     * reverse the given string
     * @param s
     * @return reversed string
     */
    public static String reverse(String s){
    	StringBuffer result = new StringBuffer();
    	
    	for(int i=s.length()-1; i>=0; i--){
    		result.append(s.charAt(i));
    	}
    	
    	return result.toString();
    }
}

{% endhighlight %}

