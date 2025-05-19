# EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

## Aim:
To write a C program to display stack elements using an array.
## Algorithm:
1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Function
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
## Program:

```
#include <stdio.h>
#define SIZE 5

int stack[SIZE];
int top = -1;

void display() {
    if (top == -1) {
        printf("Stack is empty.\n");
    } else {
        printf("Stack elements: ");
        for (int i = 0; i <= top; i++) {
            printf("%d ", stack[i]);
        }
        printf("\n");
    }
}

int main() {
    int n, value;

    scanf("%d", &n);

    for (int i = 0; i < n; i++) {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &value);
        stack[++top] = value;
    }

    display();

    return 0;
}

```

## Output:

![Screenshot 2025-05-19 191413](https://github.com/user-attachments/assets/7cb84d50-8aa0-4f22-ad2b-f41b560f978b)



## Result:
Thus, the program to display stack elements using an array is verified successfully.
 

# EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.
## Aim:
To create a C program to push the given element in to a stack using array.
## Algorithm:
1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
## Program:

```
#include <stdio.h>

#define MAX 10  

float stack[MAX];
int top = -1;    

void push(float element) {
    if (top == MAX - 1) {
        printf("Stack Overflow! Cannot push %.2f\n", element);
    } else {
        top++;
        stack[top] = element;
        printf("Pushed element %.2f into stack.\n", element);
    }
}

int main() {
    int n, i;
    float element;

    printf("Enter number of elements to push: ");
    scanf("%d", &n);

    for(i = 0; i < n; i++) {
        printf("Enter element %d: ", i + 1);
        scanf("%f", &element);
        push(element);
    }

    if(top >= 0) {
        printf("\nStack elements are:\n");
        for(i = top; i >= 0; i--) {
            printf("%.2f\n", stack[i]);
        }
    } else {
        printf("Stack is empty.\n");
    }

    return 0;
}


```
## Output:

![Screenshot 2025-05-19 192732](https://github.com/user-attachments/assets/817c417d-7eab-4981-9d82-92ec59e3c714)




## Result:
Thus, the program to push the given element in to a stack using array is verified successfully


 
# EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.
## Aim:
To write a C program to display queue elements using array

## Algorithm:
1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
## Program:

```
#include <stdio.h>

#define MAX 10  

int queue[MAX];
int front = -1, rear = -1;

void display() {
    if (front == -1 || front > rear) {
        printf("Queue is empty.\n");
    } else {
        printf("Queue elements are:\n");
        for (int i = front; i <= rear; i++) {
            printf("%d ", queue[i]);
        }
        printf("\n");
    }
}

void enqueue(int element) {
    if (rear == MAX - 1) {
        printf("Queue Overflow! Cannot insert %d\n", element);
    } else {
        if (front == -1) {
            front = 0; 
        }
        rear++;
        queue[rear] = element;
    }
}

int main() {
    int n, element;

    printf("Enter number of elements to insert in queue: ");
    scanf("%d", &n);

    for (int i = 0; i < n; i++) {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &element);
        enqueue(element);
    }

    display();

    return 0;
}


```
## Output:

![image](https://github.com/user-attachments/assets/1630beca-86c9-4714-9faf-41b1ae9347fa)


## Result:
Thus, the program to display queue elements using array is verified successfully.


 
# EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.
## Aim:
To write a C program to insert elements in queue using array.

## Algorithm:
1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

## Program:

```
#include <stdio.h>

#define MAX 10  
float queue[MAX];
int front = -1, rear = -1;

void enqueue(float element) {
    if (rear == MAX - 1) {
        printf("Queue Overflow! Cannot insert %.2f\n", element);
    } else {
        if (front == -1) {
            front = 0;  
        }
        rear++;
        queue[rear] = element;
        printf("Inserted %.2f into queue.\n", element);
    }
}

int main() {
    int n;
    float element;

    printf("Enter number of elements to insert in queue: ");
    scanf("%d", &n);

    for (int i = 0; i < n; i++) {
        printf("Enter float element %d: ", i + 1);
        scanf("%f", &element);
        enqueue(element);
    }

    if (front == -1 || front > rear) {
        printf("Queue is empty.\n");
    } else {
        printf("\nQueue elements are:\n");
        for (int i = front; i <= rear; i++) {
            printf("%.2f ", queue[i]);
        }
        printf("\n");
    }

    return 0;
}


```
## Output:

![Screenshot 2025-05-19 193320](https://github.com/user-attachments/assets/1aa09f7f-df88-48cb-8841-e03f056f5811)

## Result:
Thus, the program to insert elements in queue using array is verified successfully.



 
# EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY



## Aim:

To create a function in C that deletes an element from a queue implemented using an array.

## Algorithm:

1.	Check if the Queue is Empty
o	If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
2.	Delete the Front Element
o	If the queue is not empty, the element at the front index is deleted.
o	Increment the front pointer by 1 to remove the element and point to the next element in the queue.
3.	Check if the Queue Becomes Empty After Deletion:
o	After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
4.	End the Function.



## Program:

```
#include <stdio.h>

#define MAX 10  

int queue[MAX];
int front = -1, rear = -1;

void dequeue() {
    if (front == -1 || front > rear) {
        printf("Queue is empty. Nothing to delete.\n");
    } else {
        printf("Deleted element: %d\n", queue[front]);
        front++;

        // If the queue becomes empty after deletion
        if (front > rear) {
            front = rear = -1;
        }
    }
}

void enqueue(int element) {
    if (rear == MAX - 1) {
        printf("Queue Overflow! Cannot insert %d\n", element);
    } else {
        if (front == -1) {
            front = 0;
        }
        rear++;
        queue[rear] = element;
        printf("Inserted %d into queue.\n", element);
    }
}

void display() {
    if (front == -1 || front > rear) {
        printf("Queue is empty.\n");
    } else {
        printf("Queue elements are: ");
        for (int i = front; i <= rear; i++) {
            printf("%d ", queue[i]);
        }
        printf("\n");
    }
}

int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);
    display();

    dequeue();
    display();

    dequeue();
    dequeue();
    dequeue(); 
    display();

    return 0;
}

```
## Output:

![Screenshot 2025-05-19 193715](https://github.com/user-attachments/assets/5e0de10d-b1ed-48da-8257-fcef70d455eb)


## Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
