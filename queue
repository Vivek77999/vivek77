#include <stdio.h>
#define MAX 5   // Maximum size of queue

int queue[MAX];
int front = -1, rear = -1;

// Enqueue operation
void enqueue() {
    int value;

    // Check overflow
    if ((front == 0 && rear == MAX - 1) || (front == rear + 1)) {
        printf("Queue Overflow! Cannot insert.\n");
        return;
    }

    printf("Enter value to enqueue: ");
    scanf("%d", &value);

    // First element
    if (front == -1) {
        front = rear = 0;
    }
    // Circular condition
    else if (rear == MAX - 1) {
        rear = 0;
    }
    else {
        rear++;
    }

    queue[rear] = value;
    printf("%d inserted into queue.\n", value);
}

// Dequeue operation
void dequeue() {
    if (front == -1) {
        printf("Queue Underflow! Queue is empty.\n");
        return;
    }

    printf("Deleted element: %d\n", queue[front]);

    // Only one element
    if (front == rear) {
        front = rear = -1;
    }
    // Circular condition
    else if (front == MAX - 1) {
        front = 0;
    }
    else {
        front++;
    }
}

// Display queue
void display() {
    if (front == -1) {
        printf("Queue is empty.\n");
        return;
    }

    printf("Queue elements are:\n");

    if (rear >= front) {
        for (int i = front; i <= rear; i++) {
            printf("%d\n", queue[i]);
        }
    } else {
        for (int i = front; i < MAX; i++) {
            printf("%d\n", queue[i]);
        }
        for (int i = 0; i <= rear; i++) {
            printf("%d\n", queue[i]);
        }
    }
}

// Main function
int main() {
    int choice;

    while (1) {
        printf("\n--- Circular Queue Menu ---\n");
        printf("1. Enqueue\n");
        printf("2. Dequeue\n");
        printf("3. Display\n");
        printf("4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1: enqueue(); break;
            case 2: dequeue(); break;
            case 3: display(); break;
            case 4: printf("Exiting...\n"); return 0;
            default: printf("Invalid choice!\n");
        }
    }
}
