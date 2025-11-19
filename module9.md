

EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

Aim:
To write a C program to display stack elements using an array.
Algorithm:
1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Function
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
Program:
```
#include <stdio.h>
#define MAX 100

int stack[MAX];
int top = -1;

// Function to push an element onto the stack
void push(int value) {
    if(top == MAX - 1) {
        printf("Stack Overflow!\n");
    } else {
        top++;
        stack[top] = value;
    }
}

// Function to pop an element from the stack
int pop() {
    if(top == -1) {
        printf("Stack Underflow!\n");
        return -1;
    } else {
        int value = stack[top];
        top--;
        return value;
    }
}

// Function to display stack elements
void display() {
    if(top == -1) {
        printf("Stack is empty.\n");
    } else {
        printf("Stack elements are: ");
        for(int i = top; i >= 0; i--) {
            printf("%d ", stack[i]);
        }
        printf("\n");
    }
}

int main() {
    // Step 5 & 6: Push some elements
    push(10);
    push(20);
    push(30);

    // Display stack
    display();

    // Pop an element and display stack again
    pop();
    display();

    return 0;
}
```

Output:

<img width="485" height="202" alt="image" src="https://github.com/user-attachments/assets/06e5b6a3-1e4a-4561-888e-b73519f5ed94" />



Result:
Thus, the program to display stack elements using an array is verified successfully.
 

EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.
Aim:
To create a C program to push the given element in to a stack using array.
Algorithm:
1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
Program:
```
#include <stdio.h>
#define MAX 100

float stack[MAX];
int top = -1;

// Function to push an element onto the stack
void push(float value) {
    if(top == MAX - 1) {
        printf("Stack Overflow! Cannot push %.2f\n", value);
    } else {
        top++;
        stack[top] = value;
        printf("%.2f pushed onto the stack.\n", value);
    }
}

// Function to display stack elements
void display() {
    if(top == -1) {
        printf("Stack is empty.\n");
    } else {
        printf("Stack elements are: ");
        for(int i = top; i >= 0; i--) {
            printf("%.2f ", stack[i]);
        }
        printf("\n");
    }
}

int main() {
    int n;
    float element;

    printf("Enter the number of elements to push: ");
    scanf("%d", &n);

    for(int i = 0; i < n; i++) {
        printf("Enter element %d: ", i+1);
        scanf("%f", &element);
        push(element);
    }

    // Display stack after pushing elements
    display();

    return 0;
}
```

Output:

<img width="617" height="472" alt="image" src="https://github.com/user-attachments/assets/1f07e5a2-1bf2-41a8-9e23-93575ee517e3" />





Result:
Thus, the program to push the given element in to a stack using array is verified successfully


 
EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.
Aim:
To write a C program to display queue elements using array

Algorithm:
1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
Program:
```
#include <stdio.h>
#define MAX 5  // Maximum size of the queue

int queue[MAX];
int front = -1;
int rear = -1;

// Function to display the queue elements
void display() {
    if (front == -1 || front > rear) {
        printf("Queue is empty.\n");
        return;
    }

    printf("Queue elements are: ");
    for (int i = front; i <= rear; i++) {
        printf("%d ", queue[i]);
    }
    printf("\n");
}

// Function to insert element into the queue
void enqueue(int element) {
    if (rear == MAX - 1) {
        printf("Queue overflow!\n");
    } else {
        if (front == -1) front = 0;
        rear++;
        queue[rear] = element;
        printf("%d inserted into queue.\n", element);
    }
}

// Function to remove element from the queue
void dequeue() {
    if (front == -1 || front > rear) {
        printf("Queue underflow!\n");
    } else {
        printf("%d removed from queue.\n", queue[front]);
        front++;
    }
}

int main() {
    // Sample queue operations
    enqueue(10);
    enqueue(20);
    enqueue(30);
    enqueue(40);
    enqueue(50);

    display();  // Display all elements

    dequeue();
    dequeue();

    display();  // Display elements after deletion

    return 0;
}
```
Output:

<img width="579" height="365" alt="image" src="https://github.com/user-attachments/assets/c6a5c9c7-0eda-4d59-adb6-a71438cf836a" />



Result:
Thus, the program to display queue elements using array is verified successfully.


 
EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.
Aim:
To write a C program to insert elements in queue using array.

Algorithm:
1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

Program:
```
#include <stdio.h>
#define MAX 5  // Maximum size of the queue

float queue[MAX];
int front = -1;
int rear = -1;

// Function to insert element into the queue
void enqueue(float element) {
    if (rear == MAX - 1) {
        printf("Queue overflow! Cannot insert %.2f\n", element);
    } else {
        if (front == -1) front = 0;
        rear++;
        queue[rear] = element;
        printf("%.2f inserted into queue.\n", element);
    }
}

// Function to display queue elements
void display() {
    if (front == -1 || front > rear) {
        printf("Queue is empty.\n");
        return;
    }

    printf("Queue elements are: ");
    for (int i = front; i <= rear; i++) {
        printf("%.2f ", queue[i]);
    }
    printf("\n");
}

int main() {
    // Insert elements into the queue
    enqueue(10.5);
    enqueue(20.75);
    enqueue(30.0);
    enqueue(40.25);
    enqueue(50.5);

    display();  // Display the queue elements

    return 0;
}
```

Output:

<img width="610" height="266" alt="image" src="https://github.com/user-attachments/assets/5fcb800c-f945-469b-850b-ffaa3f6cd86f" />

Result:
Thus, the program to insert elements in queue using array is verified successfully.



 
EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY



Aim:

To create a function in C that deletes an element from a queue implemented using an array.

Algorithm:

1.	Check if the Queue is Empty
o	If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
2.	Delete the Front Element
o	If the queue is not empty, the element at the front index is deleted.
o	Increment the front pointer by 1 to remove the element and point to the next element in the queue.
3.	Check if the Queue Becomes Empty After Deletion:
o	After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
4.	End the Function.



Program:
```
#include <stdio.h>
#define MAX 5

int queue[MAX];
int front = -1;
int rear = -1;

// Function to insert element into the queue
void enqueue(int element) {
    if (rear == MAX - 1) {
        printf("Queue overflow! Cannot insert %d\n", element);
    } else {
        if (front == -1) front = 0;
        rear++;
        queue[rear] = element;
        printf("%d inserted into queue.\n", element);
    }
}

// Function to delete element from the queue
void dequeue() {
    if (front == -1 || front > rear) {
        printf("Queue underflow! Queue is empty.\n");
    } else {
        printf("%d deleted from queue.\n", queue[front]);
        front++;
        if (front > rear) { // Queue becomes empty
            front = rear = -1;
        }
    }
}

// Function to display queue elements
void display() {
    if (front == -1) {
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
    // Insert elements
    enqueue(10);
    enqueue(20);
    enqueue(30);
    enqueue(40);

    display();  // Display queue before deletion

    // Delete elements
    dequeue();
    dequeue();

    display();  // Display queue after deletion

    return 0;
}

```

Output:
<img width="559" height="338" alt="image" src="https://github.com/user-attachments/assets/bf3f9562-cd3a-41f4-a75d-ac6fea482ad9" />




Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.

https://colab.research.google.com/drive/1ZDHrPRh7Im6BXH1wW5mAa9ncHzIL5Azt#scrollTo=u15RtX3voAQA
