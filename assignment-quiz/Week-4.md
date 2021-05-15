# WEEK-4
- [[#Assignment: Algorithmic Complexity|Assignment: Algorithmic Complexity]]
	- [[#Problem 1: Recursion revisited|Problem 1: Recursion revisited]]
	- [[#Problem 2: Fibonacci profiler|Problem 2: Fibonacci profiler]]
	- [[#Problem-3|Problem-3]]
- [[#Practice Quiz • Efficiency in Practice|Practice Quiz • Efficiency in Practice]]
- [[#PRACTICE QUIZPractice Quiz •  Vectorization and Other Speed Ups|PRACTICE QUIZPractice Quiz •  Vectorization and Other Speed Ups]]
- [[#Practice Quiz|Practice Quiz]]


## Assignment: Algorithmic Complexity
### Problem 1: Recursion revisited
Write a recursive function in a more efficient way
**Solution-1**
```MATLAB
function w=reversal(v)
    
    if length(v)==1
        w=v;
    else
        w=[v(end),reversal(v(1:end-1))];
    end
end
```
**Solution-2**

```MATLAB
function v = reversal2(v)
    if length(v) > 1
        ii = round(length(v) / 2);
        v = [reversal2(v(ii+1:end)) reversal2(v(1:ii))];
    end
end
```

### Problem 2: Fibonacci profiler
Write a Fibonacci recursive function in a more efficient way.
**Solution-1**
```MATLAB
function [f, trace] = my_fibo_trace(n, trace)
    trace = [trace,n]; 
    if n<=2
        f = 1;
    else
        [f1, trace] = my_fibo_trace(n-2, trace); 
        [f2, trace] = my_fibo_trace(n-1, trace);
        f = f1+f2;  
    end 
end
```
**Solution-2**

```MATLAB
function [f, v] = fibo_trace(n,v)
    v(end+1) = n;
    if n == 1 || n == 2
        f = 1;
    else
        [f1, v] = fibo_trace(n-2,v); 
        [f2, v] = fibo_trace(n-1,v);
        f = f1+f2;
    end
end
```
### Problem-3

```MATLAB
NOT SOLVED
```


## Practice Quiz • Efficiency in Practice
1.Question What question should you ask yourself when your program runs slow and the algorithm seems to be the best you can come up with?

-   Can I afford a faster computer?
-   *Am I doing any unnecessary work?*
-   Is my nerd friend awake so I can call him for help?

2.Question What does profiling your code mean?

-   *Identifying how long various parts of your program take to run.*
-   Writing detailed comments to help others understand your code.
-   Running the program multiple times to see whether it behaves differently each time.

3.Question Method for reducing unnecessary work:

-   Avoiding repeating the same calculations by storing and reusing the results.
-   Preallocating arrays when possible so that MATLAB does not have to keep allocating and copying arrays as they grow in size.
-   Avoiding unnecessary calculations by taking advantage of the characteristics of the data the program is working on.
-   *All of the above*

4.Question Which of the following statements is true?

-   *A linear time complexity algorithm may run slower than one with quadratic time complexity on the same input.*
-   If I have nested loops in my program, the time complexity will be worse than linear by definition.
-   If we double the input size of a linear time complexity algorithm, its run time will be at least twice as long.
## PRACTICE QUIZPractice Quiz •  Vectorization and Other Speed Ups 
## Practice Quiz

1.Question Which of the following statements is false?

-   The advantages of implicit looping includes better performance and simpler, cleaner code.
-   *Vectorization is an automated process carried out by the MATLAB environment.*
-   A vector command is an operator or function that works on an entire vector or array.

2.Question An input argument to a MATLAB function

-   is passed by reference resulting in efficient code automatically.
-   is always copied on the stack, so care must be taken not to pass large variables to functions.
-   *is passed by value from the user's point of view, but it may passed by reference in reality for efficiency unless the code inside the function changes its value.*

3.Question What can we do to make sure our program is efficient when preallocation of a matrix is not possible?

-   Allocate a big array and hope it is large enough.
-   *Keep in mind that MATLAB stores arrays in column major order and write our code so that the number of array reallocation and copying is minimized.*
-   Nothing.

4.Question Which of the following is false?

-   The command parfor stands for parallel for.
-   *Any for loop can use parfor instead, if our computer has multiple cores.*
-   The command parfor can only be used if different iterations of the body of the loop are independent of each other.
-   MATLAB does not guarantee the order of different iterations of the body of a parfor loop.