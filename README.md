# SoC-26-KernelMind
## Week 1: Process Abstractions & Scheduling Mechanics

This week, we lay the foundational groundwork for operating system kernels by exploring how the OS virtualizes the CPU, maps process states, exposes system APIs, and balances execution efficiency with computational fairness.

Here is what you need to do:

1. **Read the OSTEP Chapters:** Inside the folder, you'll find the reading list covering **Chapters 4, 5, 7, and 8** from *Operating Systems: Three Easy Pieces*. If you want to check out the original text or read ahead, you can always visit [ostep.org](https://pages.cs.wisc.edu/~remzi/OSTEP/).
2. **Complete Assignment 1:** The assignment sheet has also been uploaded directly into the `week1/` folder. Please make sure you read through the chapters thoroughly **before** attempting these questions, as they will directly test your understanding of scheduling mechanics and process states.

*Note: The submission link for Assignment 1 will be shared with you all later on.*

## Week 2: Foundations of Reinforcement Learning

This week, we shift our focus from core operating system mechanics to the foundations of Reinforcement Learning. We will explore how an autonomous agent interacts with an environment, transitions between discrete state buckets, and dynamically optimizes its actions through trial and error. The Sutton & Barto textbook is uploaded in the `week2/` folder. David Silver's lecture materials and video links can be accessed [here](https://davidstarsilver.wordpress.com/teaching/). An assignment covering these reinforcement learning concepts will be uploaded here soon. Please review the following resources thoroughly by then to prepare for the assignment.
### Recommended Viewing (David Silver Lectures)

* **Lecture 1:** Introduction to RL
* **Lecture 2:** Markov Decision Processes
* **Lecture 4:** Model-Free Prediction
* **Lecture 5:** Model-Free Control

### Recommended Reading (Sutton & Barto Textbook)

* **Chapter 1 (Sections 1.1 – 1.4):** Introduction to RL elements (Policy, Reward, Value Function)
* **Chapter 3 (Sections 3.1 – 3.3):** The Agent-Environment Interface
* **Chapter 3 (Sections 3.5 – 3.6):** Policies and Value Functions
* **Chapter 6 (Sections 6.1 – 6.5):** Temporal-Difference Learning and Q-Learning

## Week 6: Deep Learning, Pytorch foundations and Deep RL

We made an agent that was a policy selector based on the state of our scheduler and given set of policies. In general, we would need a stronger hold of it directly giving us the process to execute by using its own learned policies as per the environment.

So we transition from Q-tables to Deep Q-Networks (Value-Based RL). We use neural networks as function approximators to predict our Q values. We can also extend this into Policy-Based RL in which we directly output the probability of choosing an action, that can be a bonus reading and exploration...

For this, we first need a primer on neural networks and the deep learning library PyTorch for easier and efficient implementation, so we divide this into 3 parts, you can cover them throughout this week at your pace.


### Part 1: Neural Networks and implementation
*You can find the PML book pdf in `week6-7/resources/`.*

1. **3Blue1Brown - Neural Networks series**
   https://www.youtube.com/playlist?list=PLZHQObOWTQDNU6R1_67000Dx_ZCJB-3pi
   *Watch the first 3-4 videos to get intuitive understanding of how neural networks, weights, biases, and gradient descent actually work.*

2. **PyTorch Documentation - Learn the Basics**
   https://docs.pytorch.org/tutorials/beginner/basics/intro.html#
   *Read the "Learn the Basics" section to learn the syntax for defining layers and setting up a basic training loop. You can also see the youtube series in navigation.*

3. **PML(Probabilistic Machine Learning) book - Introduction & Chapter 13 (Neural Networks)**
   *Read the introduction and Chapter 13, feel free to skim through the heavy backpropagation calculus and further sections. This is works as a book you can follow prallely with 3Blue1Brown videos if something is unclear.*

---

### Part 2: Deep RL Theory (The Function Approximation Bridge)
*Please find the correct edition and version of Sutton & Barto book in `week6-7/resources/`. Below is the course link to find lecture slides and the videos of David Silver.*

1.  **David Silver (DeepMind) - Lecture 6: Value Function Approximation**
    https://davidstarsilver.wordpress.com/teaching/
   *Watch this lecture to learn how the Bellman Equation is used to update neural network weights instead of static Q-table cells.*

2.  **Sutton & Barto - Chapter 9(On-policy Prediction with Approximation) & Section 11.3(The Deadly Triad)**
   *Read Chapter 9 for the basics of using neural networks for value prediction, and study Section 11.3 to see why combining function approximation, bootstrapping, and off-policy updates (like in DQN) can destabilize your agent.*

3.  **(Optional) David Silver (DeepMind) - Lecture 7: Policy Gradient Methods**
    *Watch this to explore an alternative architecture where the network completely bypasses value estimation and directly outputs actions.*

4.  **(Optional) Sutton & Barto - Chapter 13(Policy Gradient Methods)**
    *Read the Policy Gradient Theorem for optimizing action selections directly.*
---

### Part 3: Code Implementation Blueprints
*You can also find the code files in the `week6-7/resources/` folder of this repo. This includes some clean implementations of algorithms which we can modfiy and use in our new agent.*


1. **CleanRL - Deep Q-Network (dqn.py)**
   https://github.com/vwxyzjn/cleanrl/blob/master/cleanrl/dqn.py
   *Read this top-to-bottom to learn how to implement an Experience Replay Buffer and a Target Network using standard pytorch tensor operations.*

2. **(Optional) CleanRL - Proximal Policy Optimization (ppo.py)**
   https://github.com/vwxyzjn/cleanrl/blob/master/cleanrl/ppo.py
   *Look at this script to explore how a network outputs a probability distribution over actions.*

Do checkout this github repo for further exploration - https://github.com/vwxyzjn/cleanrl