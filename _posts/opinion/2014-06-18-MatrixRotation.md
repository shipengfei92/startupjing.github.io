---
layout: post
title:  "CC150 Problem 1.6"
date:   2014-06-18
categories: coding_problems
---

# Matrix Rotation


Given an image represented by an NxN matrix, where each pixel in the image is 4 bytes, write a method to rotate the image by 90 degrees. Can you do this in place?





{% highlight ruby %}

import java.util.*;

public class MatrixRotation {
    /**
     * user enters a matrix and program prints the rotated matrix(counter-clockwise by 90 degree)
     * @param args
     */
	public static void main(String[] args) {
		Scanner input = new Scanner(System.in);
	
		while(true){
		   System.out.println("Please enter the dimenstion of your matrix: ");
		   int n = input.nextInt();
		   int[][] matr = new int[n][n];
		   System.out.println("Please enter the matrix by rows: ");
		   
		   for(int i=0; i<n; i++){
			   for(int j=0; j<n; j++){
				  matr[i][j] = input.nextInt();
			   }
	       }
		   
		   rotateMatrix(matr, n);
		   System.out.println("The rotated matrix is: ");
		   printMatrix(matr, n);
		   
		   System.out.print("continue?(y/n): ");
		   if(input.next().equals("n")){
			     System.exit(0);
		   }
	
		}

	}
	
	/**
	 * rotate the matrix
	 * @param matr
	 * @param n
	 */
	public static void rotateMatrix(int[][] matr, int n){
		transpose(matr, n);
		horizFlip(matr, n);
	}
	
	/**
	 * transpose the matrix
	 * @param matr
	 * @param n
	 */
	public static void transpose(int[][] matr, int n){
		for(int i=0; i<n-1; i++){
			for(int j=i+1; j<n; j++){
				int temp = matr[i][j];
				matr[i][j] = matr[j][i];
				matr[j][i] = temp;
			}
		}
	}
	
	/**
	 * flip the matrix horizontally
	 * @param matr
	 * @param n
	 */
	public static void horizFlip(int[][] matr, int n){
		for(int i=0; i<=n/2-1; i++){
			int[] temp = matr[i];
			matr[i] = matr[n-1-i];
			matr[n-1-i] = temp;
		}
	
	}
	
	/**
	 * print the matrix
	 * @param matr
	 * @param n
	 */
	public static void printMatrix(int[][] matr, int n){
		for(int i=0; i<n; i++){
			for(int j=0; j<n; j++){
				System.out.printf("%-5d", matr[i][j]);
			}
			System.out.println();
		}
	}

}


{% endhighlight %}

