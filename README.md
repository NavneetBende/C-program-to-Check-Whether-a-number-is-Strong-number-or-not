# C-program-to-Check-Whether-a-number-is-Strong-number-or-not

Strong number in C
In this program we will find whether a number is strong number in C programming. A Strong Number is a number whose sum of factorial digits is equal to the number itself.

Ex:- number is 145

1! + 4! + 5! = 145 

So it is a strong number.
c program to check strong number or not
Methods discussed
Method 1 iterative way of calculation of factorial
Method 2 recursive way of calculation of factorial
Strong Number in C
Method 1
For input num

Fetch individual digits of the number
Calculate factorial of each individual digit and add them
If sum == num then its strong
Else its not strong number
C Program:-
Run
#include <stdio.h>

// function to calculate factorial
int getFactorial(int n){
    int fact = 1;
    
    for(int i = 1; i <= n; i++)
            fact = fact * i;
    
    return fact;
}

int checkStrong(int num){
    
    int digit, sum = 0;
    int temp = num;
    
    // calculate 1! + 4! + 5!
    while(temp!=0){
        digit = temp % 10;
        
        sum = sum + getFactorial(digit);
        temp /= 10;
    }
    
    // returns 1 if both equal else 0
    return sum == num;
    
}
int main ()
{
    int num = 145;
    
    if(checkStrong(num))
        printf("%d is Strong Number", num);
    else
        printf("%d is Not Strong Number", num);

}
// Time complexity: O(N^2)
// Space complexity: O(1)
Output:-
145 is Strong Number
While loop in C
Related Pages
Factor of a number

Finding Prime Factors of a number

Strong number

Perfect number

Perfect Square

Automorphic number

Method 2
In this method, we will use a recursive way to calculate the factorial number.

For input num

Fetch individual digits of the number
Calculate factorial (using Recursion) of each individual digit and add them 
If sum == num then its strong
Else its not strong number
C Program:-
Run
#include <stdio.h>

// function to calculate factorial
int getFactorial(int num)
{
    if(num == 0)
        return 1;
        
    return num * getFactorial(num-1);
}

int checkStrong(int num){
    
    int digit, sum = 0;
    int temp = num;
    
    // calculate 1! + 4! + 5!
    while(temp!=0){
        digit = temp % 10;
        
        sum = sum + getFactorial(digit);
        temp /= 10;
    }
    
    // returns 1 if both equal else 0
    return sum == num;
    
}
int main ()
{
    int num = 145;
    
    if(checkStrong(num))
        printf("%d is Strong Number", num);
    else
        printf("%d is Not Strong Number", num);

}
// Time complexity: O(N^2)
// Space complexity: O(1)
// Auxialiary Space complexity: O(N) bcz of function call stack
Output:-
145 is Strong Number
