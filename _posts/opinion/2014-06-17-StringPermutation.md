---
layout: post
title:  "CC150 Problem 1.3"
date:   2014-06-17
categories: blog
---

# String Permutation


Given two strings, write a method to decide if one is a permutation of the other. 




{% highlight ruby %}
import java.util.Scanner;

public class StrPermutation {
	
	/**
	 * ask user for two strings and decide if they are permutation of each other
	 * @param args
	 */
    public static void main(String[] args){
    	Scanner input = new Scanner(System.in);
    	System.out.println("Please enter two strings on sepaerate lines(q to quit): ");
    	
    	while(input.hasNextLine()){
    		String s1 = input.nextLine();
    		
    		if(s1.equals("q")){
    			System.out.println("quit...");
    			System.exit(0);
    		}
    		
    		String s2 = input.nextLine();
    		
    		System.out.println("Permutation of another? " + checkPermu(s1, s2));
    		System.out.println();
    		System.out.println("Please enter another two strings (q to quit): ");
    		
    	}
    	
    }
    
    
    /**
     * decide if two strings are permutations of each other
     * @param s1
     * @param s2
     * @return true if permutation of each other and false otherwise
     */
    public static boolean checkPermu(String s1, String s2){
    	//check the length first
    	if(s1.length() != s2.length()){
    		return false;
    	}
    	//create character counter array
    	int[] arr1 = charCount(s1);
    	int[] arr2 = charCount(s2);
    	//check if counter for character mismatches
    	for(int i=0; i<256; i++){
    		if(arr1[i] != arr2[i]){
    			return false;
    		}
    	}
    	return true;
    }
    
    
    /**
     * create character counter array for a given string
     * @param s
     * @return char counter array
     */
    public static int[] charCount(String s){
    	int[] arr = new int[256];
    	for(int i=0; i<s.length(); i++){
    		arr[(int) s.charAt(i)] ++;
    	}
    	return arr;
    }
}



{% endhighlight %}

