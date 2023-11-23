#include <iostream>
using namespace std;

const int MAX_SIZE = 6;

class Stack {
private:
    int arr[MAX_SIZE];
    int top;

public:
    Stack() : top(-1) {}

    void push(int element) {
        if (top == MAX_SIZE - 1) {
            cout << "Stack Overflow: Cannot push more elements." << endl;
            return;
        }
        arr[++top] = element;
        cout << "Pushed " << element << " onto the stack." << endl;
    }

    void pop() {
        if (top == -1) {
            cout << "Stack Underflow: Cannot pop from an empty stack." << endl;
            return;
        }
        cout << "Popped " << arr[top--] << " from the stack." << endl;
    }

    void display() {
        if (top == -1) {
            cout << "Stack is empty." << endl;
            return;
        }
        cout << "Elements in the stack: ";
        for (int i = 0; i <= top; ++i) {
            cout << arr[i] << " ";
        }
        cout << endl;
    }

    void topElement() {
        if (top == -1) {
            cout << "Stack is empty." << endl;
            return;
        }
        cout << "Top element: " << arr[top] << endl;
    }
};

int main() {
    Stack stack;
    int choice;

    do {
        cout << "\nPlease Enter Your Choice:\n1. Push an element\n2. Pop an element\n3. Display all\n4. Top element\n5. Exit\n";
        cin >> choice;

        switch (choice) {
            case 1: {
                int element;
                cout << "Enter element to push: ";
                cin >> element;
                stack.push(element);
                break;
            }
            case 2:
                stack.pop();
                break;
            case 3:
                stack.display();
                break;
            case 4:
                stack.topElement();
                break;
            case 5:
                cout << "Exiting program." << endl;
                break;
            default:
                cout << "Invalid choice. Please try again." << endl;
        }

    } while (choice != 5);

    return 0;
}
