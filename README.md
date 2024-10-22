# Experiment-18  

### Aim 
To study and implement Stack implementation in C++ using array. <br> 
Menu options - <ol><li> Push </li> <li> Pop </li> <li>Display</li><li>Exit</li></ol>

### Software 
Visual Studio Code 

### Theory 
A <b>Stack</b> is an abstract data stucture that contains a collection of elements. Stack implements the <b>LIFO</b> (Last In First Out) mechanism i.e., the element that is pushed at the end is popped out first. Some of the principle operations in the stack are - <ol><li>Push - This adds a data value to the top[ of the stack.</li><li>Pop - This removes the data value on the top of the stack.</li><li>Peek - This returns the top value of the stack.</li><li>IsEmpty: Checking if the stack is empty.</li><li>IsFull (when implemented using arrays): Checking if the stack has reached its maximum capacity.</li></ol>    

### Code
(A) 
```
// NAME - SHREY RAJ
// PRN - 23070123123
// EXPERIMENT - 18(A) 

// STACK 

#include<iostream>
using namespace std;

int stack[100], n = 100, top = -1;

void push(int val) {
    if (top >= n - 1) {  // Correct condition for Stack Overflow
        cout << "Stack Overflow" << endl;
    } else {
        top++;
        stack[top] = val;
    }
}

void pop() {
    if (top <= -1) {
        cout << "Stack Underflow" << endl;
    } else {
        cout << "The popped element is " << stack[top] << endl;
        top--;
    }
}

void display() {
    if (top >= 0) {
        cout << "Stack elements are: ";
        for (int i = top; i >= 0; i--)
            cout << stack[i] << " ";
        cout << endl;
    } else {
        cout << "Stack is empty" << endl;
    }
}

int main() {
    int ch, val;
    cout << "(1) Push in Stack" << endl;
    cout << "(2) Pop from Stack" << endl;
    cout << "(3) Display Stack" << endl;
    cout << "(4) Exit" << endl;

    do {
        cout << "Enter Choice: " << endl;
        cin >> ch;
        switch (ch) {
            case 1:
                cout << "Enter value to be pushed: " << endl;
                cin >> val;
                push(val);
                break;
            case 2:
                pop();
                break;
            case 3:
                display();
                break;
            case 4:
                cout << "Exit" << endl;
                break;
            default:
                cout << "Invalid Choice." << endl;
        }
    } while (ch != 4);

    return 0;
}
```

(B) 
```
// NAME - SHREY RAJ 
// PRN - 23070123123
// EXPERIMENT - 18(B) 

// STACK 

#include <iostream>
using namespace std;

#define SIZE 5
#define ERROR -9999

class Stack {
    int top;
    int ar[SIZE];
public:
    Stack() {
        top = -1;
    }
    void push(int num);
    int pop();
    int peak();
    void disp();
};

void Stack::push(int num) {
    if (top == SIZE - 1) {
        cout << "STACK OVERFLOW: STACK IS FULL" << endl;
        return;
    }
    ar[++top] = num;
}

int Stack::pop() {
    if (top == -1) {
        cout << "STACK UNDERFLOW: STACK IS EMPTY" << endl;
        return ERROR;
    }
    return ar[top--];
}

int Stack::peak() {
    if (top == -1) {
        cout << "STACK UNDERFLOW: STACK IS EMPTY" << endl;
        return ERROR;
    }
    return ar[top];
}

void Stack::disp() {
    if (top == -1) {
        cout << "STACK UNDERFLOW: STACK IS EMPTY" << endl;
        return;
    }
    for (int i = 0; i <= top; i++) {
        cout << ar[i] << " ";
    }
    cout << endl;
}

int main() {
    Stack s1;
    s1.push(7);
    s1.push(10);
    s1.push(4);
    
    int val = s1.pop();
    cout << "Popped value: " << val << endl;

    int topValue = s1.peak();
    cout << "Top value: " << topValue << endl;

    cout << "Current stack: ";
    s1.disp();

    return 0;
} 
```

(C) 
```
// NAME - SHREY RAJ
// PRN - 23070123123
// EXPERIMENT - 18(C) 

// STACK 


#include <iostream>
using namespace std;
#define size 5
#define error -9999

class stack 
{
    int top, ar[size];

public:
    stack() 
    {
        top = -1;
        ar[0]=0;
    }
    void push(int);
    int pop();
    int peak();
    void disp();
};

void stack::push(int num) 
{
    if (top == size - 1) 
    {
        cout << "Stack overflow: stack is full" << endl;
        return;
    } else 
    {
        ar[++top] = num;
    }
}

int stack::pop() {
    int val;
    if (top == -1) 
    {  // Corrected this line
        cout << "Stack underflow: stack is empty" << endl;
        return error;
    } else 
    {
        val = ar[top--];
        return val;
    }
}

int stack::peak() 
{
    if (top == -1) 
    {
        cout << "Stack underflow: stack is empty" << endl;
        return error;
    } else 
    {
        return ar[top];
    }
}

void stack::disp() 
{
    if (top == -1) 
    {
        cout << "Stack underflow: stack is empty" << endl;
        return;
    } else 
    {
        for (int i = 0; i <= top; i++) 
        {
            cout << ar[i] << " ";
        }
        cout << endl;
    }
}

int main() 
{
    stack s1;
    s1.push(10);
    s1.push(7);
    s1.push(4);
    int val = s1.pop();
    cout << "Popped value: " << val << endl;
    int top = s1.peak();
    cout << "Top value: " << top << endl;
    cout << "Stack contents: ";
    s1.disp();
    return 0;
} 
```

### Output 
(A) <br> 
![](https://github.com/shrey-raj24/CDS-Experiment-18/blob/main/OUTPUT_18a.png) 

(B) <br> 
![](https://github.com/Shloka-Patel/Experiment---18/blob/main/Output_18B.png) 

(C) <br> 
![](https://github.com/Shloka-Patel/Experiment---18/blob/main/Output_18C.png) 

### Conclusion 
Stacks are widely used in programming for tasks like reversing data, backtracking, expression evaluation (infix, postfix, prefix), and function call management in recursion. By ensuring efficient access to the most recently added elements, stacks are particularly useful in scenarios where a restricted form of access to data is required.
In C++, the stack can be implemented both manually (using arrays or linked lists).  
