### 1470 Shuffle the Array

Easy

https://leetcode.com/problems/shuffle-the-array/

Given the array `nums` consisting of `2n` elements in the form `[x1,x2,...,xn,y1,y2,...,yn]`.

*Return the array in the form* `[x1,y1,x2,y2,...,xn,yn]`.

#### My Solution

Using 2 new arrays to store the `x` and `y` numbers, put them back to the `nums` array.

```java
class Solution {
    public int[] shuffle(int[] nums, int n) {
        int[] a = new int[n];
        int[] b = new int[n];
        
        for(int i=0;i<n;i++){
            a[i] = nums[i];
            b[i] = nums[n+i];
        }
        
        for(int i=0;i<nums.length;i++){
            if(i==0) nums[i]=a[0];
            else if(i==1) nums[i]=b[0];
            else if(i%2==0) nums[i]=a[i/2];
            else nums[i]=b[i/2];
        }
        return nums;
    }
}
```

#### Other Solutions

He use 2 pointers, one point the begin as` nums[0]` and another point the mid one as `nums[n]`, and then create a new array to put the solutions.when `i` equals to 0, put the number x as the left pointer pointed and the same as mid point. The most incredible thought is the double pointers and the `i+i+2`.

```java
//@abhi_u_03
class Solution {
    public int[] shuffle(int[] nums, int n) {
        int left=0,mid=n;
        int b[]= new int[2*n];
        for(int i=0;i<2*n;i=i+2)
        {
            b[i] = nums[left++];
            b[i+1] = nums[mid++];
        }
        return b;
    }
}
```

#### Other points

Double Pointers(1)