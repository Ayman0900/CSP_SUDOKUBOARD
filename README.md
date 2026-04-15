# CSP_SUDUKOBOARD
# Sudoku Solver using CSP (Constraint Satisfaction Problem)

This project implements a **Sudoku Solver** using **Constraint Satisfaction Problem (CSP)** techniques in Python. It combines:

* AC-3 Algorithm (Arc Consistency)
* Backtracking Search
* Forward Checking
* Minimum Remaining Values (MRV) Heuristic

to efficiently solve Sudoku puzzles of varying difficulty.

---

## Features

* Solves 9×9 Sudoku puzzles
* Supports multiple difficulty levels (easy → very hard)
* Uses constraint propagation (AC-3) for optimization
* Tracks:

  * Number of backtracking calls
  * Number of failures
* Clean and modular implementation

---

## Project Structure

```
.
├── sudoku_solver.py
├── easy.txt
├── medium.txt
├── hard.txt
├── veryhard.txt
└── README.md
```

---

## Input Format

Each Sudoku puzzle is stored in a `.txt` file with:

* 9 lines
* Each line contains 9 digits (0–9)
* `0` represents an empty cell

### Example:

```
530070000
600195000
098000060
800060003
400803001
700020006
060000280
000419005
000080079
```

---

## How It Works

### 1. CSP Modeling

* Each cell = variable `(row, col)`
* Domain = `{1–9}` (or fixed if already filled)
* Constraints:

  * Row uniqueness
  * Column uniqueness
  * 3×3 grid uniqueness

### 2. AC-3 Algorithm

* Enforces arc consistency
* Reduces domains before search begins

### 3. Backtracking Search

* Uses recursion to assign values
* Stops when all variables are assigned

### 4. Heuristics and Optimization

* MRV (Minimum Remaining Values): chooses the most constrained variable
* Forward Checking: prunes invalid values early

---

## How to Run

### Step 1: Clone the repository

```
git clone https://github.com/your-username/sudoku-csp-solver.git
cd sudoku-csp-solver
```

### Step 2: Run the script

```
python sudoku_solver.py
```

---

## Output

For each puzzle, the program prints:

* Solved Sudoku grid
* Number of backtracking calls
* Number of failures

### Example:

```
--- Solving easy.txt ---
534678912
672195348
...
Calls: 15 | Failures: 2
```

---

## Key Functions

| Function                       | Description                                     |
| ------------------------------ | ----------------------------------------------- |
| `SudokuCSP`                    | Initializes variables, domains, and constraints |
| `ac3()`                        | Applies arc consistency                         |
| `revise()`                     | Removes inconsistent values                     |
| `backtrack()`                  | Recursive solver                                |
| `forward_check()`              | Prunes domains during search                    |
| `select_unassigned_variable()` | MRV heuristic                                   |
| `solve_sudoku()`               | Main solver function                            |

---

## Performance

* Fast for easy and medium puzzles
* Efficient pruning reduces search space
* Handles hard puzzles with deeper recursion

---

## Requirements

* Python 3.x
* No external libraries required

---

## Future Improvements

* GUI for visual solving
* Support for different grid sizes
* Parallel solving
* Heuristic tuning

---

## License

This project is open-source and available under the MIT License.

---

## Contribution

Feel free to fork this repo, open issues, or submit pull requests.

---

## Author

Developed as a demonstration of CSP techniques in Artificial Intelligence.
