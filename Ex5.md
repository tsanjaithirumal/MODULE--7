# Ex.No:5  
# Ex.Name: FCFS Scheduling Algorithm (3 Processes)  

## Date:  

## Aim:  
To write a C++ program to implement the First-Come, First-Served (FCFS) scheduling algorithm for three processes with burst times 10, 5, and 8, and to calculate the Waiting Time (WT) and Turnaround Time (TAT).  

## Algorithm:  
1. Start the program.  
2. Read the burst times of the processes.  
3. Initialize `WT[0] = 0`.  
4. For each process `i > 0`, calculate `WT[i] = WT[i-1] + BT[i-1]`.  
5. For each process, calculate `TAT[i] = WT[i] + BT[i]`.  
6. Display the process table with Burst Time, Waiting Time, and Turnaround Time.  
7. Stop the program.  

## Program:
```cpp
#include<iostream>
using namespace std;
int main()
{
    int bt[20],wt[20],tat[20],i,j,n,total=0;
    n=3;
    bt[0]=10, bt[1]=5, bt[2]=8;
    wt[0]=0;
    for(i=1;i<n;i++)
    {
        wt[i]=0;
        for(j=0;j<i;j++)
            wt[i]+=bt[j];
        total+=wt[i];
    }
   
    total=0;
    cout<<"Processes   BT time   WT time   TA time"<<endl;
    for(i=0;i<n;i++)
    {
        tat[i]=bt[i]+wt[i];
        total+=tat[i];
        cout<<"       "<<i+1<<"       "<<bt[i]<<"       "<<wt[i]<<"       "<<tat[i]<<endl;
    }
    return 0;
}
```

## Output:
<img width="863" height="370" alt="image" src="https://github.com/user-attachments/assets/b91c2c79-ec23-4b09-87ba-ba8d2494622e" />

## Result:
```
Processes BT time WT time TA time
1 10 0 10
2 5 10 15
3 8 15 23
```
