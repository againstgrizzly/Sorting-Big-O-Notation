# Chapter 6: Big O Notation

## Algorithms

- Can be described as a set of steps to accomplish a task
- Algorithms put the science in computer science

&nbsp;
1. How does Google Hangouts send live videos across the internet?
  - Audio and video compression algorithm
2. How does Google Maps find routes between two locations?
 - Route finding algorithm
3. How does NASA choose how to arrange the solar panels on a space station and when to rearrange them?
  - optimization and scheduling algorithms 

How do you determine the efficiency of an algorithm?

- Count the number of seconds it takes to execute and compare?
  - Problem: When run on different hardware the algorithm may seem more efficient (i.e. on a super computer)
  - It may seem more efficient when indeed it's the same program
- Illustrate a better way: Sort an Array with N integers

```java
void sort(int[] arr){
  for(int x = 1; x < arr.length; x++){
    for(int y = x; y > 0 && arr[y-1] > arr[y]; y--){
      int t = arr[y];
      arr[y] = arr[y-1];
      arr[y-1] = t;
    }
  }
}
```
This algorithm has 2 nested for loops, which means:
  - As the number of elements N in the array arr grows it will take approximately N*N longer to perform the sorting.
  - In Big O notation, this is represented as O(n)<sup>2</sup> quadratic
  - What would happen if the array was already sorted?
    - This would be the best case scenario

## Big O Notation

**Order of Functions**
- Logarithmic
- Polynomial
  - Linear
  - Quadratic
  - Cubic
  - Etc.
- Exponential

When analyzing the efficiency of an algorithm, we observe it in one of those categories

This implies 2 things:
1. Coefficients do not matter
 - e.g. 0.0001n<sup>2</sup> and 1000n<sup>2</sup>
2. Lower order items do not matter
  - e.g. n<sup>2</sup> - 200000n + 1 and n<sup>2</sup>

| Growth Rate   | Name          |
| ------------- | ------------- |
| 1             | Constant      |
| Log(n)        | Logarithmic   |
|N              |Linear         |
|N*log(N)       |Linearithmic   |
|N<sup>2</sup>  |Quadratic      |
|N<sup>3</sup>  |Cubic          |
|2<sup>N</sup>  |Exponential    |

### Examples

**Constant**
```java
a+=1;
```
Description

Statement(one line of code)

**Logarithmic**
```java
while(n>1){
n=n/2;
}
```
Description

Divide in half (Binary search)

**Linear**
```java
for(c = 0; c < n; c++){
  a+=1;
}
```

Description

Loop

**Linearithmic**

merge sort, quicksort

effective sorting algorithm

**Quadratic**

```java
for(c = 0; c < n; c++){
  for(i = 0; i < n; i++){
    a+=1;
  }
}
```
double loop

**Cubic**
```java
for(c = 0; c < n; c++){
  for(i = 0; i < n; i++){
    for(x = 0; x< n; x++){
      a+=1;
    }
  }
}
```
triple loop

**Exponential**
Description
- trying to break a password by generating all possible combinations
- Extensive search

When analyzing an algorithm, we concentrate on a sufficiently large size of input such that the order of the function makes the decisive difference

For example 0.1n<sup>2</sup> versus n
- 0.1n<sup>2</sup> is larger than N, when N gets sufficiently large
- Or we can say there is an N<sub>o</sub>, such that 0.1n<sup>2</sup> >= N as long as N > N<sub>o</sub>
- N<sub>o</sub> is the input size where the value of the quadratic function becomes greater than the linear function

When we discuss the order of a function the **constant** factor does NOT make a difference

What about 2 functions in the same order?
 - How could you address the difference between 4n<sup>2</sup> and 0.5n<sup>2</sup>
 - Ratio is capped 4n<sup>2</sup> / 0.5n<sup>2</sup> = 8
- The upper bound does not exceed 8
- In other words, the ratio 8 is constant

Consider 4n<sup>2</sup> and 0.5n
- There is no cap
- 4n<sup>2</sup> / 0.5n = 8n
- Without boundary eventually becomes infinity
- Therefore two function in the same order are within a constant factor
