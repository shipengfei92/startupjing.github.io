---
layout: post
title:  "CC150 Problem 1.4"
date:   2014-06-17
categories: blog
---

# Replace Spaces


Write a method to replace all spaces in a string with'%20'. You may assume that the string has sufficient space at the end of the string to hold the additional characters, and that you are given the "true" length of the string. (Note: if implementing in Java, please use a character array so that you can perform this operation in place.)
EXAMPLE
Input: "Mr John Smith       "
Output: "Mr%20Dohn%20Smith" 


{% highlight ruby %}

import java.util.Scanner;

public class ReplaceSpace {
	/**
	 * ask user for input and print the new string with space replaced with %20
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
	    	 System.out.println("The new string is " + replaceSpace(userStr.toCharArray()));
	    	 System.out.println();
	    	 System.out.println("Please enter another string (q to quit): ");	
	    }
	      
	 }
	
	/**
	 * replace space with %20
	 * @param arr
	 * @return string with space replaced
	 */
	public static String replaceSpace(char[] arr){
		int len = findTrueLength(arr);
		
		for(int k=0; k<=len; k++){
			
			if(arr[k] == ' '){
				int count = 0;
				int i = k;
				//count how many spots for this space
				while(arr[k] == ' '){
					count ++;
					k ++;
				}
				//shift the char array and replace space by %20
				if(count <= 2){
					shiftArrRight(arr,k,len,3-count);
					len += (3-count);
				}else if(count > 3){
					shiftArrLeft(arr, k, len, count-3);
					len -= (count-3);
				}
				replace(arr, i);			
			}
		}
		return new String(arr);
	}
	
	/**
	 * shift the char arry to right by shift spots
	 * @param arr
	 * @param i
	 * @param j
	 * @param shift
	 */
	public static void shiftArrRight(char[] arr, int i, int j, int shift){
	    while(j >= i){
	    	arr[j+shift] = arr[j];
	    	j --;
	    }
	}
	
	/**
	 * shift the char array to left by shift spots
	 * @param arr
	 * @param i
	 * @param j
	 * @param shift
	 */
	public static void shiftArrLeft(char[] arr, int i, int j, int shift){
		while(i <= j){
			arr[i-shift] = arr[i];
			arr[i] = ' ';
			i ++;
		}
	}
	
	/**
	 * replace arr[i,i+1,i+2] by %20
	 * @param arr
	 * @param i
	 */
	public static void replace(char[] arr, int i){
		arr[i] = '%';
		arr[i+1] = '2';
		arr[i+2] = '0';
	}
	
	/**
	 * find the true length of given char arr
	 * @param arr
	 * @return true length of char array
	 */
	public static int findTrueLength(char[] arr){
		int k = arr.length-1;
		while(arr[k] == ' '){
			k --;
		}
		return k;
	}
	
}


{% endhighlight %}

