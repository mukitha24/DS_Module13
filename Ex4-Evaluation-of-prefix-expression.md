# Ex4 Evaluation of prefix expression
## DATE:26-04-25
## AIM:
To write a C function to evaluate the given prefix expression using stack and print the output of the given prefix expression from the stack inside the function . 

## Algorithm
1.Start with an empty stack.
2.Read the expression from right to left.
3.If the character is an operator (like * or -):
    Pop two values from the stack.
    Perform the operation (e.g., multiply or subtract).
    Push the result back onto the stack.
4.If the character is a number (operand):
    Convert the character to an integer.
    Push the number onto the stack.
5.After processing the entire expression, the final result will be the only value left in the stack. Pop it and print it.
## Program:
```
/*
Program to evaluate the given prefix expression
Developed by:MUKITHA V M 
RegisterNumber:212223040119  
*/
```
```
#include<stdio.h>
#include<string.h>
#include<ctype.h>

int s[50];
int top=0;

void push(int ch)
{
	top++;
	s[top]=ch;
}

int pop()
{
	int ch;
	ch=s[top];
	top=top-1;
	return(ch);
}

void evalprefix(char p[50])
{
    int a,b,c,i;
    for(i=strlen(p)-1;i>=0;i--)
    {
        if(p[i]=='*')
        {
            c=pop()*pop();
            push(c);
        }
        else if(p[i]=='-')
        {
            a=pop();
            b=pop();
            c=a-b;
            push(c);
        }
        else
        {
            push(p[i]-48);
        }
    }
    printf("%d",pop());
    
    
}
```

## Output:
![Screenshot (25)](https://github.com/user-attachments/assets/4848ea59-ee6e-4c2b-ba20-885922e96e37)

## Result:
Thus, the C program to evaluate the prefix expression using stack and print the output of the given prefix expression from the stack inside the function is implemented successfully.
