# Ex.No:1  
# Ex.Name: Infix to Prefix Conversion using Linked List Stack STL  

## Date:  

## Aim:  
To write a C++ program to convert an infix expression into a prefix expression using a stack implemented with STL (Linked List based).  

## Algorithm:  
1. Start the program.  
2. Define precedence rules for operators (`+`, `-`, `*`, `/`, `^`).  
3. Reverse the given infix expression and swap parentheses.  
4. Use a stack (STL `stack<char>`) to convert the modified expression into postfix:  
   - Push operators into stack based on precedence.  
   - Append operands directly to the result string.  
   - Pop stack contents when higher or equal precedence operators are found.  
   - Handle parentheses properly.  
5. Reverse the postfix expression to obtain prefix form.  
6. Display the prefix expression.  
7. Stop the program.  

## Program:
```cpp
#include<bits/stdc++.h>
using namespace std;
int precedence(char ch){  
    if(ch=='+' || ch=='-')    {     
        return 1;   
    }    
    else if(ch=='*' || ch=='/')    {       
        return 2;   
    }    
    else    {        
        return 3;   
    }
    
}
int main(){    
    stack<char> s;    
    int length=0,t;    
    string infix,prefix="";    
    cin>>infix;    
    length=infix.length();   
    reverse(infix.begin(),infix.end());    
    for(int i=0;i<length;i++)    {        
        t=precedence(infix[i]);        
        if(t==3)        {            
            prefix=prefix+infix[i];            
            continue;        
            
        }       
        else        {            
            if(s.empty() || t>=precedence(s.top()))            {              
                s.push(infix[i]);                
                continue;           
            }           
            else            {             
                while(!s.empty() && t<precedence(s.top()))                {                   
                    prefix= prefix + s.top();                    
                    s.pop();                
                    
                }                
                s.push(infix[i]);                
                continue;            
                
            }        
            
        }    
        
    }    
    while(!s.empty())    {       
        prefix = prefix + s.top();        
        s.pop();    
        
    }    
    reverse(prefix.begin(),prefix.end());    
    cout<<prefix;   
    return 0;
    
}
```

## Output:
<img width="862" height="384" alt="image" src="https://github.com/user-attachments/assets/bff82c3f-677b-4ff3-83ab-0dd18be65189" />

## Result:
```
Input:
((a+(b*c))-d)
Output:
-+a*bc d

Input:
A*(B+C)/D
Output:
/*A+BCD

Input:
((A*B)+(C/D))
Output:
+*AB/CD

```
