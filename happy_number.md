## Given a number N find whether its a happy number or not. A number is called happy if it leads to 1 after a sequence of steps wherein each step, the number is replaced by the sum of squares of its digit that is if we start with Happy Number and keep replacing it with digits square sum, we reach 1.
### Code
```cpp
// { Driver Code Starts
#include<bits/stdc++.h> 
using namespace std;

 // } Driver Code Ends
class Solution{
public:
    int sum(int n)
        {
            int s=0;
            while(n)
            {
                s+=(n%10)*(n%10);
                n/=10;
            } 
            return s;
        }
    int isHappy(int n){
        // code here
        set<int> sums;
        while(sums.find(n)==sums.end())
        {
            if(sum(n)==1)
                return true;
            sums.insert(n);
            n=sum(n);
        }
        return false;
    }
};

// { Driver Code Starts.
int main() 
{ 
    int t;
    cin>>t;
    while(t--)
    {
        int N;
        cin>>N;
        Solution ob;
        cout << ob.isHappy(N) << endl;
    }
    return 0; 
}  // } Driver Code Ends
```
