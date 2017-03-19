# Sorting-Big-O-Notation

<b>Algorithms</b>

* Can be described as as et of steps to accomplish a task
* Algorithms put the science in computer science

1. How does google hangouts send live videos across the internet?
   * Audio and video compression algorithms

2. How does google maps find routes between two locations?
   * Route finding algorithms

3. How does NASA choose how to arrange the solar panels on the internationl space station and when to rearrange them?
   * Optimize and scheduling algorithms
   
How do you know the efficiency of an algorithm?

  1. Count the number of seconds it takes to execute and compare it
  2. However, it's not just troublseome to use Timers around code, bu tif it is different hardware (i.e. a supercomputer) it may seem more efficient when indeed it's the same program
  
  - Illustrate a better way: Sort an array with N integers
  
          void sort(int[] arr){
            for(int x = 1; x < arr.length; x++){
              for(int y = x; y > 0 && arr[y-1] > arr[y]; y--){
                int t = arr[y];
                arr[y] = arr[y-1];
                arr[y-1] = t;
              }
            }
          }

Do you recognize the algorithm?

- It has a nested for loop, which means
  - As the number of elements N in the array arr grows, it will take approximately N*N longer to perform the sorting
  - In Big O notation, this is represented as O(n<sup>2</sup>) <i>quadratic</i>

What would happen if array arr is already sorted?
- This would be the best case scenario

<b>Order of Functions</b>
- Logarithmic
- Polynomial
  - Linear
  - Quadratic
  - Cubic
  - etc.
- Exponential

When analyzing the efficiency of an algorithm, we describe it in one of these categories.

This implies 2 things
1. Coefficients do not matter
  - i.e. 0.0001n<sup>2</sup> and 1000n<sup>2</sup>
2.Lower order items do not matter
  - e.g. n<sup>2</sup>-200000n+1 and n<sup>2</sup>
          
