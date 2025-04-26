# Ex2 Conversion of the infix expression into postfix expression
## DATE:26-04-25
## AIM:
To write a C program to convert the infix expression into postfix form using stack by following the operator precedence and associative rule.

## Algorithm
1.Start by scanning the infix expression from left to right and initialize an empty stack to hold operators.
2.If the current character is an operand (alphabet or number), directly add it to the postfix output. 
3.If it's an opening parenthesis (, push it to the stack.
If it's a closing parenthesis ), pop and output from the stack until an opening parenthesis is found. 
4.If it's an operator (+, -, *, /, ^, &, |, %), pop from the stack to the output until you find an operator of lower priority, then push the current operator onto the stack.  
5.At the end, pop and print all remaining operators from the stack to complete the postfix expression.  

## Program:
```
/*
Program to convert the infix expression into postfix expression
Developed by: MUKITHA V M
RegisterNumber: 212223040119 
*/
```
```
#include<stdio.h>
#include<ctype.h>

char stack[100];
int top = -1;

void push(char x)
{
    stack[++top]=x;
   
}

char pop()
{
    if (top==-1){
        return -1;
    }
    else{
        return stack[top--];
    }
}
int priority(char x)
{
    if (x=='(')
        return 0;
    if (x=='&' || x=='|')
        return 1;
    if (x=='+' || x=='-')
        return 2;
    if (x=='*' || x=='/' || x=='%')
        return 3;
    if (x=='^')
        return 4;
    return 0;
}
char IntoPost(char *exp)
{
    char *e,x;
    e=exp;
    
    while(*e!='\0')
    {
        if(isalnum(*e))
            printf("%c ",*e);
        else if(*e=='(')
            push(*e);
        else if(*e==')')
        {
            while((x=pop())!='(')
                printf("%c ",x);
        }
        else
        {
            while(priority(stack[top])>=priority(*e))
                printf("%c ",pop());
            push(*e);
        }
        e++;
    }
    
    while(top != -1)
    {
       printf("%c ",pop());
    }return 0;
}


int main()
{
    char exp[100]="a+(b|c-(d/e^f)*g)&h";
    IntoPost(exp);
    return 1;
}
```

## Output:
![Screenshot (24)](https://github.com/user-attachments/assets/0f15fe22-3e69-4288-b5bb-58b8cdc43420)



## Result:
Thus, the C program to convert the infix expression into postfix form using stack by following the operator precedence and associative rule is implemented successfully.
