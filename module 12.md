

EXP NO 26: C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display stack elements using linked list.

Algorithm:
1.	Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
2.	Declare a global variable head representing the starting node of the linked list.
3.	Define a function display to print the elements of the linked list.
4.	Declare a pointer p and initialize it with the head of the linked list.
5.	Use a while loop to traverse the linked list:
6.	Print the data of the current node.
7.	Move to the next node using the next pointer.
 
Program:

```
#include <stdio.h>

struct Node {
    int data;
    struct Node *next;
};

struct Node *head = NULL;

void display() {
    struct Node *p = head;

    if (p == NULL) {
        printf("Stack is empty\n");
        return;
    }

    printf("Stack elements are:\n");

    while (p != NULL) {
        printf("%d\n", p->data);
        p = p->next;
    }
}

int main() {
    struct Node n1, n2, n3;

    n1.data = 10;
    n1.next = &n2;

    n2.data = 20;
    n2.next = &n3;

    n3.data = 30;
    n3.next = NULL;

    head = &n1;

    display();

    return 0;
}
```

Output:

<img width="371" height="114" alt="image" src="https://github.com/user-attachments/assets/e26704b6-d5da-4c09-a50e-f03272dcf49c" />



Result:
Thus, the program to display stack elements using linked list is verified successfully. 



EXP.NO 27: C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING 
LINKED LIST.
Aim:
To write a C program to pop an element from the given stack using liked list.

Algorithm:
1.	Check for Empty Stack
2.	If head is equal to NULL, Print "Stack is empty."
3.	Else Proceed to the next step.
4.	Set head to point to the next node in the stack.
 
Program:

```
#include <stdio.h>

struct Node {
    int data;
    struct Node *next;
};

struct Node *head = NULL;

void pop() {
    struct Node *p;

    if (head == NULL) {
        printf("Stack is empty\n");
        return;
    }

    p = head;
    printf("Popped element: %d\n", p->data);
    head = head->next;
}

int main() {
    struct Node n1, n2, n3;

    n1.data = 10;
    n1.next = &n2;

    n2.data = 20;
    n2.next = &n3;

    n3.data = 30;
    n3.next = NULL;

    head = &n1;

    pop();

    printf("Stack after pop:\n");

    while (head != NULL) {
        printf("%d\n", head->data);
        head = head->next;
    }

    return 0;
}
```

Output:

<img width="466" height="111" alt="image" src="https://github.com/user-attachments/assets/bbce4030-52d8-47ef-bde1-8ef17eb848e3" />




Result:
Thus, the program to pop an element from the given stack using liked list is verified successfully.

 
EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display queue elements using linked list.
Algorithm:
1.	Check if Queue is Empty
2.	Display Queue Elements
3.	Print the data of the current node pointed to by front
4.	Update front to point to the next node.
5.	End the display function.
 
Program:

```
#include <stdio.h>

struct Node {
    int data;
    struct Node *next;
};

struct Node *front = NULL;

void display() {
    struct Node *p = front;

    if (p == NULL) {
        printf("Queue is empty\n");
        return;
    }

    printf("Queue elements are:\n");

    while (p != NULL) {
        printf("%d\n", p->data);
        p = p->next;
    }
}

int main() {
    struct Node n1, n2, n3;

    n1.data = 10;
    n1.next = &n2;

    n2.data = 20;
    n2.next = &n3;

    n3.data = 30;
    n3.next = NULL;

    front = &n1;

    display();

    return 0;
}
```

Output:

<img width="375" height="116" alt="image" src="https://github.com/user-attachments/assets/5bb4a495-ed39-4a6f-a112-29bd684ec26b" />


Result:
Thus, the program to display queue elements using linked list is verified successfully.


 
EXP NO:29 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

Aim:
To write a C program to insert elements in queue using linked list

Algorithm:
1.	Allocate Memory for New Node
2.	Set Data and Next Pointer
3.	Check if Queue is Empty
4.	Set both front and rear to point to the new node p.
5.	Set the next pointer of the current rear to point to the new node p.
6.	End of Enqueue Operation
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

struct Node *front = NULL;
struct Node *rear = NULL;

void enqueue(int value) {
    struct Node *p;

    p = (struct Node *)malloc(sizeof(struct Node));

    p->data = value;
    p->next = NULL;

    if (front == NULL) {
        front = p;
        rear = p;
    } else {
        rear->next = p;
        rear = p;
    }
}

void display() {
    struct Node *p = front;

    printf("Queue elements are:\n");

    while (p != NULL) {
        printf("%d\n", p->data);
        p = p->next;
    }
}

int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);

    display();

    return 0;
}
```

Output:

<img width="334" height="102" alt="image" src="https://github.com/user-attachments/assets/39764922-6b2e-4ab0-a3d0-975e5d2660ec" />


Result:
Thus, the program to insert elements in queue using linked list is verified successfully.



EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.


Aim:

The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

Algorithm:

1.	Check if the queue is empty:
o	If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
2.	Access the front element:
o	If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).

Program:

```
#include <stdio.h>

struct Node {
    int data;
    struct Node *next;
};

struct Node *front = NULL;

int peek() {
    if (front == NULL)
        return -1;

    return front->data;
}

int main() {
    struct Node n1, n2, n3;

    n1.data = 10;
    n1.next = &n2;

    n2.data = 20;
    n2.next = &n3;

    n3.data = 30;
    n3.next = NULL;

    front = &n1;

    printf("Peek element: %d\n", peek());

    return 0;
}
```

Output:

<img width="668" height="90" alt="image" src="https://github.com/user-attachments/assets/c6bd4ab6-6763-4aa5-a47c-222102b20bbf" />




Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.


