# EXP NO 26: C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST.
## Aim:
To write a C program to display stack elements using linked list.

## Algorithm:
1.	Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
2.	Declare a global variable head representing the starting node of the linked list.
3.	Define a function display to print the elements of the linked list.
4.	Declare a pointer p and initialize it with the head of the linked list.
5.	Use a while loop to traverse the linked list:
6.	Print the data of the current node.
7.	Move to the next node using the next pointer.
 
## Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

struct Node* head = NULL;

void push(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = head;
    head = newNode;
}
void display() {
    struct Node* p = head;
    if (p == NULL) {
        printf("Stack is empty.\n");
        return;
    }
    printf("Stack elements are:\n");
    while (p != NULL) {
        printf("%d ", p->data);
        p = p->next;
    }
    printf("\n");
}
int main() {
    push(10);
    push(20);
    push(30);
    display();

    return 0;
}
```
## Output:
![Screenshot 2025-05-20 131726](https://github.com/user-attachments/assets/87f97da4-64de-40bf-9d94-f0d30f11dc4a)



## Result:
Thus, the program to display stack elements using linked list is verified successfully. 



# EXP.NO 27: C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING LINKED LIST.
## Aim:
To write a C program to pop an element from the given stack using liked list.

## Algorithm:
1.	Check for Empty Stack
2.	If head is equal to NULL, Print "Stack is empty."
3.	Else Proceed to the next step.
4.	Set head to point to the next node in the stack.
 
## Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

struct Node* head = NULL;

void push(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = head;
    head = newNode;
}

void pop() {
    if (head == NULL) {
        printf("Stack is empty.\n");
        return;
    }

    struct Node* temp = head;
    printf("Popped element: %d\n", temp->data);
    head = head->next;
    free(temp);
}

void display() {
    struct Node* p = head;
    if (p == NULL) {
        printf("Stack is empty.\n");
        return;
    }

    printf("Stack elements: ");
    while (p != NULL) {
        printf("%d ", p->data);
        p = p->next;
    }
    printf("\n");
}

int main() {
    push(10);
    push(20);
    push(30);
    display();

    pop();  
    display();

    pop();  
    display();

    pop(); 
    display();

    pop();  

    return 0;
}
```
## Output:
![Screenshot 2025-05-20 131935](https://github.com/user-attachments/assets/1a4d0c5b-ab21-476c-929c-01c2f6347250)




## Result:
Thus, the program to pop an element from the given stack using liked list is verified successfully.

 
# EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST.
## Aim:
To write a C program to display queue elements using linked list.
## Algorithm:
1.	Check if Queue is Empty
2.	Display Queue Elements
3.	Print the data of the current node pointed to by front
4.	Update front to point to the next node.
5.	End the display function.
 
## Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

struct Node* front = NULL;
struct Node* rear = NULL;

void enqueue(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;
    if (rear == NULL) {
        front = rear = newNode;
    } else {
        rear->next = newNode;
        rear = newNode;
    }
}

void displayQueue() {
    struct Node* temp = front;

    if (front == NULL) {
        printf("Queue is empty.\n");
        return;
    }

    printf("Queue elements: ");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    enqueue(60);
    enqueue(70);
    enqueue(80);
    enqueue(90);
    enqueue(100);
    displayQueue();  

    return 0;
}
```
## Output:
![Screenshot 2025-05-20 132141](https://github.com/user-attachments/assets/ce3762ca-c248-497e-9e52-31f3be15d3b5)


## Result:
Thus, the program to display queue elements using linked list is verified successfully.


 
# EXP NO:29 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

## Aim:
To write a C program to insert elements in queue using linked list

## Algorithm:
1.	Allocate Memory for New Node
2.	Set Data and Next Pointer
3.	Check if Queue is Empty
4.	Set both front and rear to point to the new node p.
5.	Set the next pointer of the current rear to point to the new node p.
6.	End of Enqueue Operation
 
## Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

struct Node* front = NULL;
struct Node* rear = NULL;

void enqueue(int value) {
    struct Node* p = (struct Node*)malloc(sizeof(struct Node));
    p->data = value;
    p->next = NULL;
    if (rear == NULL) {
        front = rear = p;
    } else {
        rear->next = p;
        rear = p;
    }
}

void displayQueue() {
    struct Node* temp = front;
    printf("Queue elements: ");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    int n, val, i;
    printf("Enter number of elements to insert: ");
    scanf("%d", &n);
    for (i = 0; i < n; i++) {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &val);
        enqueue(val);
    }
    displayQueue();
    return 0;
}
```
## Output:
![Screenshot 2025-05-20 132335](https://github.com/user-attachments/assets/b6ae2cc9-e872-43d9-adb8-fa7f83d0f47d)
## Result:
Thus, the program to insert elements in queue using linked list is verified successfully.



# EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.


## Aim:

The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

## Algorithm:

1.	Check if the queue is empty:
o	If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
2.	Access the front element:
o	If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).

## Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

struct Node* front = NULL;
struct Node* rear = NULL;

void enqueue(int value) {
    struct Node* p = (struct Node*)malloc(sizeof(struct Node));
    p->data = value;
    p->next = NULL;
    if (rear == NULL) {
        front = rear = p;
    } else {
        rear->next = p;
        rear = p;
    }
}

void peek() {
    if (front == NULL) {
        printf("Queue is empty.\n");
    } else {
        printf("Peek element: %d\n", front->data);
    }
}

int main() {
    int n, val, i;
    printf("Enter number of elements to insert: ");
    scanf("%d", &n);
    for (i = 0; i < n; i++) {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &val);
        enqueue(val);
    }
    peek();
    return 0;
}
```
## Output:

![Screenshot 2025-05-20 132535](https://github.com/user-attachments/assets/9bd49c1e-8df4-4bbe-b0b3-11d2cf1ae8c7)



## Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.





