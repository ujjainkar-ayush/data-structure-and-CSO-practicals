# Data Structure and CSO Practicals

List of Practical’s: Data Structure with OOP
1.	Create and display a singly linked list with n integer nodes. 
2.	Implement insertion of a new node at the end in a linked list. 
3.	Implement insertion of a new node before specific node in a linked list.
4.	Implement insertion of a new node after specific node in a linked list. 
5.	Implement deletion operations in a linked list. 
6.	Implement deletion operations in a doubly linked list. 
7.	Convert a sparse matrix to its compact representation.
8.	Write a program to find an item using sequential search in array.
9.	Write a program to find an item using binary search in array. 
10.	Write a program to insert new element in the middle of the one dimensional array.
11.	Write a program to delete the element from the middle of the one dimensional array.
12.	Write a program for array implementation of a Stack.
13.	Write a program for array implementation of a Queue.
14.	Write a program for the Merge sorts of Array.
15.	Write a program for Hashing Function.
16.	Search an element in an array using linear and binary search.
17.	Implement circular linked list with insertion at beginning and end.  
18.	Implement stack using linked list and evaluate a postfix expression. 
19.	Implement queue using array and perform enqueue, dequeue, and display. 
20.	Implement circular queue using array. 
21.	Create a binary tree and perform inorder, preorder, and postorder traversal. 
22.	Implement binary search tree with insertion and deletion operations. 
23.	Construct an AVL tree and perform rotations to maintain balance.
24.	Count leaf nodes, internal nodes, and height of a binary tree.
25.	Do any one of the following:
a.	Implement insertion sort.
b.	Implement selection sort.
c.	Implement merge sort.
d.	Implement quick sort.
e.	Implement radix sort for positive integers.
26.	Represent a graph using adjacency matrix and adjacency list.
27.	Implement BFS and DFS traversal on a graph.
28.	Do any one of the following:
a.	Find shortest path using Dijkstra’s algorithm.
b.	Find minimum cost spanning tree using Kruskal’s algorithm.
c.	Compute all-pairs shortest paths using Floyd-Warshall algorithm.
29.	Implement hashing with linear probing.

List of Practical’s: CSO 
1. Implement a C/ C++ program to convert binary number to decimal number vice versa.
2. Implement a C/ C++ program to convert Hexadecimal number to decimal number
3. Implement a C/ C++ program to perform Binary Addition and Subtraction.
4. Implement Logic gates using NAND gates 
5. Implement Logic gates using NOR gates.
6. Design and implement the 8:1 MUX using gates /ICs.
7. Design and implement the 8:1 MUX using gates /ICs.
8. Design a Full adder using gates.
9. Write 8085 Program 8-bit addition and subtraction. 


1.	Create and display a singly linked list with n integer nodes.
```
// Aim : Create and display a singly linked list with n integer nodes.
// Software used : Turbo C

// Program:

#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

struct Node* createList(int n) {
    struct Node *head = NULL, *temp, *newNode;
    int data, i;

    if (n <= 0) {
        printf("Number of nodes must be greater than zero.\n");
        return NULL;
    }

    head = (struct Node*)malloc(sizeof(struct Node));
    if (head == NULL) {
        printf("Memory not allocated.\n");
        exit(0);
    }

    printf("Enter data for node 1: ");
    scanf("%d", &data);
    head->data = data;
    head->next = NULL;
    temp = head;

    for (i = 2; i <= n; i++) {
        newNode = (struct Node*)malloc(sizeof(struct Node));
        if (newNode == NULL) {
            printf("Memory not allocated.\n");
            break;
        }

        printf("Enter data for node %d: ", i);
        scanf("%d", &data);
        newNode->data = data;
        newNode->next = NULL;

        temp->next = newNode;
        temp = newNode;
    }

    return head;
}

void displayList(struct Node *head) {
    struct Node *temp = head;

    if (head == NULL) {
        printf("List is empty.\n");
        return;
    }

    printf("\nThe elements in the linked list are:\n");
    while (temp != NULL) {
        printf("%d -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node *head = NULL;
    int n;

    printf("Enter the number of nodes: ");
    scanf("%d", &n);

    head = createList(n);
    displayList(head);

    return 0;
}

// Output :

// Enter the number of nodes: 5
// Enter data for node 1: 10
// Enter data for node 2: 20
// Enter data for node 3: 30
// Enter data for node 4: 40
// Enter data for node 5: 50

// The elements in the linked list are:
// 10 -> 20 -> 30 -> 40 -> 50 -> NULL

```
2. Implement insertion of a new node at the end in a linked list.

```
// Aim : Implement insertion of a new node at the end in a linked list. 
// Software used : Turbo C

// Program:

#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

struct Node* createList(int n) {
    struct Node *head = NULL, *temp, *newNode;
    int data, i;

    if (n <= 0) {
        printf("Number of nodes must be greater than zero.\n");
        return NULL;
    }

    head = (struct Node*)malloc(sizeof(struct Node));
    if (head == NULL) {
        printf("Memory not allocated.\n");
        exit(0);
    }

    printf("Enter data for node 1: ");
    scanf("%d", &data);
    head->data = data;
    head->next = NULL;
    temp = head;

    for (i = 2; i <= n; i++) {
        newNode = (struct Node*)malloc(sizeof(struct Node));
        if (newNode == NULL) {
            printf("Memory not allocated.\n");
            break;
        }

        printf("Enter data for node %d: ", i);
        scanf("%d", &data);
        newNode->data = data;
        newNode->next = NULL;

        temp->next = newNode;
        temp = newNode;
    }

    return head;
}

void insertAtEnd(struct Node *head, int data) {
    struct Node *newNode, *temp;
    newNode = (struct Node*)malloc(sizeof(struct Node));

    if (newNode == NULL) {
        printf("Memory not allocated.\n");
        return;
    }

    newNode->data = data;
    newNode->next = NULL;

    temp = head;
    while (temp->next != NULL) {
        temp = temp->next;
    }

    temp->next = newNode;
}

void displayList(struct Node *head) {
    struct Node *temp = head;

    if (head == NULL) {
        printf("List is empty.\n");
        return;
    }

    printf("\nThe elements in the linked list are:\n");
    while (temp != NULL) {
        printf("%d -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node *head = NULL;
    int n, newData;

    printf("Enter the number of nodes: ");
    scanf("%d", &n);

    head = createList(n);
    displayList(head);

    printf("\nEnter data to insert at the end: ");
    scanf("%d", &newData);

    insertAtEnd(head, newData);
    displayList(head);

    return 0;
}

// Output :
// Enter the number of nodes: 4
// Enter data for node 1: 5
// Enter data for node 2: 10
// Enter data for node 3: 15
// Enter data for node 4: 20
// The elements in the linked list are:
// 5 -> 10 -> 15 -> 20 -> NULL
// Enter data to insert at the end: 25
// The elements in the linked list are:
// 5 -> 10 -> 15 -> 20 -> 25 -> NULL

```

3.	Implement insertion of a new node before specific node in a linked list.

```
// Aim : Implement insertion of a new node before specific node in a linked list.
// Software used : Turbo C

// Program:
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

struct Node* createList(int n) {
    struct Node *head = NULL, *temp, *newNode;
    int data, i;

    if (n <= 0) {
        printf("Number of nodes must be greater than zero.\n");
        return NULL;
    }

    head = (struct Node*)malloc(sizeof(struct Node));
    if (head == NULL) {
        printf("Memory not allocated.\n");
        exit(0);
    }

    printf("Enter data for node 1: ");
    scanf("%d", &data);
    head->data = data;
    head->next = NULL;
    temp = head;

    for (i = 2; i <= n; i++) {
        newNode = (struct Node*)malloc(sizeof(struct Node));
        if (newNode == NULL) {
            printf("Memory not allocated.\n");
            break;
        }

        printf("Enter data for node %d: ", i);
        scanf("%d", &data);
        newNode->data = data;
        newNode->next = NULL;

        temp->next = newNode;
        temp = newNode;
    }

    return head;
}

struct Node* insertBefore(struct Node *head, int target, int newData) {
    struct Node *newNode, *temp, *prev = NULL;

    newNode = (struct Node*)malloc(sizeof(struct Node));
    if (newNode == NULL) {
        printf("Memory not allocated.\n");
        return head;
    }

    newNode->data = newData;
    newNode->next = NULL;

    if (head == NULL) {
        printf("List is empty.\n");
        return head;
    }

    if (head->data == target) {
        newNode->next = head;
        head = newNode;
        return head;
    }

    temp = head;
    while (temp != NULL && temp->data != target) {
        prev = temp;
        temp = temp->next;
    }

    if (temp == NULL) {
        printf("Node with data %d not found.\n", target);
        free(newNode);
    } else {
        prev->next = newNode;
        newNode->next = temp;
    }

    return head;
}

void displayList(struct Node *head) {
    struct Node *temp = head;

    if (head == NULL) {
        printf("List is empty.\n");
        return;
    }

    printf("\nThe elements in the linked list are:\n");
    while (temp != NULL) {
        printf("%d -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node *head = NULL;
    int n, target, newData;

    printf("Enter the number of nodes: ");
    scanf("%d", &n);

    head = createList(n);
    displayList(head);

    printf("\nEnter the data of the node before which to insert: ");
    scanf("%d", &target);

    printf("Enter the data for the new node: ");
    scanf("%d", &newData);

    head = insertBefore(head, target, newData);
    displayList(head);

    return 0;
}

// Output :
// Enter the number of nodes: 5
// Enter data for node 1: 10
// Enter data for node 2: 20
// Enter data for node 3: 30
// Enter data for node 4: 40
// Enter data for node 5: 50
// The elements in the linked list are:
// 10 -> 20 -> 30 -> 40 -> 50 -> NULL
// Enter the data of the node before which to insert: 30
// Enter the data for the new node: 25
// The elements in the linked list are:
// 10 -> 20 -> 25 -> 30 -> 40 -> 50 -> NULL

```

4.	Implement insertion of a new node after specific node in a linked list.
```
// Aim : Implement insertion of a new node after specific node in a linked list. 
// Software used : Turbo C

// Program:
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

struct Node* createList(int n) {
    struct Node *head = NULL, *temp, *newNode;
    int data, i;

    if (n <= 0) {
        printf("Number of nodes must be greater than zero.\n");
        return NULL;
    }

    head = (struct Node*)malloc(sizeof(struct Node));
    if (head == NULL) {
        printf("Memory not allocated.\n");
        exit(0);
    }

    printf("Enter data for node 1: ");
    scanf("%d", &data);
    head->data = data;
    head->next = NULL;
    temp = head;

    for (i = 2; i <= n; i++) {
        newNode = (struct Node*)malloc(sizeof(struct Node));
        if (newNode == NULL) {
            printf("Memory not allocated.\n");
            break;
        }

        printf("Enter data for node %d: ", i);
        scanf("%d", &data);
        newNode->data = data;
        newNode->next = NULL;

        temp->next = newNode;
        temp = newNode;
    }

    return head;
}

void insertAfter(struct Node *head, int target, int newData) {
    struct Node *temp = head, *newNode;

    if (head == NULL) {
        printf("List is empty.\n");
        return;
    }

    while (temp != NULL && temp->data != target) {
        temp = temp->next;
    }

    if (temp == NULL) {
        printf("Node with data %d not found.\n", target);
        return;
    }

    newNode = (struct Node*)malloc(sizeof(struct Node));
    if (newNode == NULL) {
        printf("Memory not allocated.\n");
        return;
    }

    newNode->data = newData;
    newNode->next = temp->next;
    temp->next = newNode;
}

void displayList(struct Node *head) {
    struct Node *temp = head;

    if (head == NULL) {
        printf("List is empty.\n");
        return;
    }

    printf("\nThe elements in the linked list are:\n");
    while (temp != NULL) {
        printf("%d -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node *head = NULL;
    int n, target, newData;

    printf("Enter the number of nodes: ");
    scanf("%d", &n);

    head = createList(n);
    displayList(head);

    printf("\nEnter the data of the node after which to insert: ");
    scanf("%d", &target);

    printf("Enter the data for the new node: ");
    scanf("%d", &newData);

    insertAfter(head, target, newData);
    displayList(head);

    return 0;
}

// Output :
// Enter the number of nodes: 5
// Enter data for node 1: 10
// Enter data for node 2: 20
// Enter data for node 3: 30
// Enter data for node 4: 40
// Enter data for node 5: 50
// The elements in the linked list are:
// 10 -> 20 -> 30 -> 40 -> 50 -> NULL
// Enter the data of the node after which to insert: 30
// Enter the data for the new node: 35
// The elements in the linked list are:
// 10 -> 20 -> 30 -> 35 -> 40 -> 50 -> NULL

```

5.	Implement deletion operations in a linked list.
```
// Aim : Implement deletion operations in a linked list. 
// Software used : Turbo C

// Program:
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

struct Node* createList(int n) {
    struct Node *head = NULL, *temp, *newNode;
    int data, i;

    if (n <= 0) {
        printf("Number of nodes must be greater than zero.\n");
        return NULL;
    }

    head = (struct Node*)malloc(sizeof(struct Node));
    if (head == NULL) {
        printf("Memory not allocated.\n");
        exit(0);
    }

    printf("Enter data for node 1: ");
    scanf("%d", &data);
    head->data = data;
    head->next = NULL;
    temp = head;

    for (i = 2; i <= n; i++) {
        newNode = (struct Node*)malloc(sizeof(struct Node));
        if (newNode == NULL) {
            printf("Memory not allocated.\n");
            break;
        }

        printf("Enter data for node %d: ", i);
        scanf("%d", &data);
        newNode->data = data;
        newNode->next = NULL;

        temp->next = newNode;
        temp = newNode;
    }

    return head;
}

struct Node* deleteAtBeginning(struct Node *head) {
    struct Node *temp;

    if (head == NULL) {
        printf("List is empty.\n");
        return NULL;
    }

    temp = head;
    head = head->next;
    printf("\nDeleted node: %d\n", temp->data);
    free(temp);

    return head;
}

struct Node* deleteAtEnd(struct Node *head) {
    struct Node *temp = head, *prev = NULL;

    if (head == NULL) {
        printf("List is empty.\n");
        return NULL;
    }

    if (head->next == NULL) {
        printf("\nDeleted node: %d\n", head->data);
        free(head);
        return NULL;
    }

    while (temp->next != NULL) {
        prev = temp;
        temp = temp->next;
    }

    printf("\nDeleted node: %d\n", temp->data);
    prev->next = NULL;
    free(temp);

    return head;
}

struct Node* deleteSpecific(struct Node *head, int key) {
    struct Node *temp = head, *prev = NULL;

    if (head == NULL) {
        printf("List is empty.\n");
        return NULL;
    }

    if (head->data == key) {
        head = head->next;
        printf("\nDeleted node: %d\n", temp->data);
        free(temp);
        return head;
    }

    while (temp != NULL && temp->data != key) {
        prev = temp;
        temp = temp->next;
    }

    if (temp == NULL) {
        printf("Node with data %d not found.\n", key);
        return head;
    }

    prev->next = temp->next;
    printf("\nDeleted node: %d\n", temp->data);
    free(temp);

    return head;
}

void displayList(struct Node *head) {
    struct Node *temp = head;

    if (head == NULL) {
        printf("List is empty.\n");
        return;
    }

    printf("\nThe elements in the linked list are:\n");
    while (temp != NULL) {
        printf("%d -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node *head = NULL;
    int n, choice, key;

    printf("Enter the number of nodes: ");
    scanf("%d", &n);

    head = createList(n);
    displayList(head);

    do {
        printf("\n1. Delete at Beginning");
        printf("\n2. Delete at End");
        printf("\n3. Delete Specific Node");
        printf("\n4. Display List");
        printf("\n5. Exit");
        printf("\nEnter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                head = deleteAtBeginning(head);
                break;
            case 2:
                head = deleteAtEnd(head);
                break;
            case 3:
                printf("Enter the data of the node to delete: ");
                scanf("%d", &key);
                head = deleteSpecific(head, key);
                break;
            case 4:
                displayList(head);
                break;
            case 5:
                printf("Exiting...\n");
                break;
            default:
                printf("Invalid choice.\n");
        }

    } while (choice != 5);

    return 0;
}

// Output :
Enter the number of nodes: 5
// Enter data for node 1: 10
// Enter data for node 2: 20
// Enter data for node 3: 30
// Enter data for node 4: 40
// Enter data for node 5: 50

// The elements in the linked list are:
// 10 -> 20 -> 30 -> 40 -> 50 -> NULL

// 1. Delete at Beginning
// 2. Delete at End
// 3. Delete Specific Node
// 4. Display List
// 5. Exit
// Enter your choice: 1

// Deleted node: 10

// The elements in the linked list are:
// 20 -> 30 -> 40 -> 50 -> NULL

// Enter your choice: 3
// Enter the data of the node to delete: 40

// Deleted node: 40

// The elements in the linked list are:
// 20 -> 30 -> 50 -> NULL


```

6.	Implement deletion operations in a doubly linked list.
```
// Aim : Implement deletion operations in a doubly linked list. 
// Software used : Turbo C

// Program:
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *prev;
    struct Node *next;
};

struct Node* createList(int n) {
    struct Node *head = NULL, *temp, *newNode;
    int data, i;

    if (n <= 0) {
        printf("Number of nodes must be greater than zero.\n");
        return NULL;
    }

    head = (struct Node*)malloc(sizeof(struct Node));
    if (head == NULL) {
        printf("Memory not allocated.\n");
        exit(0);
    }

    printf("Enter data for node 1: ");
    scanf("%d", &data);
    head->data = data;
    head->prev = NULL;
    head->next = NULL;
    temp = head;

    for (i = 2; i <= n; i++) {
        newNode = (struct Node*)malloc(sizeof(struct Node));
        if (newNode == NULL) {
            printf("Memory not allocated.\n");
            break;
        }

        printf("Enter data for node %d: ", i);
        scanf("%d", &data);
        newNode->data = data;
        newNode->prev = temp;
        newNode->next = NULL;
        temp->next = newNode;
        temp = newNode;
    }

    return head;
}

struct Node* deleteAtBeginning(struct Node *head) {
    struct Node *temp;

    if (head == NULL) {
        printf("List is empty.\n");
        return NULL;
    }

    temp = head;
    head = head->next;

    if (head != NULL)
        head->prev = NULL;

    printf("\nDeleted node: %d\n", temp->data);
    free(temp);

    return head;
}

struct Node* deleteAtEnd(struct Node *head) {
    struct Node *temp = head;

    if (head == NULL) {
        printf("List is empty.\n");
        return NULL;
    }

    if (head->next == NULL) {
        printf("\nDeleted node: %d\n", head->data);
        free(head);
        return NULL;
    }

    while (temp->next != NULL) {
        temp = temp->next;
    }

    printf("\nDeleted node: %d\n", temp->data);
    temp->prev->next = NULL;
    free(temp);

    return head;
}

struct Node* deleteSpecific(struct Node *head, int key) {
    struct Node *temp = head;

    if (head == NULL) {
        printf("List is empty.\n");
        return NULL;
    }

    while (temp != NULL && temp->data != key) {
        temp = temp->next;
    }

    if (temp == NULL) {
        printf("Node with data %d not found.\n", key);
        return head;
    }

    if (temp->prev == NULL)
        head = temp->next;
    else
        temp->prev->next = temp->next;

    if (temp->next != NULL)
        temp->next->prev = temp->prev;

    printf("\nDeleted node: %d\n", temp->data);
    free(temp);

    return head;
}

void displayList(struct Node *head) {
    struct Node *temp = head;

    if (head == NULL) {
        printf("List is empty.\n");
        return;
    }

    printf("\nThe elements in the doubly linked list are:\n");
    while (temp != NULL) {
        printf("%d <-> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node *head = NULL;
    int n, choice, key;

    printf("Enter the number of nodes: ");
    scanf("%d", &n);

    head = createList(n);
    displayList(head);

    do {
        printf("\n1. Delete at Beginning");
        printf("\n2. Delete at End");
        printf("\n3. Delete Specific Node");
        printf("\n4. Display List");
        printf("\n5. Exit");
        printf("\nEnter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                head = deleteAtBeginning(head);
                break;
            case 2:
                head = deleteAtEnd(head);
                break;
            case 3:
                printf("Enter the data of the node to delete: ");
                scanf("%d", &key);
                head = deleteSpecific(head, key);
                break;
            case 4:
                displayList(head);
                break;
            case 5:
                printf("Exiting...\n");
                break;
            default:
                printf("Invalid choice.\n");
        }

    } while (choice != 5);

    return 0;
}

// Output :
// Enter the number of nodes: 5
// Enter data for node 1: 10
// Enter data for node 2: 20
// Enter data for node 3: 30
// Enter data for node 4: 40
// Enter data for node 5: 50

// The elements in the doubly linked list are:
// 10 <-> 20 <-> 30 <-> 40 <-> 50 <-> NULL

// 1. Delete at Beginning
// 2. Delete at End
// 3. Delete Specific Node
// 4. Display List
// 5. Exit
// Enter your choice: 1

// Deleted node: 10

// The elements in the doubly linked list are:
// 20 <-> 30 <-> 40 <-> 50 <-> NULL

// Enter your choice: 3
// Enter the data of the node to delete: 40

// Deleted node: 40

// The elements in the doubly linked list are:
// 20 <-> 30 <-> 50 <-> NULL

```

7.	Convert a sparse matrix to its compact representation.

```
// Aim : Convert a sparse matrix to its compact representation.
// Software used : Turbo C

// Program:
#include <stdio.h>

int main() {
    int sparse[10][10], compact[10][10];
    int i, j, m, n, k = 1, count = 0;

    printf("Enter number of rows and columns: ");
    scanf("%d %d", &m, &n);

    printf("Enter elements of sparse matrix:\n");
    for (i = 0; i < m; i++)
        for (j = 0; j < n; j++) {
            scanf("%d", &sparse[i][j]);
            if (sparse[i][j] != 0)
                count++;
        }

    compact[0][0] = m;
    compact[0][1] = n;
    compact[0][2] = count;

    for (i = 0; i < m; i++)
        for (j = 0; j < n; j++)
            if (sparse[i][j] != 0) {
                compact[k][0] = i;
                compact[k][1] = j;
                compact[k][2] = sparse[i][j];
                k++;
            }

    printf("Compact matrix representation:\n");
    for (i = 0; i <= count; i++) {
        for (j = 0; j < 3; j++)
            printf("%d ", compact[i][j]);
        printf("\n");
    }

    return 0;
}

// Output :
// Enter number of rows and columns: 3 3
// Enter elements of sparse matrix:
// 0 0 3
// 0 0 0
// 4 0 5

// Compact matrix representation:
// 3 3 3
// 0 2 3
// 2 0 4
// 2 2 5

```

8.	Write a program to find an item using sequential search in array.
```
// Aim : Write a program to find an item using sequential search in array.
// Software used : Turbo C

// Program:
#include <stdio.h>

int main() {
    int n, i, key, found = 0;
    printf("Enter number of elements: ");
    scanf("%d", &n);

    int arr[n];
    printf("Enter elements:\n");
    for(i = 0; i < n; i++)
        scanf("%d", &arr[i]);

    printf("Enter element to search: ");
    scanf("%d", &key);

    for(i = 0; i < n; i++) {
        if(arr[i] == key) {
            printf("Element found at position %d\n", i + 1);
            found = 1;
            break;
        }
    }

    if(!found)
        printf("Element not found in the array\n");

    return 0;
}

// Output :
// Enter number of elements: 5
// Enter elements:
// 10 25 30 45 50
// Enter element to search: 30
// Element found at position 3

```

9.	Write a program to find an item using binary search in array. 
```
// Aim : Write a program to find an item using binary search in array. 
// Software used : Turbo C

// Program:
#include <stdio.h>

int main() {
    int n, i, key, low, high, mid, found = 0;
    printf("Enter number of elements: ");
    scanf("%d", &n);

    int arr[n];
    printf("Enter elements in sorted order:\n");
    for(i = 0; i < n; i++)
        scanf("%d", &arr[i]);

    printf("Enter element to search: ");
    scanf("%d", &key);

    low = 0;
    high = n - 1;

    while(low <= high) {
        mid = (low + high) / 2;
        if(arr[mid] == key) {
            printf("Element found at position %d\n", mid + 1);
            found = 1;
            break;
        } else if(arr[mid] < key)
            low = mid + 1;
        else
            high = mid - 1;
    }

    if(!found)
        printf("Element not found in the array\n");

    return 0;
}

// Output :
// Enter number of elements: 6
// Enter elements in sorted order:
// 5 10 15 20 25 30
// Enter element to search: 20
// Element found at position 4

```

10.	Write a program to insert new element in the middle of the one dimensional array.
```
// Aim : Write a program to insert new element in the middle of the one dimensional array.
// Software used : Turbo C

// Program:
#include <stdio.h>

int main() {
    int n, i, pos, value;
    printf("Enter number of elements: ");
    scanf("%d", &n);

    int arr[100];
    printf("Enter elements:\n");
    for(i = 0; i < n; i++)
        scanf("%d", &arr[i]);

    pos = n / 2;
    printf("Enter element to insert in the middle: ");
    scanf("%d", &value);

    for(i = n; i > pos; i--)
        arr[i] = arr[i - 1];

    arr[pos] = value;
    n++;

    printf("Array after insertion:\n");
    for(i = 0; i < n; i++)
        printf("%d ", arr[i]);

    printf("\n");
    return 0;
}

// Output :
// Enter number of elements: 6
// Enter elements:
// 10 20 30 40 50 60
// Enter element to insert in the middle: 100
// Array after insertion:
// 10 20 30 100 40 50 60


```

11.	Write a program to delete the element from the middle of the one dimensional array.
```
// Aim : Write a program to delete the element from the middle of the one dimensional array.
// Software used : Turbo C

// Program:
#include <stdio.h>

int main() {
    int n, i, pos;
    printf("Enter number of elements: ");
    scanf("%d", &n);

    int arr[100];
    printf("Enter elements:\n");
    for(i = 0; i < n; i++)
        scanf("%d", &arr[i]);

    pos = n / 2;

    for(i = pos; i < n - 1; i++)
        arr[i] = arr[i + 1];

    n--;

    printf("Array after deleting middle element:\n");
    for(i = 0; i < n; i++)
        printf("%d ", arr[i]);

    printf("\n");
    return 0;
}

// Output :
// Enter number of elements: 7
// Enter elements:
// 10 20 30 40 50 60 70
// Array after deleting middle element:
// 10 20 30 50 60 70

```
12.	Write a program for array implementation of a Stack.
```
// Aim : Write a program for array implementation of a Stack.
// Software used : Turbo C

// Program:
#include <stdio.h>
#define MAX 5

int stack[MAX], top = -1;

void push(int value) {
    if(top == MAX - 1)
        printf("Stack Overflow\n");
    else {
        top++;
        stack[top] = value;
        printf("%d pushed into stack\n", value);
    }
}

void pop() {
    if(top == -1)
        printf("Stack Underflow\n");
    else {
        printf("%d popped from stack\n", stack[top]);
        top--;
    }
}

void display() {
    if(top == -1)
        printf("Stack is empty\n");
    else {
        printf("Stack elements are:\n");
        for(int i = top; i >= 0; i--)
            printf("%d\n", stack[i]);
    }
}

int main() {
    int choice, value;
    while(1) {
        printf("\n1. Push\n2. Pop\n3. Display\n4. Exit\nEnter your choice: ");
        scanf("%d", &choice);

        switch(choice) {
            case 1:
                printf("Enter value to push: ");
                scanf("%d", &value);
                push(value);
                break;
            case 2:
                pop();
                break;
            case 3:
                display();
                break;
            case 4:
                return 0;
            default:
                printf("Invalid choice\n");
        }
    }
}

// Output :
// 1. Push
// 2. Pop
// 3. Display
// 4. Exit
// Enter your choice: 1
// Enter value to push: 10
// 10 pushed into stack

// Enter your choice: 1
// Enter value to push: 20
// 20 pushed into stack

// Enter your choice: 1
// Enter value to push: 30
// 30 pushed into stack

// Enter your choice: 3
// Stack elements are:
// 30
// 20
// 10

// Enter your choice: 2
// 30 popped from stack

// Enter your choice: 3
// Stack elements are:
// 20
// 10

// Enter your choice: 4

```

13.	Write a program for array implementation of a Queue.
```
// Aim : Write a program for array implementation of a Queue.
// Software used : Turbo C

// Program:
#include <stdio.h>
#define MAX 5

int queue[MAX], front = -1, rear = -1;

void enqueue(int value) {
    if(rear == MAX - 1)
        printf("Queue Overflow\n");
    else {
        if(front == -1)
            front = 0;
        rear++;
        queue[rear] = value;
        printf("%d inserted into queue\n", value);
    }
}

void dequeue() {
    if(front == -1 || front > rear)
        printf("Queue Underflow\n");
    else {
        printf("%d deleted from queue\n", queue[front]);
        front++;
    }
}

void display() {
    if(front == -1 || front > rear)
        printf("Queue is empty\n");
    else {
        printf("Queue elements are:\n");
        for(int i = front; i <= rear; i++)
            printf("%d ", queue[i]);
        printf("\n");
    }
}

int main() {
    int choice, value;
    while(1) {
        printf("\n1. Enqueue\n2. Dequeue\n3. Display\n4. Exit\nEnter your choice: ");
        scanf("%d", &choice);

        switch(choice) {
            case 1:
                printf("Enter value to insert: ");
                scanf("%d", &value);
                enqueue(value);
                break;
            case 2:
                dequeue();
                break;
            case 3:
                display();
                break;
            case 4:
                return 0;
            default:
                printf("Invalid choice\n");
        }
    }
}

// Output :
// 1. Enqueue
// 2. Dequeue
// 3. Display
// 4. Exit
// Enter your choice: 1
// Enter value to insert: 10
// 10 inserted into queue

// Enter your choice: 1
// Enter value to insert: 20
// 20 inserted into queue

// Enter your choice: 1
// Enter value to insert: 30
// 30 inserted into queue

// Enter your choice: 3
// Queue elements are:
// 10 20 30

// Enter your choice: 2
// 10 deleted from queue

// Enter your choice: 3
// Queue elements are:
// 20 30

// Enter your choice: 4

```

14.	Write a program for the Merge sorts of Array.
```
// Aim : Write a program for the Merge sorts of Array.
// Software used : Turbo C

// Program:
#include <stdio.h>

void merge(int arr[], int left, int mid, int right) {
    int i = left, j = mid + 1, k = left;
    int temp[100];

    while(i <= mid && j <= right) {
        if(arr[i] <= arr[j])
            temp[k++] = arr[i++];
        else
            temp[k++] = arr[j++];
    }

    while(i <= mid)
        temp[k++] = arr[i++];

    while(j <= right)
        temp[k++] = arr[j++];

    for(i = left; i <= right; i++)
        arr[i] = temp[i];
}

void mergeSort(int arr[], int left, int right) {
    if(left < right) {
        int mid = (left + right) / 2;
        mergeSort(arr, left, mid);
        mergeSort(arr, mid + 1, right);
        merge(arr, left, mid, right);
    }
}

int main() {
    int n, i;
    printf("Enter number of elements: ");
    scanf("%d", &n);

    int arr[100];
    printf("Enter elements:\n");
    for(i = 0; i < n; i++)
        scanf("%d", &arr[i]);

    mergeSort(arr, 0, n - 1);

    printf("Sorted array:\n");
    for(i = 0; i < n; i++)
        printf("%d ", arr[i]);

    printf("\n");
    return 0;
}

// Output :
// Enter number of elements: 6
// Enter elements:
// 45 12 89 33 22 10
// Sorted array:
// 10 12 22 33 45 89

```

15.	Write a program for Hashing Function.
```
// Aim : Write a program for Hashing Function.
// Software used : Turbo C

// Program:
#include <stdio.h>

#define SIZE 10

int hash(int key) {
    return key % SIZE;
}

void insert(int hashTable[], int key) {
    int index = hash(key);
    int i = 0;

    while(hashTable[(index + i) % SIZE] != -1)
        i++;

    hashTable[(index + i) % SIZE] = key;
}

void display(int hashTable[]) {
    printf("Hash Table:\n");
    for(int i = 0; i < SIZE; i++) {
        if(hashTable[i] != -1)
            printf("%d --> %d\n", i, hashTable[i]);
        else
            printf("%d --> NULL\n", i);
    }
}

int main() {
    int hashTable[SIZE];
    int n, key;

    for(int i = 0; i < SIZE; i++)
        hashTable[i] = -1;

    printf("Enter number of keys to insert: ");
    scanf("%d", &n);

    printf("Enter keys:\n");
    for(int i = 0; i < n; i++) {
        scanf("%d", &key);
        insert(hashTable, key);
    }

    display(hashTable);
    return 0;
}

// Output :
// Enter number of keys to insert: 5
// Enter keys:
// 25 37 18 55 22
// Hash Table:
// 0 --> NULL
// 1 --> NULL
// 2 --> 22
// 3 --> 55
// 4 --> NULL
// 5 --> 25
// 6 --> 37
// 7 --> 18
// 8 --> NULL
// 9 --> NULL

```

16.	Search an element in an array using linear and binary search.
```
// Aim : Search an element in an array using linear and binary search.
// Software used : Turbo C

// Program:
#include <stdio.h>

void linearSearch(int arr[], int n, int key) {
    int i, found = 0;
    for(i = 0; i < n; i++) {
        if(arr[i] == key) {
            printf("Linear Search: Element found at position %d\n", i + 1);
            found = 1;
            break;
        }
    }
    if(!found)
        printf("Linear Search: Element not found\n");
}

void binarySearch(int arr[], int n, int key) {
    int low = 0, high = n - 1, mid, found = 0;
    while(low <= high) {
        mid = (low + high) / 2;
        if(arr[mid] == key) {
            printf("Binary Search: Element found at position %d\n", mid + 1);
            found = 1;
            break;
        } else if(arr[mid] < key)
            low = mid + 1;
        else
            high = mid - 1;
    }
    if(!found)
        printf("Binary Search: Element not found\n");
}

int main() {
    int n, i, key;
    printf("Enter number of elements: ");
    scanf("%d", &n);

    int arr[n];
    printf("Enter elements in sorted order:\n");
    for(i = 0; i < n; i++)
        scanf("%d", &arr[i]);

    printf("Enter element to search: ");
    scanf("%d", &key);

    linearSearch(arr, n, key);
    binarySearch(arr, n, key);

    return 0;
}

// Output :
// Enter number of elements: 6
// Enter elements in sorted order:
// 5 10 15 20 25 30
// Enter element to search: 20
// Linear Search: Element found at position 4
// Binary Search: Element found at position 4

```

17.	Implement circular linked list with insertion at beginning and end.
```
// Aim : Implement circular linked list with insertion at beginning and end.  
// Software used : Turbo C

// Program:
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

struct Node *head = NULL;

void insertAtBeginning(int value) {
    struct Node *newNode = (struct Node *)malloc(sizeof(struct Node));
    newNode->data = value;

    if(head == NULL) {
        head = newNode;
        newNode->next = head;
    } else {
        struct Node *temp = head;
        while(temp->next != head)
            temp = temp->next;

        newNode->next = head;
        temp->next = newNode;
        head = newNode;
    }
    printf("%d inserted at beginning\n", value);
}

void insertAtEnd(int value) {
    struct Node *newNode = (struct Node *)malloc(sizeof(struct Node));
    newNode->data = value;

    if(head == NULL) {
        head = newNode;
        newNode->next = head;
    } else {
        struct Node *temp = head;
        while(temp->next != head)
            temp = temp->next;

        temp->next = newNode;
        newNode->next = head;
    }
    printf("%d inserted at end\n", value);
}

void display() {
    if(head == NULL) {
        printf("List is empty\n");
        return;
    }
    struct Node *temp = head;
    printf("Circular Linked List: ");
    do {
        printf("%d ", temp->data);
        temp = temp->next;
    } while(temp != head);
    printf("\n");
}

int main() {
    int choice, value;
    while(1) {
        printf("\n1. Insert at Beginning\n2. Insert at End\n3. Display\n4. Exit\nEnter your choice: ");
        scanf("%d", &choice);

        switch(choice) {
            case 1:
                printf("Enter value to insert: ");
                scanf("%d", &value);
                insertAtBeginning(value);
                break;
            case 2:
                printf("Enter value to insert: ");
                scanf("%d", &value);
                insertAtEnd(value);
                break;
            case 3:
                display();
                break;
            case 4:
                return 0;
            default:
                printf("Invalid choice\n");
        }
    }
}

// Output :
// 1. Insert at Beginning
// 2. Insert at End
// 3. Display
// 4. Exit
// Enter your choice: 1
// Enter value to insert: 10
// 10 inserted at beginning

// Enter your choice: 2
// Enter value to insert: 20
// 20 inserted at end

// Enter your choice: 2
// Enter value to insert: 30
// 30 inserted at end

// Enter your choice: 1
// Enter value to insert: 5
// 5 inserted at beginning

// Enter your choice: 3
// Circular Linked List: 5 10 20 30

// Enter your choice: 4

```

18.	Implement stack using linked list and evaluate a postfix expression.
```
// Aim : Implement stack using linked list and evaluate a postfix expression.   
// Software used : Turbo C

// Program:
#include <stdio.h>
#include <stdlib.h>
#include <ctype.h>
#include <string.h>

struct Node {
    int data;
    struct Node *next;
};

struct Node* top = NULL;

void push(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = top;
    top = newNode;
}

int pop() {
    if(top == NULL) {
        printf("Stack Underflow\n");
        return -1;
    }
    struct Node* temp = top;
    int value = temp->data;
    top = top->next;
    free(temp);
    return value;
}

int evaluatePostfix(char* expr) {
    int i, op1, op2, result;
    for(i = 0; expr[i] != '\0'; i++) {
        char ch = expr[i];
        if(isdigit(ch)) {
            push(ch - '0');
        } else {
            op2 = pop();
            op1 = pop();
            switch(ch) {
                case '+': result = op1 + op2; break;
                case '-': result = op1 - op2; break;
                case '*': result = op1 * op2; break;
                case '/': result = op1 / op2; break;
            }
            push(result);
        }
    }
    return pop();
}

int main() {
    char expr[100];
    printf("Enter postfix expression: ");
    scanf("%s", expr);

    int result = evaluatePostfix(expr);
    printf("Result of postfix expression: %d\n", result);

    return 0;
}

// Output :
// Enter postfix expression: 231*+9-
// Result of postfix expression: -4

```
19.	Implement queue using array and perform enqueue, dequeue, and display.
```
// Aim : Implement queue using array and perform enqueue, dequeue, and display.    
// Software used : Turbo C

// Program:
#include <stdio.h>
#define MAX 5

int queue[MAX];
int front = -1, rear = -1;

void enqueue(int value) {
    if(rear == MAX - 1) {
        printf("Queue Overflow\n");
        return;
    }
    if(front == -1)
        front = 0;
    rear++;
    queue[rear] = value;
    printf("%d inserted into queue\n", value);
}

void dequeue() {
    if(front == -1 || front > rear) {
        printf("Queue Underflow\n");
        return;
    }
    printf("%d deleted from queue\n", queue[front]);
    front++;
}

void display() {
    if(front == -1 || front > rear) {
        printf("Queue is empty\n");
        return;
    }
    printf("Queue elements are: ");
    for(int i = front; i <= rear; i++)
        printf("%d ", queue[i]);
    printf("\n");
}

int main() {
    int choice, value;
    while(1) {
        printf("\n1. Enqueue\n2. Dequeue\n3. Display\n4. Exit\nEnter your choice: ");
        scanf("%d", &choice);

        switch(choice) {
            case 1:
                printf("Enter value to insert: ");
                scanf("%d", &value);
                enqueue(value);
                break;
            case 2:
                dequeue();
                break;
            case 3:
                display();
                break;
            case 4:
                return 0;
            default:
                printf("Invalid choice\n");
        }
    }
}

// Output :
// 1. Enqueue
// 2. Dequeue
// 3. Display
// 4. Exit
// Enter your choice: 1
// Enter value to insert: 10
// 10 inserted into queue

// Enter your choice: 1
// Enter value to insert: 20
// 20 inserted into queue

// Enter your choice: 1
// Enter value to insert: 30
// 30 inserted into queue

// Enter your choice: 3
// Queue elements are: 10 20 30

// Enter your choice: 2
// 10 deleted from queue

// Enter your choice: 3
// Queue elements are: 20 30

// Enter your choice: 4

```
20.	Implement circular queue using array. 
```
// Aim : Implement circular queue using array.  
// Software used : Turbo C

// Program:
#include <stdio.h>
#define MAX 5

int queue[MAX];
int front = -1, rear = -1;

void enqueue(int value) {
    if((front == 0 && rear == MAX - 1) || (rear + 1) % MAX == front) {
        printf("Queue Overflow\n");
        return;
    }
    if(front == -1)
        front = rear = 0;
    else
        rear = (rear + 1) % MAX;
    queue[rear] = value;
    printf("%d inserted into circular queue\n", value);
}

void dequeue() {
    if(front == -1) {
        printf("Queue Underflow\n");
        return;
    }
    printf("%d deleted from circular queue\n", queue[front]);
    if(front == rear)
        front = rear = -1;
    else
        front = (front + 1) % MAX;
}

void display() {
    if(front == -1) {
        printf("Queue is empty\n");
        return;
    }
    printf("Circular Queue elements are: ");
    int i = front;
    while(1) {
        printf("%d ", queue[i]);
        if(i == rear)
            break;
        i = (i + 1) % MAX;
    }
    printf("\n");
}

int main() {
    int choice, value;
    while(1) {
        printf("\n1. Enqueue\n2. Dequeue\n3. Display\n4. Exit\nEnter your choice: ");
        scanf("%d", &choice);

        switch(choice) {
            case 1:
                printf("Enter value to insert: ");
                scanf("%d", &value);
                enqueue(value);
                break;
            case 2:
                dequeue();
                break;
            case 3:
                display();
                break;
            case 4:
                return 0;
            default:
                printf("Invalid choice\n");
        }
    }
}

// Output :
// 1. Enqueue
// 2. Dequeue
// 3. Display
// 4. Exit
// Enter your choice: 1
// Enter value to insert: 10
// 10 inserted into circular queue

// Enter your choice: 1
// Enter value to insert: 20
// 20 inserted into circular queue

// Enter your choice: 1
// Enter value to insert: 30
// 30 inserted into circular queue

// Enter your choice: 3
// Circular Queue elements are: 10 20 30

// Enter your choice: 2
// 10 deleted from circular queue

// Enter your choice: 3
// Circular Queue elements are: 20 30

// Enter your choice: 1
// Enter value to insert: 40
// 40 inserted into circular queue

// Enter your choice: 3
// Circular Queue elements are: 20 30 40

// Enter your choice: 4

```

21.	Create a binary tree and perform inorder, preorder, and postorder traversal.
```
// Aim : Create a binary tree and perform inorder, preorder, and postorder traversal.   
// Software used : Turbo C

// Program:
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* left;
    struct Node* right;
};

struct Node* createNode(int data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->left = newNode->right = NULL;
    return newNode;
}

void inorder(struct Node* root) {
    if(root != NULL) {
        inorder(root->left);
        printf("%d ", root->data);
        inorder(root->right);
    }
}

void preorder(struct Node* root) {
    if(root != NULL) {
        printf("%d ", root->data);
        preorder(root->left);
        preorder(root->right);
    }
}

void postorder(struct Node* root) {
    if(root != NULL) {
        postorder(root->left);
        postorder(root->right);
        printf("%d ", root->data);
    }
}

int main() {
    struct Node* root = createNode(1);
    root->left = createNode(2);
    root->right = createNode(3);
    root->left->left = createNode(4);
    root->left->right = createNode(5);

    printf("Inorder Traversal: ");
    inorder(root);
    printf("\n");

    printf("Preorder Traversal: ");
    preorder(root);
    printf("\n");

    printf("Postorder Traversal: ");
    postorder(root);
    printf("\n");

    return 0;
}

// Output :
// Inorder Traversal: 4 2 5 1 3
// Preorder Traversal: 1 2 4 5 3
// Postorder Traversal: 4 5 2 3 1

```
22.	Implement binary search tree with insertion and deletion operations.
```
// Aim : Implement binary search tree with insertion and deletion operations.    
// Software used : Turbo C

// Program:
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* left;
    struct Node* right;
};

struct Node* createNode(int data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->left = newNode->right = NULL;
    return newNode;
}

struct Node* insert(struct Node* root, int data) {
    if(root == NULL)
        return createNode(data);
    if(data < root->data)
        root->left = insert(root->left, data);
    else if(data > root->data)
        root->right = insert(root->right, data);
    return root;
}

struct Node* minValueNode(struct Node* node) {
    struct Node* current = node;
    while(current && current->left != NULL)
        current = current->left;
    return current;
}

struct Node* deleteNode(struct Node* root, int key) {
    if(root == NULL)
        return root;

    if(key < root->data)
        root->left = deleteNode(root->left, key);
    else if(key > root->data)
        root->right = deleteNode(root->right, key);
    else {
        if(root->left == NULL) {
            struct Node* temp = root->right;
            free(root);
            return temp;
        } else if(root->right == NULL) {
            struct Node* temp = root->left;
            free(root);
            return temp;
        }
        struct Node* temp = minValueNode(root->right);
        root->data = temp->data;
        root->right = deleteNode(root->right, temp->data);
    }
    return root;
}

void inorder(struct Node* root) {
    if(root != NULL) {
        inorder(root->left);
        printf("%d ", root->data);
        inorder(root->right);
    }
}

int main() {
    struct Node* root = NULL;
    int choice, value;

    while(1) {
        printf("\n1. Insert\n2. Delete\n3. Inorder Traversal\n4. Exit\nEnter your choice: ");
        scanf("%d", &choice);

        switch(choice) {
            case 1:
                printf("Enter value to insert: ");
                scanf("%d", &value);
                root = insert(root, value);
                break;
            case 2:
                printf("Enter value to delete: ");
                scanf("%d", &value);
                root = deleteNode(root, value);
                break;
            case 3:
                printf("Inorder Traversal: ");
                inorder(root);
                printf("\n");
                break;
            case 4:
                return 0;
            default:
                printf("Invalid choice\n");
        }
    }
}

// Output :
// 1. Insert
// 2. Delete
// 3. Inorder Traversal
// 4. Exit
// Enter your choice: 1
// Enter value to insert: 50

// Enter your choice: 1
// Enter value to insert: 30

// Enter your choice: 1
// Enter value to insert: 70

// Enter your choice: 1
// Enter value to insert: 20

// Enter your choice: 1
// Enter value to insert: 40

// Enter your choice: 3
// Inorder Traversal: 20 30 40 50 70

// Enter your choice: 2
// Enter value to delete: 30

// Enter your choice: 3
// Inorder Traversal: 20 40 50 70

// Enter your choice: 4

```

23.	Construct an AVL tree and perform rotations to maintain balance.
```
// Aim : Construct an AVL tree and perform rotations to maintain balance.    
// Software used : Turbo C

// Program:
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* left;
    struct Node* right;
    int height;
};

int max(int a, int b) {
    return (a > b) ? a : b;
}

int height(struct Node* node) {
    if(node == NULL) return 0;
    return node->height;
}

struct Node* createNode(int data) {
    struct Node* node = (struct Node*)malloc(sizeof(struct Node));
    node->data = data;
    node->left = node->right = NULL;
    node->height = 1;
    return node;
}

struct Node* rightRotate(struct Node* y) {
    struct Node* x = y->left;
    struct Node* T2 = x->right;

    x->right = y;
    y->left = T2;

    y->height = max(height(y->left), height(y->right)) + 1;
    x->height = max(height(x->left), height(x->right)) + 1;

    return x;
}

struct Node* leftRotate(struct Node* x) {
    struct Node* y = x->right;
    struct Node* T2 = y->left;

    y->left = x;
    x->right = T2;

    x->height = max(height(x->left), height(x->right)) + 1;
    y->height = max(height(y->left), height(y->right)) + 1;

    return y;
}

int getBalance(struct Node* node) {
    if(node == NULL) return 0;
    return height(node->left) - height(node->right);
}

struct Node* insert(struct Node* node, int key) {
    if(node == NULL)
        return createNode(key);

    if(key < node->data)
        node->left = insert(node->left, key);
    else if(key > node->data)
        node->right = insert(node->right, key);
    else
        return node;

    node->height = 1 + max(height(node->left), height(node->right));
    int balance = getBalance(node);

    if(balance > 1 && key < node->left->data)
        return rightRotate(node);

    if(balance < -1 && key > node->right->data)
        return leftRotate(node);

    if(balance > 1 && key > node->left->data) {
        node->left = leftRotate(node->left);
        return rightRotate(node);
    }

    if(balance < -1 && key < node->right->data) {
        node->right = rightRotate(node->right);
        return leftRotate(node);
    }

    return node;
}

void inorder(struct Node* root) {
    if(root != NULL) {
        inorder(root->left);
        printf("%d ", root->data);
        inorder(root->right);
    }
}

int main() {
    struct Node* root = NULL;
    int n, value;

    printf("Enter number of elements to insert: ");
    scanf("%d", &n);

    printf("Enter elements:\n");
    for(int i = 0; i < n; i++) {
        scanf("%d", &value);
        root = insert(root, value);
    }

    printf("Inorder traversal of AVL tree: ");
    inorder(root);
    printf("\n");

    return 0;
}

// Output :
// Enter number of elements to insert: 7
// Enter elements:
// 10 20 30 40 50 25 5
// Inorder traversal of AVL tree: 5 10 20 25 30 40 50

```
24.	Count leaf nodes, internal nodes, and height of a binary tree.
```
// Aim : Count leaf nodes, internal nodes, and height of a binary tree.    
// Software used : Turbo C

// Program:
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* left;
    struct Node* right;
};

struct Node* createNode(int data) {
    struct Node* node = (struct Node*)malloc(sizeof(struct Node));
    node->data = data;
    node->left = node->right = NULL;
    return node;
}

int countLeafNodes(struct Node* root) {
    if(root == NULL) return 0;
    if(root->left == NULL && root->right == NULL) return 1;
    return countLeafNodes(root->left) + countLeafNodes(root->right);
}

int countInternalNodes(struct Node* root) {
    if(root == NULL || (root->left == NULL && root->right == NULL)) return 0;
    return 1 + countInternalNodes(root->left) + countInternalNodes(root->right);
}

int height(struct Node* root) {
    if(root == NULL) return 0;
    int leftHeight = height(root->left);
    int rightHeight = height(root->right);
    return 1 + (leftHeight > rightHeight ? leftHeight : rightHeight);
}

int main() {
    struct Node* root = createNode(1);
    root->left = createNode(2);
    root->right = createNode(3);
    root->left->left = createNode(4);
    root->left->right = createNode(5);

    printf("Leaf nodes: %d\n", countLeafNodes(root));
    printf("Internal nodes: %d\n", countInternalNodes(root));
    printf("Height of tree: %d\n", height(root));

    return 0;
}

// Output :
// Leaf nodes: 3
// Internal nodes: 2
// Height of tree: 3

```
25.	Do any one of the following:
    a.	Implement insertion sort.
    b.	Implement selection sort.
    c.	Implement merge sort.
    d.	Implement quick sort.
    e.	Implement radix sort for positive integers.

```
// Aim : a.Implement insertion sort.    
// Software used : Turbo C

// Program:
#include <stdio.h>

int main() {
    int n, i, j, key;
    printf("Enter number of elements: ");
    scanf("%d", &n);

    int arr[100];
    printf("Enter elements:\n");
    for(i = 0; i < n; i++)
        scanf("%d", &arr[i]);

    for(i = 1; i < n; i++) {
        key = arr[i];
        j = i - 1;
        while(j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            j--;
        }
        arr[j + 1] = key;
    }

    printf("Sorted array: ");
    for(i = 0; i < n; i++)
        printf("%d ", arr[i]);
    printf("\n");

    return 0;
}

// Output :
// Enter number of elements: 6
// Enter elements:
// 12 11 13 5 6 7
// Sorted array: 5 6 7 11 12 13

```

26.	Represent a graph using adjacency matrix and adjacency list.
```
// Aim : Represent a graph using adjacency matrix and adjacency list.    
// Software used : Turbo C

// Program:
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int vertex;
    struct Node* next;
};

struct GraphList {
    int numVertices;
    struct Node** adjLists;
};

struct Node* createNode(int v) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->vertex = v;
    newNode->next = NULL;
    return newNode;
}

struct GraphList* createGraphList(int vertices) {
    struct GraphList* graph = (struct GraphList*)malloc(sizeof(struct GraphList));
    graph->numVertices = vertices;
    graph->adjLists = (struct Node**)malloc(vertices * sizeof(struct Node*));

    for(int i = 0; i < vertices; i++)
        graph->adjLists[i] = NULL;

    return graph;
}

void addEdgeList(struct GraphList* graph, int src, int dest) {
    struct Node* newNode = createNode(dest);
    newNode->next = graph->adjLists[src];
    graph->adjLists[src] = newNode;

    newNode = createNode(src);
    newNode->next = graph->adjLists[dest];
    graph->adjLists[dest] = newNode;
}

void printAdjList(struct GraphList* graph) {
    printf("Adjacency List:\n");
    for(int i = 0; i < graph->numVertices; i++) {
        struct Node* temp = graph->adjLists[i];
        printf("%d: ", i);
        while(temp) {
            printf("%d ", temp->vertex);
            temp = temp->next;
        }
        printf("\n");
    }
}

void printAdjMatrix(int vertices, int matrix[vertices][vertices]) {
    printf("Adjacency Matrix:\n");
    for(int i = 0; i < vertices; i++) {
        for(int j = 0; j < vertices; j++)
            printf("%d ", matrix[i][j]);
        printf("\n");
    }
}

int main() {
    int vertices, edges;
    printf("Enter number of vertices: ");
    scanf("%d", &vertices);

    int adjMatrix[vertices][vertices];
    for(int i = 0; i < vertices; i++)
        for(int j = 0; j < vertices; j++)
            adjMatrix[i][j] = 0;

    struct GraphList* graph = createGraphList(vertices);

    printf("Enter number of edges: ");
    scanf("%d", &edges);

    printf("Enter edges (source destination):\n");
    for(int i = 0; i < edges; i++) {
        int src, dest;
        scanf("%d %d", &src, &dest);
        adjMatrix[src][dest] = 1;
        adjMatrix[dest][src] = 1;
        addEdgeList(graph, src, dest);
    }

    printAdjMatrix(vertices, adjMatrix);
    printAdjList(graph);

    return 0;
}

// Output :
// Enter number of vertices: 4
// Enter number of edges: 4
// Enter edges (source destination):
// 0 1
// 0 2
// 1 2
// 2 3
// Adjacency Matrix:
// 0 1 1 0
// 1 0 1 0
// 1 1 0 1
// 0 0 1 0
// Adjacency List:
// 0: 2 1
// 1: 2 0
// 2: 3 1 0
// 3: 2

```
27.	Implement BFS and DFS traversal on a graph.
```
// Aim : Implement BFS and DFS traversal on a graph.    
// Software used : Turbo C

// Program:
#include <stdio.h>
#include <stdlib.h>

#define MAX 100

int visited[MAX];

void DFS(int n, int adjMatrix[MAX][MAX], int start) {
    visited[start] = 1;
    printf("%d ", start);
    for(int i = 0; i < n; i++) {
        if(adjMatrix[start][i] && !visited[i])
            DFS(n, adjMatrix, i);
    }
}

void BFS(int n, int adjMatrix[MAX][MAX], int start) {
    int queue[MAX], front = 0, rear = 0;
    for(int i = 0; i < n; i++)
        visited[i] = 0;

    queue[rear++] = start;
    visited[start] = 1;

    while(front < rear) {
        int curr = queue[front++];
        printf("%d ", curr);
        for(int i = 0; i < n; i++) {
            if(adjMatrix[curr][i] && !visited[i]) {
                queue[rear++] = i;
                visited[i] = 1;
            }
        }
    }
}

int main() {
    int n, edges;
    printf("Enter number of vertices: ");
    scanf("%d", &n);

    int adjMatrix[MAX][MAX];
    for(int i = 0; i < n; i++)
        for(int j = 0; j < n; j++)
            adjMatrix[i][j] = 0;

    printf("Enter number of edges: ");
    scanf("%d", &edges);

    printf("Enter edges (source destination):\n");
    for(int i = 0; i < edges; i++) {
        int u, v;
        scanf("%d %d", &u, &v);
        adjMatrix[u][v] = 1;
        adjMatrix[v][u] = 1;
    }

    printf("DFS traversal starting from vertex 0: ");
    for(int i = 0; i < n; i++)
        visited[i] = 0;
    DFS(n, adjMatrix, 0);
    printf("\n");

    printf("BFS traversal starting from vertex 0: ");
    BFS(n, adjMatrix, 0);
    printf("\n");

    return 0;
}

// Output :
// Enter number of vertices: 4
// Enter number of edges: 4
// Enter edges (source destination):
// 0 1
// 0 2
// 1 2
// 2 3
// DFS traversal starting from vertex 0: 0 1 2 3
// BFS traversal starting from vertex 0: 0 1 2 3

```
28.	Do any one of the following:
    a.	Find shortest path using Dijkstra’s algorithm.
    b.	Find minimum cost spanning tree using Kruskal’s algorithm.
    c.	Compute all-pairs shortest paths using Floyd-Warshall algorithm.

```
// Aim : a.Find shortest path using Dijkstra’s algorithm.    
// Software used : Turbo C

// Program:
#include <stdio.h>
#include <limits.h>

#define MAX 100

int minDistance(int dist[], int visited[], int n) {
    int min = INT_MAX, min_index;
    for(int i = 0; i < n; i++) {
        if(!visited[i] && dist[i] <= min) {
            min = dist[i];
            min_index = i;
        }
    }
    return min_index;
}

void dijkstra(int n, int graph[MAX][MAX], int src) {
    int dist[MAX], visited[MAX];

    for(int i = 0; i < n; i++) {
        dist[i] = INT_MAX;
        visited[i] = 0;
    }
    dist[src] = 0;

    for(int count = 0; count < n - 1; count++) {
        int u = minDistance(dist, visited, n);
        visited[u] = 1;

        for(int v = 0; v < n; v++) {
            if(!visited[v] && graph[u][v] && dist[u] != INT_MAX &&
               dist[u] + graph[u][v] < dist[v])
                dist[v] = dist[u] + graph[u][v];
        }
    }

    printf("Vertex\tDistance from Source\n");
    for(int i = 0; i < n; i++)
        printf("%d\t%d\n", i, dist[i]);
}

int main() {
    int n;
    printf("Enter number of vertices: ");
    scanf("%d", &n);

    int graph[MAX][MAX];
    printf("Enter adjacency matrix (0 for no edge):\n");
    for(int i = 0; i < n; i++)
        for(int j = 0; j < n; j++)
            scanf("%d", &graph[i][j]);

    int src;
    printf("Enter source vertex: ");
    scanf("%d", &src);

    dijkstra(n, graph, src);

    return 0;
}

// Output :
// Enter number of vertices: 5
// Enter adjacency matrix (0 for no edge):
// 0 10 0 30 100
// 10 0 50 0 0
// 0 50 0 20 10
// 30 0 20 0 60
// 100 0 10 60 0
// Enter source vertex: 0
// Vertex	Distance from Source
// 0	0
// 1	10
// 2	60
// 3	30
// 4	70

```
29.	Implement hashing with linear probing.
```
// Aim : Implement hashing with linear probing.    
// Software used : Turbo C

// Program:
#include <stdio.h>
#define SIZE 10

int hash(int key) {
    return key % SIZE;
}

void insert(int hashTable[], int key) {
    int index = hash(key);
    int i = 0;

    while(hashTable[(index + i) % SIZE] != -1)
        i++;

    hashTable[(index + i) % SIZE] = key;
}

void display(int hashTable[]) {
    printf("Hash Table:\n");
    for(int i = 0; i < SIZE; i++) {
        if(hashTable[i] != -1)
            printf("%d --> %d\n", i, hashTable[i]);
        else
            printf("%d --> NULL\n", i);
    }
}

int main() {
    int hashTable[SIZE];
    int n, key;

    for(int i = 0; i < SIZE; i++)
        hashTable[i] = -1;

    printf("Enter number of keys to insert: ");
    scanf("%d", &n);

    printf("Enter keys:\n");
    for(int i = 0; i < n; i++) {
        scanf("%d", &key);
        insert(hashTable, key);
    }

    display(hashTable);

    return 0;
}

// Output :
// Enter number of keys to insert: 5
// Enter keys:
// 25 37 18 55 22
// Hash Table:
// 0 --> NULL
// 1 --> NULL
// 2 --> 22
// 3 --> 55
// 4 --> NULL
// 5 --> 25
// 6 --> 37
// 7 --> 18
// 8 --> NULL
// 9 --> NULL

```

# List of Practical’s: CSO 
1. Implement a C/ C++ program to convert binary number to decimal number vice versa.
```
// Aim : Implement a C/ C++ program to convert binary number to decimal number vice versa.    
// Software used : Turbo C

// Program:
#include <stdio.h>

int binaryToDecimal(long long binary) {
    int decimal = 0, base = 1, lastDigit;
    while(binary > 0) {
        lastDigit = binary % 10;
        decimal += lastDigit * base;
        base *= 2;
        binary /= 10;
    }
    return decimal;
}

long long decimalToBinary(int decimal) {
    long long binary = 0;
    int remainder, factor = 1;
    while(decimal > 0) {
        remainder = decimal % 2;
        binary += remainder * factor;
        decimal /= 2;
        factor *= 10;
    }
    return binary;
}

int main() {
    int choice;
    printf("1. Binary to Decimal\n2. Decimal to Binary\nEnter your choice: ");
    scanf("%d", &choice);

    if(choice == 1) {
        long long binary;
        printf("Enter binary number: ");
        scanf("%lld", &binary);
        printf("Decimal equivalent: %d\n", binaryToDecimal(binary));
    } else if(choice == 2) {
        int decimal;
        printf("Enter decimal number: ");
        scanf("%d", &decimal);
        printf("Binary equivalent: %lld\n", decimalToBinary(decimal));
    } else {
        printf("Invalid choice\n");
    }

    return 0;
}

// Output :
// 1. Binary to Decimal
// 2. Decimal to Binary
// Enter your choice: 1
// Enter binary number: 1011
// Decimal equivalent: 11

```

2. Implement a C/ C++ program to convert Hexadecimal number to decimal number
```
// Aim : Implement a C/ C++ program to convert Hexadecimal number to decimal number    
// Software used : Turbo C

// Program:
#include <stdio.h>
#include <string.h>
#include <math.h>

int hexToDecimal(char hex[]) {
    int length = strlen(hex);
    int decimal = 0, power = 0;

    for(int i = length - 1; i >= 0; i--) {
        char ch = hex[i];
        int value;

        if(ch >= '0' && ch <= '9')
            value = ch - '0';
        else if(ch >= 'A' && ch <= 'F')
            value = ch - 'A' + 10;
        else if(ch >= 'a' && ch <= 'f')
            value = ch - 'a' + 10;
        else
            value = 0;

        decimal += value * pow(16, power);
        power++;
    }
    return decimal;
}

int main() {
    char hex[20];
    printf("Enter hexadecimal number: ");
    scanf("%s", hex);

    printf("Decimal equivalent: %d\n", hexToDecimal(hex));

    return 0;
}

// Output :
// Enter hexadecimal number: 1A3
// Decimal equivalent: 419

```
3. Implement a C/ C++ program to perform Binary Addition and Subtraction.
```
// Aim : Implement a C/ C++ program to perform Binary Addition and Subtraction.   
// Software used : Turbo C

// Program:
#include <stdio.h>
#include <string.h>
#include <stdlib.h>

int binaryToDecimal(char bin[]) {
    int decimal = 0;
    for(int i = 0; bin[i]; i++) {
        decimal = decimal * 2 + (bin[i] - '0');
    }
    return decimal;
}

void decimalToBinary(int decimal) {
    if(decimal == 0) {
        printf("0\n");
        return;
    }
    char bin[100];
    int i = 0;
    while(decimal > 0) {
        bin[i++] = (decimal % 2) + '0';
        decimal /= 2;
    }
    for(int j = i - 1; j >= 0; j--)
        printf("%c", bin[j]);
    printf("\n");
}

int main() {
    char bin1[100], bin2[100];
    int choice;
    printf("1. Binary Addition\n2. Binary Subtraction\nEnter your choice: ");
    scanf("%d", &choice);

    printf("Enter first binary number: ");
    scanf("%s", bin1);
    printf("Enter second binary number: ");
    scanf("%s", bin2);

    int dec1 = binaryToDecimal(bin1);
    int dec2 = binaryToDecimal(bin2);

    if(choice == 1) {
        printf("Binary addition result: ");
        decimalToBinary(dec1 + dec2);
    } else if(choice == 2) {
        printf("Binary subtraction result: ");
        decimalToBinary(abs(dec1 - dec2));
    } else {
        printf("Invalid choice\n");
    }

    return 0;
}

// Output :
// 1. Binary Addition
// 2. Binary Subtraction
// Enter your choice: 1
// Enter first binary number: 1011
// Enter second binary number: 1101
// Binary addition result: 11000

```

4. Implement Logic gates using NAND gates
```
// Aim : Implement Logic gates using NAND gates    
// Software used : Turbo C

// Program:
#include <stdio.h>

int NAND(int a, int b) {
    return !(a && b);
}

int NOT(int a) {
    return NAND(a, a);
}

int AND(int a, int b) {
    return NOT(NAND(a, b));
}

int OR(int a, int b) {
    return NAND(NOT(a), NOT(b));
}

int XOR(int a, int b) {
    return AND(OR(a, b), NAND(a, b));
}

int main() {
    int a, b;
    printf("Enter first input (0 or 1): ");
    scanf("%d", &a);
    printf("Enter second input (0 or 1): ");
    scanf("%d", &b);

    printf("Using NAND gates:\n");
    printf("NOT %d = %d\n", a, NOT(a));
    printf("%d AND %d = %d\n", a, b, AND(a, b));
    printf("%d OR %d = %d\n", a, b, OR(a, b));
    printf("%d XOR %d = %d\n", a, b, XOR(a, b));

    return 0;
}

// Output :
// Enter first input (0 or 1): 1
// Enter second input (0 or 1): 0
// Using NAND gates:
// NOT 1 = 0
// 1 AND 0 = 0
// 1 OR 0 = 1
// 1 XOR 0 = 1

```

5. Implement Logic gates using NOR gates.
```
// Aim : Implement Logic gates using NOR gates.   
// Software used : Turbo C

// Program:
#include <stdio.h>

int NOR(int a, int b) {
    return !(a || b);
}

int NOT(int a) {
    return NOR(a, a);
}

int OR(int a, int b) {
    return NOT(NOR(a, b));
}

int AND(int a, int b) {
    return NOR(NOT(a), NOT(b));
}

int XOR(int a, int b) {
    return AND(OR(a, b), NOR(a, b));
}

int main() {
    int a, b;
    printf("Enter first input (0 or 1): ");
    scanf("%d", &a);
    printf("Enter second input (0 or 1): ");
    scanf("%d", &b);

    printf("Using NOR gates:\n");
    printf("NOT %d = %d\n", a, NOT(a));
    printf("%d AND %d = %d\n", a, b, AND(a, b));
    printf("%d OR %d = %d\n", a, b, OR(a, b));
    printf("%d XOR %d = %d\n", a, b, XOR(a, b));

    return 0;
}

// Output :
// Enter first input (0 or 1): 1
// Enter second input (0 or 1): 0
// Using NOR gates:
// NOT 1 = 0
// 1 AND 0 = 0
// 1 OR 0 = 1
// 1 XOR 0 = 1

```
6. Design and implement the 8:1 MUX using gates /ICs.
```
// Aim : Design and implement the 8:1 MUX using gates /ICs.   
// Software used : Turbo C

// Program:
#include <stdio.h>

int main() {
    int inputs[8], s0, s1, s2, output;
    printf("Enter 8 data inputs (0 or 1): ");
    for(int i = 0; i < 8; i++)
        scanf("%d", &inputs[i]);

    printf("Enter select lines s2 s1 s0 (0 or 1): ");
    scanf("%d %d %d", &s2, &s1, &s0);

    int select = (s2 << 2) | (s1 << 1) | s0;
    output = inputs[select];

    printf("Output of 8:1 MUX = %d\n", output);

    return 0;
}

// Output :
// Enter 8 data inputs (0 or 1): 1 0 1 0 1 0 1 0
// Enter select lines s2 s1 s0 (0 or 1): 1 0 1
// Output of 8:1 MUX = 0

```
7. Design and implement the 4:1 MUX using gates /ICs.
```
// Aim : Design and implement the 8:1 MUX using gates /ICs.   
// Software used : Turbo C

// Program:

#include <stdio.h>

int NOT(int a) {
    return a ? 0 : 1;
}

int AND(int a, int b) {
    return a & b;
}

int OR(int a, int b) {
    return a | b;
}

int mux4to1(int i0, int i1, int i2, int i3, int s0, int s1) {
    int ns0 = NOT(s0);
    int ns1 = NOT(s1);

    int y0 = AND(i0, AND(ns1, ns0));
    int y1 = AND(i1, AND(ns1, s0));
    int y2 = AND(i2, AND(s1, ns0));
    int y3 = AND(i3, AND(s1, s0));

    return OR(OR(y0, y1), OR(y2, y3));
}

int main() {
    int i0, i1, i2, i3, s0, s1;

    printf("Enter inputs i0 i1 i2 i3: ");
    scanf("%d %d %d %d", &i0, &i1, &i2, &i3);

    printf("Enter select lines s0 s1: ");
    scanf("%d %d", &s0, &s1);

    int output = mux4to1(i0, i1, i2, i3, s0, s1);

    printf("Output of 4:1 MUX = %d\n", output);

    return 0;
}


// Output :
// Enter inputs i0 i1 i2 i3: 1 0 1 1
// Enter select lines s0 s1: 0 1
// Output of 4:1 MUX = 1

```
8. Design a Full adder using gates.
```
// Aim : Design a Full adder using gates.  
// Software used : Turbo C

// Program:
#include <stdio.h>

int AND(int a, int b) { return a && b; }
int OR(int a, int b) { return a || b; }
int XOR(int a, int b) { return a != b; }

int main() {
    int A, B, Cin;
    printf("Enter input A (0 or 1): ");
    scanf("%d", &A);
    printf("Enter input B (0 or 1): ");
    scanf("%d", &B);
    printf("Enter carry input Cin (0 or 1): ");
    scanf("%d", &Cin);

    int Sum = XOR(XOR(A, B), Cin);
    int Cout = OR(OR(AND(A, B), AND(B, Cin)), AND(A, Cin));

    printf("Sum = %d\n", Sum);
    printf("Carry Out (Cout) = %d\n", Cout);

    return 0;
}

// Output :
// Enter input A (0 or 1): 1
// Enter input B (0 or 1): 0
// Enter carry input Cin (0 or 1): 1
// Sum = 0
// Carry Out (Cout) = 1

```

9. Write 8085 Program 8-bit addition and subtraction.
```
// Aim : Write 8085 Program 8-bit addition and subtraction.   
// Software used : Turbo C

// Program:
#include <stdio.h>
#include <stdint.h>

int main() {
    uint8_t A, B, sum, diff;

    printf("Enter first 8-bit number (0-255): ");
    scanf("%hhu", &A);

    printf("Enter second 8-bit number (0-255): ");
    scanf("%hhu", &B);

    sum = A + B;
    diff = A - B;

    printf("8-bit Addition: %d + %d = %d\n", A, B, sum);
    printf("8-bit Subtraction: %d - %d = %d\n", A, B, diff);

    return 0;
}

// Output :
// Enter first 8-bit number (0-255): 37
// Enter second 8-bit number (0-255): 23
// 8-bit Addition: 37 + 23 = 60
// 8-bit Subtraction: 37 - 23 = 14

```
