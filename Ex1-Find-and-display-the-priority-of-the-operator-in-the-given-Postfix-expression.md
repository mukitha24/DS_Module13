# EX.NO. 1(A) Display operator precedence in the infix expression.
## DATE:
## AIM:
To write a C program to find and display the priority of the operator in the given Postfix expression

## Algorithm
1.Start and declare the input expression as a string (e.g., "A*B+C"), and define a function to return the priority of each operator. 
2.Loop through each character of the expression using a for loop. 
3.Check if the current character is an operator (+, -, *, /, %, ^, &, |). 
4.Call the priority() function for that operator and get its corresponding priority level.  
5.Display the operator along with a message indicating its priority level.   

## Program:
```
/*
Program to find and display the priority of the operator in the given Postfix expression
Developed by: MUKITHA V M
RegisterNumber: 212223040119
*/
```
```
#include <stdio.h>
#include<string.h>

    int priority(char x)
{
   if(x=='&' || x=='|')
        return 1;
    if(x=='+' || x=='-')
        return 2;
    if(x=='*'|| x=='/' || x=='%')
        return 3;
    if(x=='^')
        return 4;
  
  return 0;
}
int main()
{
   int i,j;
   char ch[100]="(A*B)^C+(D%H)/F&G";
   for(i=0;i<strlen(ch);i++)
   {
       if(ch[i]=='+'|| ch[i]=='-' || ch[i]=='*' || ch[i]=='%' || ch[i]=='/' || ch[i]=='^' || ch[i]=='&' || ch[i]=='|')
       {
           j=priority(ch[i]);
           switch(j)
           {
               case 1:
             printf("%c  ----> ",ch[i]);
           printf("Lowest Priority\n");
             break;
            case 2:
             printf("%c  ----> ",ch[i]);
           printf("Second Lowest Priority\n");
             break;
            case 3:
             printf("%c  ----> ",ch[i]);
           printf("Second Highest Priority\n"); 
             break;
            case 4:
             printf("%c  ----> ",ch[i]);
           printf("Highest Priority\n");
             break;
           }
        }
  
   
}
}
```

## Output:
![Screenshot 2025-04-26 153127](https://github.com/user-attachments/assets/4b5262de-225c-42fa-bf57-5f6bc607972c)

## Result:
Thus the C program to find and display the priority of the operator in the given Postfix expression is implemented successfully
