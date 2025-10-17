# Treasure-Hunt-Pathfinding

## Overview
This project implements the A* informed search algorithm to solve a treasure hunting problem in a hexagonal maze. The maze contains treasures, traps, and rewards that dynamically affect movement cost and energy consumption. The objective is to collect all treasures with the minimum total cost, considering the effects of traps and rewards. This project demonstrates the ability to apply heuristic search, problem formulation, and algorithm design in an environment with dynamic state transitions and multiple constraints.

## Key Features
- **A\* Search Implementation:** Combines actual cost g(n) and heuristic h(n) to find the optimal path.
- **Hexagonal Maze Structure:** Each node has six possible neighbors depending on even/odd column geometry.
- **Dynamic Cost System:** Movement cost varies depending on active traps or rewards.
- **Traps & Rewards Logic:**
  1. **Reward 1:** Halves energy cost for all future moves.
  2. **Reward 2:** Halves step cost for all future moves.
  3. **Trap 1:** Doubles energy cost.
  4. **Trap 2:** Doubles step cost.
  5. **Trap 3:** Triggers a forced two-cell jump, consuming energy but not steps.
  6. **Trap 4:** Ends the program immediately.
- **Visualization:** Displays the maze, path, traps, rewards, and treasures using Matplotlib.
- **Console Output:** Prints the full path sequence, number of treasures collected, total cost, and step count.

## Technical Details
### Algorithms Used
- **A\* Search Algorithm:**
  1. Combines g(n) (actual cost so far) and h(n) (estimated cost to goal).
  2. Heuristic: Hexagonal Manhattan Distance, computed using cube coordinates for accuracy.
  3. Optimal and admissible for this environment.

### Cost Function
Move Cost = Step Multiplier × Energy Multiplier
- **Affected dynamically by traps and rewards:**
  1. **Best case:** 0.25 per move (both rewards active).
  2. **Worst case:** 4.0 per move (both traps active).

### Heuristic Function
- Uses the minimum hex distance to any remaining treasure.
- Updated dynamically as treasures are collected to maintain admissibility and efficiency.

### Transition Model
- Determines legal moves within the maze.
- Applies traps, rewards, and treasures dynamically after each state transition.
- Handles special effects such as forced movement for Trap 3 and immediate termination for Trap 4.

## Output and Visualization
### Console Output
- Displays:
  1. Start position.
  2. Sequence of all steps taken.
  3. Type of cell at each step (e.g., Trap, Reward, Treasure).
  4. Total steps and energy cost.

### Plotted Map
- Each hexagonal cell labeled with coordinates and special cell types.
- **Red line:** Path taken.
- **Green circle:** Start.
- **Blue square:** End.
- **Black dotted line:** Forced move caused by Trap 3.

## Results Summary
- **Start Position:** (5, 0)
- **Treasures Collected:** 4 / 4
- **Total Physical Steps:** 12.0
- **Total Cost:** 8.0
- **Outcome:** Successfully collects all treasures using optimal path while applying correct trap and reward logic.

## Evaluation
- **Algorithm Performance:** A* successfully finds the optimal path while considering traps, rewards, and obstacles.
- **Heuristic Efficiency:** Hex Manhattan distance ensures admissibility and consistency.
- **Complexity:** Time & Space: O(N × C), where N = grid cells and C = possible state combinations.
- **Limitations:** Scalability decreases with larger grids due to exponential state growth.

## Technologies Used
- Python
- Matplotlib
- NumPy
- Spyder

## Reflection
This project strengthened our understanding of heuristic search and teamwork. We learned how to model a complex environment, handle dynamic costs, and implement an efficient A* search algorithm. Through collaboration and problem-solving, we successfully created a system that balances algorithmic logic, visual clarity, and functional accuracy.

## Credits
**Developer:**
1. Goh Irene
2. Kelly Jong Qiao Jie
3. Ng Soon Teck
4. Ong Boon Heng
5. Sum Hon You
6. Wong Yoong Xuen <br>

**Course:** Bachelor of Science (Honours) in Computer Science <br>
**Institution:** Faculty of Engineering and Technology, Sunway University
