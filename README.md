# Stack
Stacks operations
#include <iostream>
using namespace std;
#define MAX 5 // Maximum size of the stack
class Stack {
private:
int arr[MAX];  // Array to hold the stack elements
int top;
// Index of the top element in the stack
public:
    // Constructor to initialize the stack
    Stack() {
        top = -1;  // Stack is initially empty
    }
    // Push operation to add an element to the stack
    void push(int value) {
        if (top >= MAX - 1) {
            cout << "Stack Overflow! Cannot push " << value << endl;
        } else {
            top++;
            arr[top] = value;
            cout << value << " pushed into stack." << endl;
        }
    }
    // Pop operation to remove the top element from the stack
    void pop() {
        if (top < 0) {
            cout << "Stack Underflow! No element to pop." << endl;
        } else {
            cout << arr[top] << " popped from stack." << endl;
            top--;
        }
    }
    // Display operation to show all the elements of the stack
    void display() {
        if (top < 0) {
            cout << "Stack is empty!" << endl;
        } else {
            cout << "Stack elements: ";
            for (int i = 0; i <= top; i++) {
                cout << arr[i] << " ";
            }
            cout << endl;
        }
    }
};
int main() {
    Stack stack;
    int choice, value;
    do {
        cout << "\n1. Push\n2. Pop\n3. Display\n4. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;
        switch (choice) {
        case 1:
            cout << "Enter value to push: ";
            cin >> value;
            stack.push(value);
            break;
        case 2:
            stack.pop();
            break;
        case 3:
            stack.display();
            break;
        case 4:
            cout << "Exiting..." << endl;
            break;
        default:
            cout << "Invalid choice! Please enter again." << endl;
        }
    } while (choice != 4);
    return 0;
}
