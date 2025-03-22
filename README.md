Value Iteration for 4x4 GridWorld
Introduction
This project implements Value Iteration for solving a 4x4 GridWorld using the Bellman equation. The agent starts at the top-left corner (state 0) and tries to reach the bottom-right corner (state 15).

Problem Setup
The environment is a 4×4 grid (16 states).

The agent can move up, down, left, or right, with equal probability.

Every move incurs a reward of -1, except for the terminal state (bottom-right, state 15), which has a reward of 0.

The goal is to compute the optimal value function for each state using Value Iteration.

Algorithm (Value Iteration)
Initialize

Set grid size = 4x4 (16 states).

Initialize the value function V(s) = 0 for all states.

Define rewards:

R(s) = -1 for every move.

R(terminal state) = 0.

Set discount factor (γ) = 1.0 (no discounting).

Define the convergence threshold θ = 1e-4.

Define possible actions: Up, Down, Left, Right.

Value Iteration Loop (Until Convergence)

Copy the current value function V_new = V.

For each state s (excluding terminal state):

Compute the expected value for moving in each direction.

Apply the Bellman equation:

𝑉
(
𝑠
)
=
1
4
∑
𝑠
′
[
𝑅
+
𝛾
𝑉
(
𝑠
′
)
]
V(s)= 
4
1
​
  
s 
′
 
∑
​
 [R+γV(s 
′
 )]
Track the maximum change in values (delta) to check for convergence.

Update V = V_new.

Stop if delta < θ.

Output the Final Value Function

The computed value function shows how good each state is, given optimal movement towards the goal.

Expected Output (Example)
lua
Copy
Edit
[[-59.42  -57.42  -54.28  -51.71 ]
 [-57.42  -54.56  -49.71  -45.13 ]
 [-54.28  -49.71  -40.85  -29.99 ]
 [-51.71  -45.13  -29.99   0.    ]]
Values become less negative as the agent gets closer to the goal.

The terminal state (bottom-right) has a value of 0, since it's the goal.

How to Run the Code
Install Python (if not already installed)

sh
Copy
Edit
sudo apt install python3  # Linux
brew install python3      # macOS
Run the Python script

sh
Copy
Edit
python value_iteration.py
(Assuming the script is saved as value_iteration.py.)

Future Improvements
Implement Policy Iteration for policy extraction.

Extend the environment with obstacles or stochastic rewards.

Apply the method to larger grid sizes (e.g., 8×8, 10×10).

License
This project is released under the MIT License.

