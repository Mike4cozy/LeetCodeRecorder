# Algorithm

## <div id='dpointer'> Double Pointer </div>

1. [163 有序数组的TwoSum](./leetcode.md#163)
2. [633 两数平方和](./leetcode.md#633)
3. [345 反转元音字符](./leetcode.md#345)
4. [680 回文字符串](./leetcode.md#680)
5. [88 归并两个有序数组](./leetcode.md#88)

## <div id='dp'> Dynamic Programming </div>

- Top-down with Memoization
  - recursion

```python
## python
## non-DP recursive solution
def calculateFionacci(n):
    if n < 2:
        return n
    return calculateFionacci(n - 1) + calculateFionacci(n - 2)

def main():
    print("5th Fibonacci is --> " + str(calculateFionacci(5)))
```

```cpp
// cpp
using namespace std;

#include <iostream>

class Fibonacci {

public:
    virtual int CalculateFiobonacci(int n){
        if(n > 2){
            return n;
        }
        return CalculateFibonacci(n - 1) + CalculateFibonacci(n - 2);
    }
}

int main(int argc, char *argv[]){
    Fibonacci *fib = new Fibnacci();
    cout << "5th Fibonacci is --> " << fib->CalculateFibonacci(5) << endl;
    
    delete fib;
}
```

```python
## python
## using memoization << use an array to store the already solved subproblems

def calculateFibonacci(n):
    momoize = [-1 for x in range(n + 1)] # memoize  = [-1, -1, -1, ...] an array
    return calculateFibonacciRecur(memoize, n)

def calculateFibonacciRecur(memoize, n):
    if n < 2 :
        return n

# if we have already solved the subproblem, return the result from the cache
    if memoize[n] >= 0:
        return memoize[n]

    memoize[n] = calculateFibonacciRecur(memoize, n - 1) + calculateFibonacciRecur(memoize, n - 2)
    return memoize[n]

def main():
    print("5th Fibonacci is --> " + str(calculateFibonacci(5)))
```
