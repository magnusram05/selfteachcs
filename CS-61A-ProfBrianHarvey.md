22-Mar-2025
Lecture-1: [Functional programming in Scheme](https://archive.org/details/ucberkeley_webcast_l28HAzKy0N8)

* Learnt about a new language called Scheme. Professor Harvey was executing a bunch of Scheme programs.
Example: When executed, this (+ 3 4) will print 7

+ is the function
3 4 are actual arguments

* Prof. explained a fun program called pigl which is a code language used by children to talk infront of their parents

scheme ==> emesch - stop at the first vowel in a word and move all preceeding letters to the last!

23-Mar-2025
Lecture-2: [Functional programming - Lecture-2](https://archive.org/details/ucberkeley_webcast_TTK2lZoWbPQ)

**What is a Function?**
-  For one or more input, a function always returns the same output irrespective of what is happening elsewhere in the program
-  This is important in parallelism as we don't want one part of the program affecting other part
-  With multi-core processors each core can run a program simultaneously
-  A single-core can be made to run faster only so much because it wil heatup and melt after a point
-  Hence processor speeds are kept the same but no of processors increased in a computer
  
**Abstraction**
- Application | High-level language (Scheme) | Low-level language (c) | Machine language/Architecture | Logic Gates | Transistors | Quantum Physics
- Abstraction is a layer built on top of lower-level bulding blocks

**Function vs Procedure**

- f(x) = 2x + 6
- g(x) = 2 (x+3)

These are same function but different procedures.  There are no functions inside a computer. A computer only understands procedures.
Procedures what determines how fast a function is though 2 functions does the same thing but differently.  

*It is easier to make things work and then make it work efficiently than to make it run faster and then make it work!*

24-Mar-2025
Lecture-3: [Functional programming - Higher-order procedure-1](https://archive.org/details/ucberkeley_webcast_ogIGxEzvnSE)

there are things - data 
and
there are actions - functions

There is a wall between these two concepts in our brain.  Breaking down this wall is the goal of this functional programming course where we will soon see that the functions can be passed to other functions as data

why would we do that?
A computer program that can fit in our memory is easy to understand in contrast to the ones that are huge.  
One way to reduce the size of the programs and make it easy to digest is to find the common patterns and extract it into a function and pass the unique actions as functions to the common function

For example: sumofsquare and sumofcubes are functions that have similar functionality except for a minor variation - square and sum vs cube and sum. 

```java
public int sumofsquare(int start, int end) {
    int sum = 0;
    for (i=start; i <= end; i++) {
        sum = sum + (i * i)
    }
    return sum;
}
```

```java
public int sumofcube(int start, int end) {
    int sum = 0;
    for (i=start; i <= end; i++) {
        sum = sum + (i * i * i)
    }
    return sum;
}
```

```java
public int sum(Function<Integer, Integer> func, int start, int end){ 
    int sum = 0;
    for (i=start; i <= end; i++) {
        sum = sum + func.apply(i);
    }
    return sum;
}

public static void main(String [] args) {
    HigherOrderProcedure hop = new HigherOrderProcedure();
    hop.sum( (i) -> (i * i * i), 1, 10); //Sum of cubes
    hop.sum( (i) -> (i * i), 1, 10);     //Sum of square
}
```
As shown, we generalized the summing function.  We take the thing that varies, represented as another function, as a parameter input into the generalized function.

- When we pass a function to another function, the funtion that is passed is evaluated as a function but it is not 'called'.  Calling happens within the generalized function.

28-Mar-2025

[Alan Kay distinguished lecture series Part-1: User interface design](https://archive.org/details/ucberkeley_webcast_dC4YGxzoAXk)

Computer literacy has three parts
- Access literacy: reading code. just like we can read a newspaper or book using our reading skills
- Creative literacy: writing code. 
just reading English language is not considered literate. Must know how to write
- Genre literacy: Just like we have to adapt to different genres of literature - Shakespeare era, era after that.. we need to adapt to different programming languages and styles within that

29-Mar-2025

[Alan Kay distinguished lecture series Part-2:](https://archive.org/details/ucberkeley_webcast_qxDGE1-S_LE)

Context is more important than logic - ex.: Choosing the correct data structure will do solve most of the problem we are trying to solve than the algorithm (or logic)

Problem solving has more than one dimension - lateral thinking

There are three mentalities - Kinesthetics (children - real-world) => Images (young adults - concrete) => Symbolics (adults - abstraction)
Ex.: Mouse helps locate things on the screen - Kinesthetics is how easy UI design should be.  Mouse as a UI tool is so basic for the user to operate.  

When designing UI systems, it should do the thing it is supposed to do. At the same time, it should let the user make full use of the underlying system.  Example - MaC OS is a wrapper around unix.

Anyone new to tennis can learn to play tennis in one afternoon by not letting the mind interfere with thing we are supposed to do when playing tennis - when we don't try too hard we can learn anything easily.

So any great UI design takes into account the human psychology and the three mentalities to problem solving - don't make them try too hard. It should feel natural. 

07-Apr-2025

[Lecture-7 - Orders of growth](https://archive.org/details/ucberkeley_webcast_32L5j10rrK0)

Running time of an algorithm must be measured by identifying number of constant time operations in the algorithm multiplied by N. 

If an algorithm's running time function is 7N^2 + 3N + 2, we can ignore constant 7 and 3N+2 as N^2 is always going to be higher.

07-Apr-2025

[Lecture-8 - Recursion and Iteration](https://archive.org/details/ucberkeley_webcast_0G3tNuBBO5I)

Recursion solves the problem on the way out i.e. traversing back up the call stack. Iteration solves it on the way in. So recursion takes up more memory because of the stacked procedure call. 

Think hard where the inefficiency in our algorithm and reduce the order of growth from exponential to quadratic to linear to logarithmic

Search algorithms are typically linear, logarithmic 

Sorting algorithms are quadratic, nlogn

09-Apr-2025

[Lecture-9: Data Abstraction](https://archive.org/details/ucberkeley_webcast_Oy36XpGVyjA)

Constructors abstract object creations

Selectors encapsulate internal implementation

We create abstract types from the language primitives and create meaningful abstractions which enables easy maintenance as changes can be localized within the individual abstractions as the abstractions are/should be responsible for only thing.

10-Apr-2025

[Lecture-10](https://archive.org/details/ucberkeley_webcast__qGeRWplPgc)

Scheme language specific APIs - keep, every - for sentence structure 
filter, map - for list data structure
accumulate - works for both

12-Apr-2025

[Lecture-11 - Computer Science 61A Example: calculator](https://archive.org/details/ucberkeley_webcast_nzMPF59Ackg)

syntax varies across programming languages while semantics remain the same. if/for conditional and loops are common in programming languages but it's syntax will be different.

Applicative order - evaluate expression and then call the function

normal order - call the function with expression itself

apply - is a function that takes a function and arguments to that function and calls the function with the arguments

REPL - Read, eval, print, loop

calc language is an interpreter written in scheme and it has only 4 functionalities +/-/*/\ 

calc interpreter interprets (read and eval) the calc expression passed to it and prints the output 





