# EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
## Aim:
To write a C program to search a given element in the given linked list.

## Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
## Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    char data;
    struct Node* next;
};

int search(struct Node* head, char key) {
    struct Node* current = head;
    int position = 1;

    while (current != NULL) {
        if (current->data == key) {
            printf("Element '%c' found at position %d\n", key, position);
            return 1; 
        }
        current = current->next;
        position++;
    }

    printf("Element '%c' not found in the list.\n", key);
    return 0; 
}

struct Node* create_node(char data) {
    struct Node* new_node = (struct Node*)malloc(sizeof(struct Node));
    new_node->data = data;
    new_node->next = NULL;
    return new_node;
}

int main() {
    struct Node* head = create_node('A');
    head->next = create_node('B');
    head->next->next = create_node('C');
    head->next->next->next = create_node('D');

    printf("Linked List: ");
    struct Node* temp = head;
    while (temp != NULL) {
        printf("%c ", temp->data);
        temp = temp->next;
    }
    printf("\n");

    char key;
    printf("Enter the character to search: ");
    scanf(" %c", &key);

    search(head, key);

    while (head != NULL) {
        struct Node* temp = head;
        head = head->next;
        free(temp);
    }

    return 0;
}
```

## Output:

![Screenshot 2025-05-20 122714](https://github.com/user-attachments/assets/0bfab137-5de4-420d-b2d3-8c285bea5011)



## Result:
Thus, the program to search a given element in the given linked list is verified successfully.


 
# EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.
## Aim:
To write a C program to insert a node in a linked list.
## Algorithm:
1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
## Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    char data;
    struct Node* next;
};

void insert(struct Node** head_ref, char new_data) {
    struct Node* new_node = (struct Node*)malloc(sizeof(struct Node));
    new_node->data = new_data;
    new_node->next = NULL;

    if (*head_ref == NULL) {
        *head_ref = new_node;
        return;
    }

    struct Node* last = *head_ref;
    while (last->next != NULL) {
        last = last->next;
    }
    last->next = new_node;
}

void display(struct Node* head) {
    printf("Linked List: ");
    while (head != NULL) {
        printf("%c ", head->data);
        head = head->next;
    }
    printf("\n");
}

int main() {
    struct Node* head = NULL; 

    int n, i;
    char ch;
    printf("Enter the number of characters to insert: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++) {
        printf("Enter character %d: ", i + 1);
        scanf(" %c", &ch);
        insert(&head, ch);
    }

    display(head);

    while (head != NULL) {
        struct Node* temp = head;
        head = head->next;
        free(temp);
    }

    return 0;
}


```
## Output:

![Screenshot 2025-05-20 123444](https://github.com/user-attachments/assets/9bc4185f-d3a7-423d-94aa-ce40c5117188)

 
## Result:
Thus, the program to insert a node in a linked list is verified successfully.


 
# EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST
## Aim:
To write a C program to traverse a doubly linked list.

## Algorithm:
1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
## Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* prev;
    struct Node* next;
};

void traverse(struct Node* head) {
    struct Node* temp = head;
    printf("Linked List:\n");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

struct Node* create_node(int data) {
    struct Node* new_node = (struct Node*)malloc(sizeof(struct Node));
    new_node->data = data;
    new_node->prev = NULL;
    new_node->next = NULL;
    return new_node;
}

int main() {
    struct Node* head = create_node(10);
    struct Node* second = create_node(20);
    struct Node* third = create_node(30);
    struct Node* fourth = create_node(40);

    head->next = second;

    second->prev = head;
    second->next = third;

    third->prev = second;
    third->next = fourth;

    fourth->prev = third;

    traverse(head);

    return 0;
}
```
## Output:

![Screenshot 2025-05-20 123741](https://github.com/user-attachments/assets/7e93a0de-80f8-4a26-9dc4-1f226f584f67)


## Result:
Thus, the program to traverse a doubly linked list is verified successfully. 



# EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST
## Aim:
To write a C program to insert an element in doubly linked list

## Algorithm:
1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
## Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* prev;
    struct Node* next;
};

struct Node* insert(struct Node* head, int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->prev = NULL;
    newNode->next = NULL;

    if (head == NULL) {
        head = newNode;
        return head;
    }

    struct Node* temp = head;
    while (temp->next != NULL) {
        temp = temp->next;
    }

    temp->next = newNode;
    newNode->prev = temp;

    return head;
}

void display(struct Node* head) {
    struct Node* temp = head;
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    struct Node* head = NULL;
    int n, i, val;

    printf("Enter number of elements to insert: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++) {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &val);
        head = insert(head, val);
    }

    printf("Doubly Linked List: ");
    display(head);

    return 0;
}

```
## Output:

![Screenshot 2025-05-20 123956](https://github.com/user-attachments/assets/e566370b-f5d1-4ce5-b008-8a04d631815b)


## Result:
Thus, the program to insert an element in doubly linked list is verified successfully.




# EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST




## Aim:
To write a C function that deletes a given element from a linked list.

## Algorithm:
1.	Check if the Linked List is Empty:
o	If the head of the linked list is NULL, print a message indicating the list is empty and exit the function.
2.	Traverse the Linked List:
o	Start from the head node and iterate through the list to find the node that contains the given element (data).
3.	Handle Deletion of the First Node:
o	If the element to be deleted is found in the head node:
	Update the head of the linked list to point to the next node (i.e., head = head->next).
	Free the memory allocated to the node to be deleted.
	Exit the function.
4.	Traverse and Delete from the Middle or End:
o	If the element is not in the head node, continue traversing the list by checking each node’s next pointer.
o	When the node with the element is found, update the previous node’s next pointer to point to the next node of the node to be deleted (prev->next = current->next).
o	Free the memory allocated to the node to be deleted.
5.	Handle the Case when the Element is Not Found:
o	If the element is not found in any node, print a message indicating the element is not present in the list.
6.	End the Function.


## Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

struct Node* insert(struct Node* head, int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;

    if (head == NULL) {
        return newNode;
    }

    struct Node* temp = head;
    while (temp->next != NULL) {
        temp = temp->next;
    }
    temp->next = newNode;

    return head;
}

struct Node* delete_element(struct Node* head, int key) {
    if (head == NULL) {
        printf("List is empty.\n");
        return head;
    }

    struct Node* temp = head;

    // If the element is in the head
    if (temp->data == key) {
        head = temp->next;
        free(temp);
        return head;
    }

    struct Node* prev = NULL;
    while (temp != NULL && temp->data != key) {
        prev = temp;
        temp = temp->next;
    }

    if (temp == NULL) {
        printf("Element %d not found in the list.\n", key);
        return head;
    }

    prev->next = temp->next;
    free(temp);
    return head;
}

void display(struct Node* head) {
    struct Node* temp = head;
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    struct Node* head = NULL;
    int n, val, del_val;

    printf("Enter number of elements: ");
    scanf("%d", &n);

    for (int i = 0; i < n; i++) {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &val);
        head = insert(head, val);
    }

    printf("Original List: ");
    display(head);

    printf("Enter value to delete: ");
    scanf("%d", &del_val);

    head = delete_element(head, del_val);

    printf("List after deletion: ");
    display(head);

    return 0;
}

```
## Output:

![Screenshot 2025-05-20 124221](https://github.com/user-attachments/assets/83eb963b-9c37-41bb-80a3-5865888d024e)





## Result:
Thus, the function that deletes a given element from a linked list is verified successfully.











