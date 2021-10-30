## Implement a Queue using 2 stacks s1 and s2 . <br> A Query Q is of 2 Types <br> (i) 1 x (a query of this type means  pushing 'x' into the queue) <br> (ii) 2   (a query of this type means to pop element from queue and print the poped element)
### Code
```cpp
// { Driver Code Starts
#include<bits/stdc++.h>

using namespace std;

class StackQueue{
private:
    stack<int> s1;
    stack<int> s2;
public:
    void push(int B);
    int pop();

};
int main()
{

    int T;
    cin>>T;
    while(T--)
    {
        StackQueue *sq = new StackQueue();

        int Q;
        cin>>Q;
        while(Q--){
        int QueryType=0;
        cin>>QueryType;
        if(QueryType==1)
        {
            int a;
            cin>>a;
            sq->push(a);
        }else if(QueryType==2){
            cout<<sq->pop()<<" ";

        }
        }
        cout<<endl;
    }


}
// } Driver Code Ends


/* The structure of the class is
class StackQueue{
private:   
    // These are STL stacks ( http://goo.gl/LxlRZQ )
    stack<int> s1;
    stack<int> s2;
public:
    void push(int);
    int pop();
}; */
stack<int> s1,s2;       //s2 for input and s1 for output
//Function to push an element in queue by using 2 stacks.
void StackQueue :: push(int x)
{
    // Your Code
    while(!s1.empty())
        {
            s2.push(s1.top());
            s1.pop();
        }
        s2.push(x);
        while(!s2.empty())
        {
            s1.push(s2.top());
            s2.pop();
        }
}

//Function to pop an element from queue by using 2 stacks.
int StackQueue :: pop()
{
        // Your Code 
        if (s1.empty()) 
            return -1;
 
        int t= s1.top();
        s1.pop();
        return t;
        return t;
}
```