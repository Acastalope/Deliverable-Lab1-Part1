# Deliverable-Lab1-Part1
package Assignment1;

import java.util.Scanner;

public class MyAssignment1 {

	public static void main(String[] args) {
		// My first statement
		
		Scanner sc = new Scanner(System.in);       //declaration of sc of scanner type
		System.out.print("Enter number 1: ");      //Print out 
		while ( !sc.hasNextInt() )      //While loop used for storing user input in sc
			sc.next();
		
		int num1 = sc.nextInt(); //variable num1 is assigned user input
		
		
		int len1 = String.valueOf(num1).length();    //assigning len1 with length of number 1
		System.out.println("Enter a second number " + len1 + " digits long.");
		
		
		while (!sc.hasNextInt()) 
			sc.next();
		
		int num2 = sc.nextInt();     //assigning num2 with second user-input
		//System.out.format("accepted number : %d \n", num2);
		
		int len2 = String.valueOf(num2).length();
		//System.out.format("length of num2 is : %d \n", len2);
		
		if(len2 != len1) {    //If the length of the two numbers are not equal, print "error"
			System.out.println("Error");
			return;
		}
		int ct = 1;                //ct stands for the number of times the loop runs
		int placevalue1 = 0;       //Initialization of placevalue1   
		int placevalue2 = 0;       //Initialization of placevalue2  
		int new_num1 = num1;  //Copy the value of num1 to new_num1
		int new_num2 = num2;  //Copy the value of num2 to new_num2
		int sum1_previous = 0;  //Variable to hold the sum of the digits of respective places
		
		while(ct <= len1) {	//Loop to repeat len1 times
			placevalue1 = new_num1%10; //Assigning of place values to placevalue1 one by one with each execution of the loop
		    new_num1 = new_num1/10;  //Set new_num1 to hold the rest of the digits of number 1
		    System.out.format("digit number %d of %d is : %d \n", ct, num1, placevalue1);
		    
		    placevalue2 = new_num2%10;  //Assigning of place values to placevalue2 one by one with each execution of the loop
		    new_num2 = new_num2/10; //Set new_num2 to hold the rest of the digits of number 2
		    System.out.format("digit number %d of %d is : %d \n", ct, num2, placevalue2);
		    if(ct == 1) {  //Add up the value of the ones place  
		    	sum1_previous = placevalue1 + placevalue2;
		    	System.out.println("Sum of the digits at this stage is : " + sum1_previous);
		    }
		    	
		    else if(sum1_previous == placevalue1 + placevalue2 ) { //If the previous sum is equal to the current sum, then the check will continue
		    	ct = ct + 1;  //Loop will continue according to the number of digits in the number
		    	System.out.println("Sum of the digits at this stage is : " + sum1_previous);
		    	System.out.println("True");
		    	continue; //Will continue back to run the loop after condition check if true
		    }
		    else  //Will execute following if conditions are not met
		    {
		    	System.out.println("Sum of the digits at this stage is : " + (placevalue1 + placevalue2));
		    	System.out.println("Sum of the digits at the previous stage was : " + sum1_previous);
		    	System.out.println("False");
		    	break;
		    }
		    	
		    
		    ct = ct + 1;
		}
		
	}

}
