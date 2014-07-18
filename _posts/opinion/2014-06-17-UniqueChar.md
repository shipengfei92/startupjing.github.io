---
layout: post
title:  "CC150 Problem 1.1"
date:   2014-06-17
categories: blog
---

# Check Unique Character in a String


Implement an algorithm to determine if a string has all unique characters. 
What if you cannot use additional data structures?

{% highlight java %}

import java.util.*;

public class UniqueChar {
	
	/**
	 * ask for user input and check if it has unique character
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
    		System.out.println(userStr + "has unique char? " + hasUniqueChar(userStr));
    		System.out.println();
    		System.out.println("Please enter another string (q to quit): ");
    		
    	}	
    	
    }
 
    /**
     * check if the given string has unique character
     * @param s
     * @return true if string has unique character and false otherwise
     */
    public static boolean hasUniqueChar(String s){
        //some special checks
        if(s == null){
            throw new IllegalArgumentException();
        }else if(s.length() == 0){
            return true;
        }else if(s.length() > 256){
            return false;
        }
        
    	//boolean array of length 256
    	boolean[] arr = new boolean[256];
    	
    	//traverse the string and find ASCII value for each char
    	for(int i=0; i<s.length(); i++){
    		int val = s.charAt(i);
    		//check if duplicate exists
    		if(arr[val]){
    			return false;
    		}
    		arr[val] = true; 		
    	}
    	return true;  	
    }
}


{% endhighlight %}

