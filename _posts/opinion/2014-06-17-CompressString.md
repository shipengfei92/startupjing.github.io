---
layout: post
title:  "CC150 Problem 1.5"
categories: coding_problems
---

# Compress String


 Implement a method to perform basic string compression using the counts of repeated characters. For example, the string aabcccccaaa would become a2blc5a3. If the "compressed" string would not become smaller than the original string, your method should return the original string.





{% highlight ruby %}

import java.util.*;

public class CompressStr {
	/**
	 * ask user for input and output the compressed string
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
	    	 System.out.println("The compressed string is " + compress(userStr));
	    	 System.out.println();
	    	 System.out.println("Please enter another string (q to quit): ");
	    		
	    }
	      
	 }
	 
	 /**
	  * compress the string if needed
	  * @param s
	  * @return compressed string
	  */
	 public static String compress(String s){
		 //tempCount to count number of char
		 int tempCount = 0;
		 //pointer to traverse the string
		 int i = 0;
		 StringBuffer result = new StringBuffer();
		 
		 
		 while(i < s.length()){
			 char tempChar = s.charAt(i);	 
			 while(s.charAt(i) == tempChar){
				 i++;
				 tempCount ++;
				 
				 //if ptr exceeds the length, call for final result
				 if(i >= s.length()){
					 result.append("" + tempChar + tempCount);
					 return decideStr(result.toString(), s);
				 }
			 }
			 //append the character and its frequency
			 result.append("" + tempChar + tempCount);
			 tempCount = 0;
		 }
		 
		 return decideStr(result.toString(), s);
 
	 }
	 
	 /**
	  * return the string of shorter length
	  * @param s1
	  * @param s2
	  * @return string of shorter length
	  */
	 public static String decideStr(String s1, String s2){
		 if(s1.length() < s2.length()){
			 return s1;
		 }else{
			 return s2;
		 }
		 
	 }
}



{% endhighlight %}

