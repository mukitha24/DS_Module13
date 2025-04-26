# EX3 Implementation of Tower of Hanoi
## DATE:
## AIM:
To write a C program to implement Tower of Hanoi

## Algorithm
1. Start with n disks on the source peg (say A), and identify three pegs.
2. Move (n−1) disks from the source peg A to the auxiliary peg C, using destination peg B.
3. Move the largest disk (disk n) from source peg A to destination peg B.
4. Move the (n−1) disks from auxiliary peg C to destination peg B, using source peg A. 
5. Repeat steps recursively for each sub-problem until n = 1, which is the base case.  

## Program:
```
/*
Program to implement Tower of Hanoi
Developed by:MUKITHA V M 
RegisterNumber: 212223040119
*/
```
```
#include<stdio.h>
void TOH(int n,char x,char y,char z)
{
  if(n>0)
  {
      TOH(n-1,x,z,y);
      printf("%c to %c",x,y);
      printf("\n");
      TOH(n-1,z,y,x);
  }
}
int main()
{
    int n=3;
    TOH(n,'A','B','C');
    return 0;
}
```
## Output:
![Screenshot (22)](https://github.com/user-attachments/assets/e49ab352-8c84-4118-b776-8dd25d9be2a2)



## Result:
Thus, the C program to implement Tower of Hanoi using recursion is implemented successfully.
