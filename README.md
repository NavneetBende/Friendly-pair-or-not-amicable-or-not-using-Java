# Friendly-pair-or-not-amicable-or-not-using-Java

Friendly pair or not (amicable or not) using Java
Check Whether or Not the Two Numbers are a Friendly Pair in Java
Given Two integer inputs as the numbers, the objective is to check whether the ratio of the sum of the factors of the number except the number itself upon the number, of the both numbers, matches or not. Therefore, we’ll write a code to Check Whether or Not the Two Numbers are a Friendly Pair in Java Language.
Example
Input : 6 12
Output : Yes, they are a friendly pair.
friendly pair or not in java
Check Whether or Not the Two Numbers are a Friendly Pair in Java Language
Given two integer as the numbers, the objective is to check whether the ratio of the sum of the factors of a number except the number itself upon the number, for both numbers, matches or not using Java Language. To do so we’ll firstly find all the factors of the two numbers given as the input. Then we divide the sum with the numbers to get the ratio. Now we’ll compare both the ratios. For any pair of numbers to be a Friendly Pair, the ratio must match. Here are a few methods to check for Friendly Pairs using Java Language,

Method 1: Using the Range until Number
Method 2: Using the Range until Sqrt( Number )
We’ll discuss the above mentioned methods in detail in the upcoming sections. Do check the blue box mentioned below for better understanding. Check out the Java page to Find all the Factors of a Number for better understanding.

Friendly Pair
The numbers whose ( sum of divisors ) / number ratio is same are known as Friendly Pair Numbers.
Let's try and understand it better using an example

Example
Input : 6 28
Output : Yes, they are a friendly pair
Explanation : The factors of 6 and 28 except the numbers themselves are 1, 2, 3 and 1, 2, 4, 7, 14 respectively.
Now the sum of factors of both the numbers are 6 and 28 respectively. 
When we divide the sums with the numbers we get 1 and 1 respectively. 
As the ratio of both the number match, they are considered as a friendly pair.
Therefore, from the above mentioned definition and example, we'll check for friendly pairs.
Method 1: Using the Range until Number
Java Code
Run
public class Main
 {
   public static void main (String[]args)
   {

     int num1 = 30, num2 = 140;

     int sum1 = getDivisorsSum (num1);
     int sum2 = getDivisorsSum (num2);

     if (sum1 / num1 == sum2 / num2)
       System.out.println (num1 + " & " + num2 + " are friendly pairs");
     else
         System.out.println (num1 + " & " + num2 + " are not friendly pairs");
   }

   static int getDivisorsSum (int num)
   {

     int sum = 0;

     for (int i = 1; i < num; i++)
       {
 	    if (num % i == 0)
 	    sum = sum + i;
       }
     return sum;
   }
 }
Output
30 & 140 are friendly pairs
Method 2: Using the Range until Sqrt( Number )
Java Code
Run
public class Main
{
  public static void main (String[]args)
  {

    int num1 = 30, num2 = 140;

    int sum1 = getDivisorsSum (num1);
    int sum2 = getDivisorsSum (num2);

    if (sum1 / num1 == sum2 / num2)
      System.out.println (num1 + " & " + num2 + " are friendly pairs");
    else
        System.out.println (num1 + " & " + num2 + " are not friendly pairs");
  }

  static int getDivisorsSum (int n)
  {

    int sum = 0;
    
    for(int i = 1; i < Math.sqrt(n); i++) 
    { 
        if (n % i == 0) 
        { 
            // For n : (1, n) will always be pair of divisor 
            // acc to def., we must ignore adding n itself as divisor 
            // when calculating for abundant number 
            if(i == 1) 
                sum = sum + i; 

            // Example For 100 (10,10) will be one of the pair 
            // But, we should add value 10 to the sum just once 
            else if(i == n/i) 
                sum = sum + i; 

            // add both pairs as divisors 
            // For any divisor i, n/i will also be a divisor 
            else 
                sum = sum + i + n/i; 
        } 
    } 
    return sum; 
  }
}
Output
30 & 140 are friendly pairs
