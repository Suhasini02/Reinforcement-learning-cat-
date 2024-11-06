CAT1
Definition • Objective: A news value maximiser: Politically and commercially affiliated media companies are tasked with maximizing the views for certain articles more than others. Build a system that maximises the views for these “aligned” articles

From my research, When compared to UCB OR Elipson_greedy, I have felt that Thompson sampling concept is a better approach as it uses probability distributions (like the Beta distribution) to model the uncertainty about each option's reward. It adjusts their strategy as they learn more. As the goal is to maximize rewards in a dynamic and uncertain environment. It Avoids greedy search and ultimately leads to better results.
It Avoids greedy search and ultimately leads to better results. I have referred this document( https://web.stanford.edu/~bvr/pubs/TS_Tutorial.pdf)
The system using Thompson Sampling to optimize the selection of articles for promotion, aiming to maximize views. It treats each article as an "arm" in a multi-armed bandit problem, where the algorithm balances between exploring new articles and exploiting those that have previously shown high engagement. By maintaining and updating probability distributions (using alpha and beta parameters) for each article based on the received rewards (views), the system gradually learns which articles are most likely to attract views and prioritizes promoting those, while still occasionally testing less-promoted options to ensure all possibilities are considered.
A simple code I performed implementing my understanding is attached.


CAT2
