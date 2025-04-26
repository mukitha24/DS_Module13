# EX.NO.1(D) Evaluation of prefix expression
## DATE:24-02-25
## AIM:
To write a C function to evaluate the given prefix expression using stack and print the output of the given prefix expression from the stack inside the function . 

## Algorithm
1. Start the program.
2. Initialize a stack and set the top index to -1.
3. Define the push() and pop() functions to add and remove elements from the stack.
4. Define the priority() function to assign priorities to operators.
5. Traverse the expression in the IntoPost() function, handling operands, parentheses, and
operators.
6. After processing the expression, pop and print any remaining operators from the stack.
7. End.
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
