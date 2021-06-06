# Big O

- Big O is how we measure the worst potential running time of an algorithm: the higher the number and/or how quickly it scales, the worse it is

- Scenarios from worst to best:
  1. Factorial time (`O(n!)`) is the worst possbile scenario, but unavoidable in some NP-complete cases.
  2. Exponential Growth (`2n`) is the next worst possible Big O scenario.
  3. Quadratic growth (`O(n^2)`) is next, commonly seen in nested loops.
  4. n log n
  5. n
  6. log n: This is when the complexity is cut in half with each operation, such as binary search.
  7. 1

- If the algo is "Do this, then do that when you're done with this", you add runtimes.
- If the algo is "Do this for every time you do that", you multiply runtimes.

# Recursion

- Recursion is what we call the technique of a function calling itself until it reaches some predetermined limit.

- The `base case` is what tells the recursive algorithm when to stop calling itself.
  
- The `recursive call` is the portion of the algorithm where it keeps calling itself until it reaches the base case.

- Recursive solutions take less time at the cost of computational space/memory.

- Understanding how the call stack works is important to truly understanding recursion. As the recursive call runs, the call stack gets fuller until the base case is reached.

- JS DOES NOT have consistent tail recursion support. 

