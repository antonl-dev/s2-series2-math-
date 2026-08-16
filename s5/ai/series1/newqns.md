Here are all the **newly discovered Module 1 and Module 2 AI questions** extracted directly from your newly uploaded PDF documents (including the **Series Test II** and **End-Semester Examination** papers for Course Code **23ERT503 / 24ERT503**).

The solutions below are fully detailed and written proportional to their assigned marks.

---

# NEW QUESTION BANK SOLUTIONS (MODULE 1 & MODULE 2)

---

## PART A: 2-MARK QUESTIONS

### Q1. Identify the suitable machine learning approach used for the given task: "An online music app wants to automatically group songs with similar audio features (like tempo, rhythm, and pitch) without predefined categories."
* **Machine Learning Approach:** **Unsupervised Learning (Clustering)** (specifically algorithms like K-Means or Hierarchical Clustering).
* **Justification:** The task involves discovering natural patterns or groupings in unlabeled input data without any prior training labels or predefined categories.

---

### Q2. Mention any two advantages of A* search algorithm.
1. **Optimal and Complete:** A* is guaranteed to find the shortest/least-cost path to the goal if the heuristic function $h(n)$ is **admissible** (never overestimates cost) and **consistent** (monotonic).
2. **Informed Efficiency:** By using both past cost $g(n)$ and estimated future cost $h(n)$, it expands significantly fewer nodes compared to uninformed search strategies like BFS or Uniform Cost Search.

---

### Q3. What is an environment in AI?
An **environment** in AI is the external world, context, or software framework within which an intelligent agent operates. It continuously provides **percepts** (sensor readings) to the agent and receives **actions** (executed via actuators), updating its internal state as a result.

---

## PART B: 4 to 8-MARK QUESTIONS

### Q4. Three factories A, B, and C of an electric bulb manufacturing company produce 35%, 35%, and 30% of the total output, respectively. Approximately 1.5%, 1%, and 2% of the bulbs produced by these factories are known to be defective. If a randomly selected bulb manufactured by the company was found to be defective, what is the probability that the bulb was manufactured in Factory A? [4 Marks]

#### Solution:

**Step 1: Define Events**
* Let $E_1, E_2, E_3$ be the events that the bulb was produced by Factory A, B, and C, respectively.
* Let $D$ be the event that the selected bulb is defective.

**Step 2: List Prior and Conditional Probabilities**
* **Prior Probabilities:**
  $$P(E_1) = 0.35, \quad P(E_2) = 0.35, \quad P(E_3) = 0.30$$
* **Likelihoods (Conditional Defect Probabilities):**
  $$P(D|E_1) = 0.015, \quad P(D|E_2) = 0.010, \quad P(D|E_3) = 0.020$$

**Step 3: Total Probability of Defective Bulb $P(D)$**
$$P(D) = P(E_1)P(D|E_1) + P(E_2)P(D|E_2) + P(E_3)P(D|E_3)$$
$$P(D) = (0.35 \times 0.015) + (0.35 \times 0.010) + (0.30 \times 0.020)$$
$$P(D) = 0.00525 + 0.00350 + 0.00600 = 0.01475$$

**Step 4: Apply Bayes' Theorem**
Find $P(E_1|D)$, the probability the bulb came from Factory A given it is defective:
$$P(E_1|D) = \frac{P(E_1) \cdot P(D|E_1)}{P(D)}$$
$$P(E_1|D) = \frac{0.35 \times 0.015}{0.01475} = \frac{0.00525}{0.01475} = \frac{525}{1475} = \frac{21}{59} \approx 0.3559\ (35.59\%)$$

---

### Q5. Describe the percepts and actions in the vacuum cleaner environment. Why is this problem considered a good example to illustrate agent-environment interaction? [6 + 2 = 8 Marks]

#### 1. Percepts and Actions in Vacuum Environment [6 Marks]
* **Percept Representation:**
  The agent's sensors read a two-element tuple specifying location and state:
  $$\text{Percept} = [\text{Location}, \text{Status}]$$
  * $\text{Location} \in \{\text{Room A}, \text{Room B}\}$
  * $\text{Status} \in \{\text{Clean}, \text{Dirty}\}$
  * *Example Percept:* $[\text{Room A}, \text{Dirty}]$

* **Actions Space:**
  The agent can invoke four discrete commands:
  1. `Left`: Move the agent to Room A.
  2. `Right`: Move the agent to Room B.
  3. `Suck`: Remove dirt from the current room.
  4. `NoOp`: Remain idle.

* **Percept Sequence Mapping (Simple Reflex Agent Function):**
  * $[\text{Room A}, \text{Dirty}] \to \text{Suck}$
  * $[\text{Room A}, \text{Clean}] \to \text{Right}$
  * $[\text{Room B}, \text{Dirty}] \to \text{Suck}$
  * $[\text{Room B}, \text{Clean}] \to \text{Left}$

---

#### 2. Why it is a Good Example for Agent-Environment Interaction [2 Marks]
1. **Minimalist & Formalized:** It cleanly isolates core AI mechanics (percept mapping, state transitions, rational decision-making) without the mathematical complexity of continuous physical dynamics.
2. **Versatile Benchmark:** It serves as a unified case study to compare different agent architectures (Simple Reflex vs. Model-Based vs. Goal-Based) and test environment properties (Fully vs. Partially Observable, Deterministic vs. Stochastic).

---

### Q6. Describe any four categories of environments in which intelligent agents can function. [4 Marks]

1. **Fully Observable vs. Partially Observable:**
   * *Fully Observable:* The agent's sensors provide complete information about the environment's state at any point in time (e.g., Chess).
   * *Partially Observable:* Noise, occlusion, or missing sensors hide parts of the true state (e.g., Poker, driving in heavy rain).

2. **Deterministic vs. Stochastic:**
   * *Deterministic:* The next state is entirely determined by the current state and the agent's action (e.g., Sudoku).
   * *Stochastic:* Unpredictable or random factors cause uncertain outcomes (e.g., Weather forecasting, self-driving cars).

3. **Episodic vs. Sequential:**
   * *Episodic:* Each episode is self-contained; actions taken in one episode do not affect future episodes (e.g., Image defect classification on a conveyor belt).
   * *Sequential:* Current decisions impact all future states and choices (e.g., Chess, route planning).

4. **Static vs. Dynamic:**
   * *Static:* The environment remains unchanged while the agent takes time to deliberate (e.g., Turn-based board games).
   * *Dynamic:* The environment continues to evolve while the agent is deciding what action to take (e.g., Real-time stock trading).

---

### Q7. Differentiate Simple reflex agent and Goal-based agent with the help of an example. [4 Marks]

| Feature | Simple Reflex Agent | Goal-Based Agent |
| :--- | :--- | :--- |
| **Primary Basis** | Reacts purely to the **current percept** using fixed `condition-action` rules. | Evaluates actions based on whether they bring the agent closer to a **desired goal state**. |
| **Memory / State** | No internal memory or state history. | Maintains internal models of the world and future states. |
| **Adaptability** | Rigid; breaks if environmental conditions change outside rule definitions. | Flexible; can adapt to new goals without rewriting base code. |
| **Example** | **Thermostat:** Turns on heater if current temp $< 20^\circ\text{C}$. | **GPS Navigation:** Evaluates route options to minimize travel time to a specified destination address. |
