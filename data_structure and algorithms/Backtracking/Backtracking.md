### Basics
**Backtracking** is a method to solve problems by making a series of choices that we can return or backtrack to.

The **call stack** "remembers" our choices and "knows" what to choose next.

Whenever you have something that represents many decision points, that's when you know backtracking is the tool that you need to be using. 

#### Keys (important)
1. Our **Choice**
- What choice do we make at each call of the function?
- *Recursion expresses decisions*. And our decisions are remembered on the call stack.
- Common pattern: choose, explore, undo our choose
1. Our **Constraints**
- When to stop following a certain path?
2. Our **Goal**
- What's our target?
- What are we trying to find? -> Base case(when our recursion stops, when we say we have an answer, let's add this to our results and return back to a previous position and keep searching)

==As long as you define a correct policy in each call of the function, you can trust the recursion to do its job :D==

More like a Brute-Force approach
Backtracking follows Depth-First-Search(DFS)
Pretty much like finding all possible solutions, return all distinct solutions
(while dynamic programming is more like an optimization problem, only return the most optimal solution)

### Implementation
[[N Queens problem]]
[[Subset problems]]
[[graph coloring problem]]