# Sliding Puzzle
![Puzzle](logo.png)
  **This Java-based project implements an A\* search algorithm to solve the sliding puzzle game. The goal of the game is to rearrange the tiles in n-by-n grid to achieve a specific target configuration using as few moves as possible.**

## How it Works

The project consists of two main components: `Board class`  and `Solver class`.

### Board Class

The `Board` class represents the game board and provides methods to manipulate and analyze it. The class includes the following key methods:

- `Board(int[][] tiles)`: Constructs a board from a 2D array of tiles.
- `toString()`: Returns a string representation of the board.
- `dimension()`: Returns the dimension of the board.
- `hamming()`: Returns the number of tiles out of place.
- `manhattan()`: Returns the sum of Manhattan distances between tiles and the goal.
- `isGoal()`: Checks if the board is the goal board.
- `equals(Object y)`: Checks if the board is equal to another object.
- `neighbors()`: Returns an iterable collection of neighboring boards.
- `twin()`: Returns a board obtained by exchanging any pair of tiles.

### Solver Class

The `Solver` class implements the A* search algorithm to find the optimal solution for the puzzle. It takes an initial board as input and provides methods to determine solvability, minimum number of moves, and the sequence of boards in the shortest solution. The class includes the following key methods:

- `Solver(Board initial)`: Constructs a solver for the given initial board.
- `isSolvable()`: Checks if the initial board is solvable.
- `moves()`: Returns the minimum number of moves to solve the puzzle.
- `solution()`: Returns an iterable collection of boards representing the shortest solution.

## Contributing
Contributions are welcome! If you find a bug or have a suggestion, please open an issue or submit a pull request.

## Getting Started

To use the 8 puzzle solver, follow these steps:

1. Clone the repository to your local machine.
2. Import the project into your preferred Java IDE.
3. Build the project to resolve dependencies.
4. Use the `PuzzleChecker` class to solve puzzle instances from files or modify the `main` method of `Solver` class to solve custom puzzles.

## Examples

To run the solver and solve puzzles from files, you can use the `PuzzleChecker` class. The class reads puzzle instances from files and prints the minimum number of moves required to solve each puzzle.

```shell
java PuzzleChecker puzzle1.txt puzzle2.txt puzzle3.txt
```

To solve custom puzzles, you can modify the `main` method of the `Solver` class. Create an instance of the `Board` class with the desired initial configuration, and pass it to the `Solver` constructor. Then, use the methods of the `Solver` class to access the solution.

```java
int[][] tiles = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 0}
};

Board initial = new Board(tiles);
Solver solver = new Solver(initial);

if (solver.isSolvable()) {
    int moves = solver.moves();
    Iterable<Board> solution = solver.solution();
    // Process the solution
} else {
    // Puzzle is unsolvable
}
```

## Optimization

The A* search algorithm includes an optimization to avoid exploring duplicate search nodes. When considering the neighbors of a search node, a neighbor is not enqueued if its board is the same as the board of the previous search node in the game tree. This optimization reduces unnecessary exploration and improves the efficiency of the algorithm.

## Dependencies

The project has the following dependencies:

- `java.util.Arrays`
- `java.util`
- `Comparator`
- `java.util.PriorityQueue`
- `java.util.Stack`


## Acknowledgments

The A* algorithm used in this project is a classic artificial intelligence algorithm widely used in various problem-solving scenarios.

## References

#### [A* search algorithm](https://en.wikipedia.org/wiki/A*_search_algorithm)
#### [Sliding puzzle](https://en.wikipedia.org/wiki/Sliding_puzzle)

