# Ex.No:2  
# Ex.Name: Insert five double elements into Stack using Linked List (STL)  

## Date:  

## Aim:  
To write a C++ program to insert five double elements into a stack using the STL `stack` container (linked list based), and demonstrate stack operations (push, pop, top, and size).  

## Algorithm:  
1. Start the program.  
2. Create an STL `stack<double>`.  
3. Read `n` (number of elements).  
4. Push `n` double values onto the stack.  
5. Display the current size of the stack.  
6. Display the top element of the stack.  
7. Perform 1 pop operation and display the new top.  
8. Perform another pop operation and display the new top.  
9. Display the final size of the stack after two pops.  
10. Stop the program.  

## Program:
```cpp
#include <bits/stdc++.h>
using namespace std;
template <typename T>


class Stack {
public:
	list<T> l;
	double cs = 0;
	void push(T d)
	{
		cs++;
		l.push_front(d);
	}
	
	void pop()
	{
		if (cs <= 0) {
			cout << "Stack empty" << endl;
		}
		else {
			cs--;
			l.pop_front();
		}
	}
	bool empty() 
	{ 
	    return cs == 0; 
	    
	}
	
	T top() { return l.front(); }
	double size()
	{
		return cs;
	}
	
	void print()
	{
		for (auto x: l) 
		{
			cout << x << endl;
		}
	}
};
int main()
{
    int n;
    float num;
    cin>>n;
	Stack<double> s;
	for(int i=0;i<n;i++)
	{
	    cin>>num;
	    s.push(num);
	}
	cout << "Current size of the stack is " << s.size() << endl;
	cout << "The top element of the stack is " << s.top() << endl;
	s.pop(); 
	cout << "The top element after 1 pop operation is " << s.top() << endl;
	s.pop();
	cout << "The top element after 2 pop operations is " << s.top() << endl;
	cout << "Size of the stack after 2 pop operations is " << s.size() << endl;
	return 0;
}
```

## Output:
<img width="862" height="545" alt="image" src="https://github.com/user-attachments/assets/a528c5f1-850f-4699-967a-328bd2a7aa3c" />

## Result:
```
Input:
5
10.1 20.2 30.3 40.4 50.5

Output:
Current size of the stack is 5
The top element of the stack is 50.5
The top element after 1 pop operation is 40.4
The top element after 2 pop operations is 30.3
Size of the stack after 2 pop operations is 3
```
