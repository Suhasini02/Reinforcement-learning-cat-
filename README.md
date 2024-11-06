CAT1
Definition • Objective: A news value maximiser: Politically and commercially affiliated media companies are tasked with maximizing the views for certain articles more than others. Build a system that maximises the views for these “aligned” articles

From my research, When compared to UCB OR Elipson_greedy, I have felt that Thompson sampling concept is a better approach as it uses probability distributions (like the Beta distribution) to model the uncertainty about each option's reward. It adjusts their strategy as they learn more. As the goal is to maximize rewards in a dynamic and uncertain environment. It Avoids greedy search and ultimately leads to better results.
It Avoids greedy search and ultimately leads to better results. I have referred this document( https://web.stanford.edu/~bvr/pubs/TS_Tutorial.pdf)
The system using Thompson Sampling to optimize the selection of articles for promotion, aiming to maximize views. It treats each article as an "arm" in a multi-armed bandit problem, where the algorithm balances between exploring new articles and exploiting those that have previously shown high engagement. By maintaining and updating probability distributions (using alpha and beta parameters) for each article based on the received rewards (views), the system gradually learns which articles are most likely to attract views and prioritizes promoting those, while still occasionally testing less-promoted options to ensure all possibilities are considered.
A simple code I performed implementing my understanding is attached.


CAT2

Let’s create a concrete example of RL unlearning on a 100x100 grid, with obstacles and a dynamic environment where the agent needs to forget and relearn certain policies. In this example, we'll have an agent that is initially trained to find the shortest path to a goal on the grid, but later we introduce a new obstacle that blocks the path, forcing the agent to “unlearn” its previous policy and adapt to the new environment.

Problem Setup
Grid Environment: A 100x100 grid with random obstacles.
Agent’s Goal: Start from a defined point and reach a goal point.
Rewards:
Positive reward for reaching the goal.
Negative reward for hitting an obstacle.
Small negative reward for each step to encourage finding the shortest path.
Key Steps for RL Unlearning
Initial Training: Train the agent using Q-learning to find an optimal path to the goal in the grid.
Environment Change: Add a new obstacle that blocks the optimal path.
Unlearning Process: Reset the Q-values for affected states, increase exploration, and retrain the agent to find a new path.

Explanation of Code Workflow
Initial Training: The agent learns the best path to the goal by exploring the grid.
Adding a New Obstacle: We place an obstacle in the agent’s path, forcing it to find a new way.
Unlearning Mechanism:
We reset the Q-values around the new obstacle so the agent doesn’t rely on old, invalid information.
We also increase exploration, so the agent tries different routes instead of sticking to previously learned paths.
Retraining: The agent explores new paths and learns a new policy that avoids the newly introduced obstacle.
Results and Adaptation
This process helps the agent “unlearn” outdated paths and learn a new optimal route that adapts to the updated environment. By adjusting exploration and selectively resetting Q-values, the agent can efficiently adapt without relearning everything from scratch.
