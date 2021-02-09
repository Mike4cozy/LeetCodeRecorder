# Leetcode

## Algorithm

1. [双指针](./algorithm.md#dpointer)
2. [动态规划](./algorithm.md#dp)

## Recorder

### <div id='163'> 163. Two Sum II - Input array is sorted </div>

#### 163-Describe

Given an array of integers **numbers** that is already sorted in ascending order, find two numbers such that they add up to a **specific** target number.

```
Input: numbers = [2,3,4], target = 6
Output: [1,3]
```

#### 163-Solution

Double pointer

```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& numbers, int target) {
        int i = 0;
        int j = numbers.size() - 1;
        while(i < j){
            int sum = numbers[i] + numbers[j];
            if(sum > target) j--;
            else if( sum < target) i++;
            else return vector<int>{i + 1, j + 1};
        }
        return vector<int>{-1, -1};
    }
};
```

### <div id='633'> 633. Sum of Square Numbers </div>

#### 633-describe

Given a non-negative integer c, decide whether there're two integers a and b such that a^2 + b^2 = c.

```
Input: c = 5
Output: true
Explanation: 1 * 1 + 2 * 2 = 5
```

#### 633-solution

Double-pointer

```cpp
class Solution {
public:
    bool judgeSquareSum(int c) {
        long i = 0;
        long j = int(sqrt(c));
        while(i <= j){
            int sum = i*i + j*j;
            if(sum > c) { j--; }
            else if(sum < c) { i++; }
            else {return true;}
        }
        return false;
    }
};
```

### <div id='345'>345. Reverse Vowels of a String </div>

#### 345-describe

Write a function that takes a string as input and reverse only the vowels of a string.

```
Input: "hello"
Output: "holle"
```

#### 345-solution

```cpp
class Solution {
public:
    string reverseVowels(string s) {
        set<char> dict={'a','o','e','i','u','A','O','E','I','U'};
        int i = 0, j = s.size()-1;
        while(i < j){
            while(i<j && !dict.count(s[i])) {i++;}
            while(i<j && !dict.count(s[j])) {j--;}
            if(i < j) {swap(s[i++], s[j--]);}
        }
        return s;
    }
};
```

### <div id='680'> 680 Valid Palindrome II </div> 

#### 680-describe

Given a non-empty string s, you may delete at most one character. Judge whether you can make it a palindrome.

```
Input: "aba"
Output: True
```

#### 680-solution

```cpp
class Solution {
public:
    bool validPalindrome(string s) {
        int i = 0, j = s.size() - 1;
        for (i = 0; i < j; i++, j--){
            if(s[i] != s[j]){
                return isPalindrome(s, i + 1, j) || isPalindrome(s, i, j - 1);
            }
        }
        return true;
    }

    bool isPalindrome(string s, int i, int j){
        while(i < j){
            if (s[i++] != s[j--]){
                return false;
            }
        }
        return true;
    }
};
```

### <div id = '88'> 88. Merge Sorted Array </div> 

#### 88-describe

Given two sorted integer arrays **nums1** and **nums2**, merge **nums2** into **nums1** as one sorted array.

The number of elements initialized in **nums1** and **nums2** are **m** and **n** respectively. You may assume that **nums1** has a size equal to **m** + **n** such that it has enough space to hold additional elements from **nums2**.

```
Input: nums1 = [1,2,3,0,0,0], m = 3, nums2 = [2,5,6], n = 3
Output: [1,2,2,3,5,6]
```

#### 88-solution

```cpp

```