# Ex.No:3  
# Ex.Name: Insert five special character elements in to stack 

## Date:  

## Aim:  
To Write a CPP Program to insert five special character elements in to stack using linked list (use STL for Stack)

## Algorithm:  
1. Start the program.  
2. Create a base class `Base` with a virtual function `print()`.  
3. Create a derived class `Derived` that overrides the `print()` function.  
4. Use a base class pointer to point to the derived class object.  
5. Call the `print()` function to demonstrate runtime polymorphism (base pointer calls derived function).  
6. Stop the program.  

## Program:
```cpp
#include <bits/stdc++.h>
using namespace std;
template <typename T>
// templating it so that any data type can be used

class Stack {
public:
	list<T> l;
	float cs = 0;
	// current size of the stack

	// pushing an element into the stack
	void push(T d)
	{
		cs++;
		// increasing the current size of the stack
		l.push_front(d);
	}
	// popping an element from the stack
	void pop()
	{
		if (cs <= 0) {
			// cannot pop us stack does not contain an
			// elements
			cout << "Stack empty" << endl;
		}
		else {
			// decreasing the current size of the stack
			cs--;
			l.pop_front();
		}
	}
	// if current size is 0 then stack is empty
	bool empty() 
	{ 
	    return cs == 0; 
	    
	}
	// getting the element present at the top of the stack
	T top() { return l.front(); }
	float size()
	{
		// getting the size of the stack
		return cs;
	}
	// printing the elements of the stack
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
    float n;
    char num;
    cin>>n;
	Stack<char> s;
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
```
Input:
5
@ # $ % ^

Output:
Current size of the stack is 5
The top element of the stack is ^
The top element after 1 pop operation is %
The top element after 2 pop operations is $
Size of the stack after 2 pop operations is 3
```
## Result:
<img width="1203" height="525" alt="image" src="https://github.com/user-attachments/assets/040d67a9-170b-42a1-996d-9346e19f4fa6" />
