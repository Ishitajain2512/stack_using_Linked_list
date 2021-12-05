# stack_using_Linked_list
Here, Stack is implemented using Linked List

#include <stdio.h> 

#include <stdlib.h> 

void push(); 

void pop(); 

void show(); 

struct node 

{ 

int info; 

struct node *next; 

}*start; 



void main () 

{ 

int ch=0; 

while(ch != 4) 

{ 

printf("\n1.Push\n2.Pop\n3.Show\n4.Exit"); 

printf("\nEnter your choice : "); 

scanf("%d",&ch); 

switch(ch) 

{ 

case 1: push(); 

break; 

case 2: pop();

break;

case 3: show();

break;

case 4: printf("Exiting...."); 


break;
 default:printf("Please Enter valid choice "); 

} 

}

} 



void push () 

{ 

int x; 

struct node *ptr = (struct node*)malloc(sizeof(struct node)); 

if(ptr == NULL) 

printf("Unable to push the element in stack\n"); 

else 

{ 

printf("Enter the value : "); 

scanf("%d",&x); 

if(start==NULL) 

{ 

ptr->info = x; 

ptr -> next = NULL; 

start=ptr; 

} 


else 

{ 

ptr->info = x; 

ptr->next = start; 

start=ptr; 

} 

printf("Item pushed\n"); 

} 

} 



void pop() 

{ 

int item; 

struct node *ptr; 

if (start == NULL) 

{ 

printf("Underflow\n"); 

} 

else 

{ 

item = start->info; 

ptr = start; 

start = start->next; 

free(ptr); 

printf("Item popped is %d\n",item); 

} 

} 

void show() 

{ 

int i; 

struct node *ptr; 


ptr=start; 

if(ptr == NULL) 

{ 

printf("Stack is empty\n"); 

} 

else 

{ 

printf("Stack\n"); 

while(ptr!=NULL) 

{ 

printf("%d\n",ptr->info); 

ptr = ptr->next; 

} 

} 

}
