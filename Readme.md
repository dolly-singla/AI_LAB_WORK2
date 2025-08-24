# AI-LAB-2
Contains 8 puzzle problem solution with heuristics and Hill Climbing , Water Jug Problem Solution, Tic Tac Toe Solution and Magic square Problem Solution

**AI Lab - Problem Solutions**
This repository contains Python solutions for several classic AI and puzzle problems. Each solution demonstrates different search algorithms and problem-solving techniques.

**Problems and Algorithms**
Below is a list of the problems solved in this repository, along with a discussion of the time complexity for each solution.

**1. Water Jug Problem**
Problem: Given two jugs with capacities m and n liters, find a sequence of operations to measure a specific amount of water.

Algorithm: This problem is solved using a state-space search, typically with Breadth-First Search (BFS) to find the shortest solution.

Time Complexity: O(m * n)

The complexity is determined by the number of possible states the system can be in. A state is defined by the amount of water in each jug (x, y), where 0 <= x <= m and 0 <= y <= n.

The total number of states is (m+1) * (n+1). BFS explores each state and its transitions at most once, leading to a time complexity proportional to the size of the state space.

**2. Tic-Tac-Toe**
Problem: Implement an agent that can play Tic-Tac-Toe optimally.

Algorithm: The standard solution uses the Minimax algorithm, which explores the game tree to find the optimal move.

Time Complexity: O(1)

While the Minimax algorithm has a general complexity of O(b^d) (where b is the branching factor and d is the depth of the tree), the game of Tic-Tac-Toe has a very small and finite state space.

The number of possible board positions is less than 9! (362,880). Because the game tree is small and constant, the time to find the optimal move from any position is also effectively constant.

**3. 8-Puzzle Problem**
The 8-puzzle problem involves arranging tiles on a 3x3 grid to match a goal configuration.

a) Solution with Heuristics (A* Search)
Algorithm: This solution uses the A* search algorithm, an informed search technique that uses a heuristic function (like the number of misplaced tiles or Manhattan distance) to guide its path.

Time Complexity: O(b^d)

b is the effective branching factor (the average number of successor nodes considered).

d is the depth of the optimal solution.

The worst-case complexity is related to the total number of states (9! / 2 = 181,440), but a good heuristic prunes the search space significantly, making the search much faster in practice than an uninformed search.

b) Solution using Hill Climbing
Algorithm: This approach uses a local search algorithm called Hill Climbing. It starts with a random state and iteratively moves to a neighboring state that is "better" (closer to the goal), based on a heuristic value.

Time Complexity: Variable, no worst-case guarantee.

The time complexity is difficult to state in Big-O notation for finding the optimal solution because Hill Climbing does not guarantee finding it. It can easily get stuck in a "local optimum."

The complexity is better described as the cost of the search path. The time to choose the next move is constant (evaluating a maximum of 4 neighbors), but the number of moves taken depends entirely on the starting state and the heuristic landscape.

**4. Magic Square**
Problem: Create a 3x3 grid where the numbers 1 through 9 are placed such that the sum of the numbers in each row, column, and main diagonal is the same.

Algorithm: This is likely solved using a backtracking or brute-force search algorithm.

Time Complexity: O(n^2!)

For an n x n grid, there are (n^2)! ways to arrange the numbers. A backtracking algorithm explores this search space.

While pruning rules (e.g., stopping a path if a row sum is already incorrect) reduce the search space significantly, the worst-case complexity remains factorial in nature, which is very high. For a fixed 3x3 square, the number of operations is large but constant.
