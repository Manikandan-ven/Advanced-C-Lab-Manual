EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
Aim:
To write a C program to search a given element in the given linked list.

Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
Program:
```
#include <stdio.h>
#include <stdlib.h>

struct node {
    int data;
    struct node *next;
};

// Function to search an element in the linked list
int search(struct node *head, int key) {
    struct node *temp = head;
    while (temp != NULL) {
        if (temp->data == key)
            return 1;   // Key found
        temp = temp->next;
    }
    return 0;  // Key not found
}

int main() {
    int n, i, value, key;

    printf("Enter number of nodes: ");
    scanf("%d", &n);

    struct node *head = NULL, *temp, *newnode;

    // Creating the linked list
    for (i = 0; i < n; i++) {
        newnode = (struct node *)malloc(sizeof(struct node));
        printf("Enter value for node %d: ", i + 1);
        scanf("%d", &value);

        newnode->data = value;
        newnode->next = NULL;

        if (head == NULL)
            head = newnode;
        else {
            temp = head;
            while (temp->next != NULL)
                temp = temp->next;
            temp->next = newnode;
        }
    }

    printf("Enter element to search: ");
    scanf("%d", &key);

    if (search(head, key))
        printf("Element %d found in the list.\n", key);
    else
        printf("Element %d not found in the list.\n", key);

    return 0;
}

```

Output:

<img width="544" height="241" alt="image" src="https://github.com/user-attachments/assets/17013d91-d81f-4a1a-b09d-ca3429abcde1" />




Result:
Thus, the program to search a given element in the given linked list is verified successfully.


 
EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.
Aim:
To write a C program to insert a node in a linked list.
Algorithm:
1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
Program:
```
#include <stdio.h>
#include <stdlib.h>

// Structure of a node
struct node {
    char data;
    struct node *next;
};

// Function to insert a node at the end
void insert(struct node **head, char value) {
    struct node *newnode = (struct node *)malloc(sizeof(struct node));
    newnode->data = value;
    newnode->next = NULL;

    if (*head == NULL) {
        *head = newnode;
    } else {
        struct node *temp = *head;
        while (temp->next != NULL)
            temp = temp->next;
        temp->next = newnode;
    }
}

// Function to display the linked list
void display(struct node *head) {
    struct node *temp = head;
    printf("Linked List: ");
    while (temp != NULL) {
        printf("%c -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main() {
    struct node *head = NULL;
    int n, i;
    char value;

    printf("Enter number of nodes to insert: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++) {
        printf("Enter data for node %d: ", i + 1);
        scanf(" %c", &value);
        insert(&head, value);
    }

    display(head);
    return 0;
}

```

Output:

<img width="540" height="226" alt="image" src="https://github.com/user-attachments/assets/e0cb0edb-9b6d-4a04-ba2b-0df2eae7095b" />


 
Result:
Thus, the program to insert a node in a linked list is verified successfully.


 
EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST
Aim:
To write a C program to traverse a doubly linked list.

Algorithm:
1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

// Structure of a doubly linked list node
struct node {
    int data;
    struct node *prev;
    struct node *next;
};

// Function to create a new node
struct node* createNode(int value) {
    struct node* newnode = (struct node*)malloc(sizeof(struct node));
    newnode->data = value;
    newnode->prev = NULL;
    newnode->next = NULL;
    return newnode;
}

// Function to traverse the doubly linked list
void traverse(struct node *head) {
    struct node *temp = head;
    printf("Doubly Linked List: ");
    while (temp != NULL) {
        printf("%d <-> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main() {
    struct node *head = NULL, *second = NULL, *third = NULL;

    // Creating nodes
    head = createNode(10);
    second = createNode(20);
    third = createNode(30);

    // Linking nodes
    head->next = second;
    second->prev = head;
    second->next = third;
    third->prev = second;

    // Traverse the doubly linked list
    traverse(head);

    return 0;
}

```

Output:

<img width="656" height="179" alt="image" src="https://github.com/user-attachments/assets/f53d9ec8-a354-4f61-99af-96e917f9e3f7" />



Result:
Thus, the program to traverse a doubly linked list is verified successfully. 



EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST
Aim:
To write a C program to insert an element in doubly linked list

Algorithm:
1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

// Structure of a doubly linked list node
struct node {
    int data;
    struct node *prev;
    struct node *next;
};

// Function to insert at the end of the doubly linked list
void insertEnd(struct node **head, int value) {
    struct node *newNode = (struct node*)malloc(sizeof(struct node));
    newNode->data = value;
    newNode->prev = NULL;
    newNode->next = NULL;

    // If list is empty
    if (*head == NULL) {
        *head = newNode;
        return;
    }

    // Traverse to last node
    struct node *temp = *head;
    while (temp->next != NULL) {
        temp = temp->next;
    }

    // Insert at end
    temp->next = newNode;
    newNode->prev = temp;
}

// Display the doubly linked list
void display(struct node *head) {
    struct node *temp = head;
    printf("Doubly Linked List: ");
    while (temp != NULL) {
        printf("%d <-> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main() {
    struct node *head = NULL;
    int n, value, i;

    printf("Enter number of elements to insert: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++) {
        printf("Enter value for node %d: ", i + 1);
        scanf("%d", &value);
        insertEnd(&head, value);
    }

    display(head);

    return 0;
}

```

Output:

<img width="663" height="236" alt="image" src="https://github.com/user-attachments/assets/cb381541-c497-4599-89c4-27c4f9c5345a" />



Result:
Thus, the program to insert an element in doubly linked list is verified successfully.




EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST




Aim:
To write a C function that deletes a given element from a linked list.

Algorithm:
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


Program:

```
#include <stdio.h>
#include <stdlib.h>

// Structure of a node
struct node {
    int data;
    struct node *next;
};

// Function to delete a node with a given key
void deleteElement(struct node **head, int key) {
    if (*head == NULL) {
        printf("List is empty.\n");
        return;
    }

    struct node *temp = *head;

    // If the node to delete is the first node
    if (temp != NULL && temp->data == key) {
        *head = temp->next;
        free(temp);
        printf("Element %d deleted from the list.\n", key);
        return;
    }

    struct node *prev = NULL;

    // Search for the key in the list
    while (temp != NULL && temp->data != key) {
        prev = temp;
        temp = temp->next;
    }

    // If element not found
    if (temp == NULL) {
        printf("Element %d not found in the list.\n", key);
        return;
    }

    // Delete the node
    prev->next = temp->next;
    free(temp);
    printf("Element %d deleted from the list.\n", key);
}

// Function to display the linked list
void display(struct node *head) {
    struct node *temp = head;
    printf("Linked List: ");
    while (temp != NULL) {
        printf("%d -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main() {
    struct node *head = NULL, *newnode, *temp;
    int n, value, key, i;

    printf("Enter number of nodes: ");
    scanf("%d", &n);

    // Creating linked list
    for (i = 0; i < n; i++) {
        newnode = (struct node*)malloc(sizeof(struct node));
        printf("Enter value for node %d: ", i + 1);
        scanf("%d", &value);

        newnode->data = value;
        newnode->next = NULL;

        if (head == NULL)
            head = newnode;
        else {
            temp = head;
            while (temp->next != NULL)
                temp = temp->next;
            temp->next = newnode;
        }
    }

    display(head);

    printf("Enter element to delete: ");
    scanf("%d", &key);

    deleteElement(&head, key);

    display(head);

    return 0;
}

```
Output:

<img width="511" height="303" alt="image" src="https://github.com/user-attachments/assets/af30c570-3b68-4e43-a909-31fda7e223e2" />






Result:
Thus, the function that deletes a given element from a linked list is verified successfully.





