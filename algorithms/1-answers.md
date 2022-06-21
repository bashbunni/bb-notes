## 1.1

Q1. Give a real-world example for sorting or convex hull
First of all, I forgot what a convex hull is... 
- the convex hull is the smallest convex polygon containing the points

sorting - any time you want to access a set of linear data. For example, a list of patients in a electronic medical record system

convex hull - (good for any area problems) calculating the danger zone for forest fires, with each fire being a point on the graph. The point would include danger radius

Q2. What are the measures of efficiency used in a real-world setting
most companies want to save time + money
time - speed, but compromise on cost. It costs more to have better hardware (faster runtime) but is the fastest option
money - $ hardware - memory, storage, cpu -> space efficiency

Q3. Discuss the strengths and limitations of a data structure you've seen/used
hash table - makes every problem faster; not space efficient?
(1337 solution to landing your job when they ask how you can make your solution more efficient)

Q4. Compare and contrast the shortest-path and traveling-salesman problems 
traveling salesman problem is a NP-complete algorithm meaning there is no optimal solution, only an approximate best solution.

shortest path is typically from one point to another. There will be nodes en-route to the endpoint with varying weighted edges, some are aren't required to reach your final destination while the traveling salesman problem requires you to reach all nodes

Q5. Think of a real-world problem where you can approximate the best solution and think of one where only the best will do
Approx Ok:
snack delivery - approximate is ok
Only best:
MRI/CT - has to be a very accurate scan - reminds me of convex hull algo 
Finding pages on the Internet

## 1.2
### Questions 
Q1. what kind of application does not require algorithmic content at the application level?
Web-based applications, but even then they often require some algorithmic content depending on the functionality of the application/service

Q2. For inputs of size n, if insertion sort runs in $4n^2$ steps, while merge sort runs in $16n\log_2n$ steps. When will insertion sort beat merge sort 
// TODO

Q3. smallest value n such that an algorithm with a runtime of $80n^2$ runs faster than an algorithm whose runtime is $2^n$. Assume they run on the same machine 
// TODO