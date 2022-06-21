# Intro to Algorithms

## Goals
- when are different algos used in the real world
- implement the algos from pseudocode to your language of choice
- describe mathematical notation of algos 

## 1.1 Algorithms in Computing
#### **algorithm** - a well-defined computational proccedure that takes some value or set of values as *inputs* and provides some value(s) as *output*
	e.g. sorting problem
	- in: a sequence of numbers of length *n*
	- out: a permutation of the *input* sequence such that $a_1<a_2<...<a_n$
##### What goes into choosing the best algorithm?
- num of items to be sorted
- existing orderof the items
- restictions on the item values
- architecture of the computer
- kind of storage devices used
	- main memory, disks, or tapes
	
algorithms can be: english (or some other lang), computer program, or hardware design

### Programs we can solve
- sorting
	- identifying, determining sequences of the 3 million chemical base pairs that make up human DNA, storing info in databases, developing tools for data analysis -> all algorithms aimed to accomplish tasks while using resources efficiently
		- benefits: saves time and money
		- e.g. human genome project
- large amount of data on Internet
	- good routes for data travel
	- search engine to find pages
- e-commerce: cryptographic algorithms
- graph algorithms + linear programming -> mapping most efficient delivery routes

### Data Structures
**data structure** - store and organize data

default measure of efficiency is speed
NP-complete - no efficient solution is known; not proven that one cannot exist

### Parallelism
- algorithms should be designed with parallelism in mind to get the best performance from multicore computers

### Exercises
Q1. Give a real-world example for sorting or convex hull
Q2. What are the measures of efficiency used in a real-world setting
Q3. Discuss the strengths and limitations of a data structure you've seen/used
Q4. Compare and contrast the shortest-path and traveling-salesman problems 
Q5. Think of a real-world problem where you can approximate the best solution and think of one where only the best will do

## 1. 2 Algorithms as Technology

### Sorting
- insertion sort -> $n^2$
- merge sort -> $n\log_2n$

### Mostly Inspirational Chapter
### Questions 
Q1. what kind of application does not require algorithmic content at the application level?
Q2. For inputs of size n, if insertion sort runs in $4n^2$ steps, while merge sort runs in $16n\log_2n$ steps. When will insertion sort beat merge sort 
Q3. smallest value n such that an algorithm with a runtime of $80n^2$ runs faster than an algorithm whose runtime is $2^n$. Assume they run on the same machine 