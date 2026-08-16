Here is **Part 2** of your Question Paper Bank Solutions, focusing strictly on **Module 2 (Foundations of AI, Applications, PEAS, Agent Structures, Environment Properties, and Vacuum Cleaner Case Study)**.

All solutions are written with structural depth proportional to their allotted marks.

---

# MODULE 2: SOLUTIONS (PART 2)

---

## SECTION A: 2-MARK QUESTIONS (MODULE 2)

### Q12. A robot vacuum cleaner senses dust and moves to clean it automatically. What kind of system does this represent, and why is it considered intelligent?
* **Kind of System:** It represents a **Simple Reflex Agent** (or Goal-Based Agent depending on target state tracking) operating within a dynamic physical environment.
* **Why it is Considered Intelligent:** It exhibits **rationality** by mapping percept sequences (dust sensors) to appropriate actions (suck/clean) to maximize its performance measure (cleanliness of the area) autonomously without explicit continuous human intervention.

---

### Q13. Define the PEAS representation of an intelligent agent. Give one example.
* **PEAS Definition:** PEAS stands for **P**erformance Measure, **E**nvironment, **A**ctuators, and **S**ensors. It is the formal specification required when defining the task environment for an intelligent agent.
* **Example (Automated Taxi Driver):**
  * **P (Performance Measure):** Safe, fast, legal, comfortable trip, maximize profits.
  * **E (Environment):** Roads, other traffic, pedestrians, weather conditions.
  * **A (Actuators):** Steering wheel, accelerator, brake, signal indicators, horn.
  * **S (Sensors):** Cameras, LIDAR, radar, GPS, speedometer, engine sensors.

---

### Q14. List the possible actions of a vacuum cleaner agent in a two-room environment.
In a standard two-room environment (Rooms A and B), the action space of the agent consists of:
1. `Right` (move to Room B)
2. `Left` (move to Room A)
3. `Suck` (clean dust in the current room)
4. `NoOp` (No Operation / stay idle if both rooms are clean)

---

### Q15. Give one example each for AI in education and AI in agriculture.
* **AI in Education:** **Adaptive Learning Systems / Intelligent Tutoring Systems (ITS)** like *DreamBox* or *Knewton*, which personalize learning paths and difficulty based on individual student performance.
* **AI in Agriculture:** **Precision Farming & Crop Health Monitoring Systems** like *John Deere’s See & Spray* or *Plantix*, using computer vision to detect crop diseases, weeds, and soil nutrient deficiencies.

---

### Q16. What is an environment in AI?
In Artificial Intelligence, an **environment** is the external setting or context in which an agent operates. It provides **percepts** (sensor inputs) to the agent and receives **actions** (via actuators) from the agent, changing its internal state in response to those actions.

---

## SECTION B: 3 to 5-MARK QUESTIONS (MODULE 2)

### Q17. Mention any four practical applications of Artificial Intelligence and give a brief explanation of each. [5 Marks]

1. **Healthcare & Medical Diagnostics:**
   AI-powered computer vision models analyze medical imaging (X-rays, CT scans, MRIs) to assist radiologists in early detection of tumors, fractures, and retinal diseases with high precision.

2. **Autonomous Transportation (Self-Driving Vehicles):**
   Vehicles utilize deep learning networks, LIDAR, and computer vision algorithms to perceive surrounding traffic, detect lane markings, predict pedestrian movement, and navigate routes safely.

3. **Natural Language Processing (NLP) & Virtual Assistants:**
   Large Language Models (LLMs) and conversational agents (e.g., ChatGPT, Siri) process and generate natural human language to assist in customer support, translation, and automated content summary.

4. **Finance & Automated Fraud Detection:**
   Machine learning algorithms evaluate millions of banking transactions in real-time to detect anomalous transaction patterns, preventing credit card fraud and automating high-frequency trading strategies.

---

### Q18. Explain the working of a goal-based vacuum cleaner agent with an example. [5 Marks]

#### Concept
A **Goal-Based Agent** goes beyond condition-action rules by combining environment state information with explicit **goal descriptions**. It chooses actions specifically calculated to achieve desirable target states.

```
                  +-------------------+
                  |      Sensors      |
                  +---------+---------+
                            |
                            v
                  +-------------------+
                  |  What state the   |
                  |  world is in now  |
                  +---------+---------+
                            |
                            v
+-----------------+  +--------------+  +------------------+
| What my actions |->| What it will |->| What goals I     |
| do              |  | be like next |  | should achieve   |
+-----------------+  +--------------+  +--------+---------+
                                                |
                                                v
                                       +------------------+
                                       | Select Action to |
                                       | reach Goal       |
                                       +--------+---------+
                                                |
                                                v
                                       +------------------+
                                       |    Actuators     |
                                       +------------------+
```

#### Working Principle
1. **Percept Processing:** The agent receives sensor data regarding its location and dirt status.
2. **Internal State Maintenance:** It retains an internal model of the world (e.g., "Room A is Clean, Room B is Dirty").
3. **Goal Formulation:** The goal is explicitly defined: `Goal = Both Room A and Room B are Clean`.
4. **Action Selection:** Instead of merely reacting to current dust, it evaluates: *"If I am in Room A and it is clean, moving Right gets me closer to achieving the goal of cleaning Room B."*

#### Example
Suppose the agent is placed in **Room A** and Room A is already clean, but **Room B is dirty**.
* **Simple Reflex Agent:** Has no goal; if Room A is clean, its rule might tell it to do `NoOp` or wander endlessly.
* **Goal-Based Agent:** Evaluates its goal state (`Clean(A) AND Clean(B)`). It senses `Clean(A)`, updates its internal state, determines that `Dirty(B)` prevents goal satisfaction, selects the action `Right`, and once in B, executes `Suck` to satisfy the overall goal.

---

### Q19. Describe any four categories of environments in which intelligent agents can function. [4 Marks]

1. **Fully Observable vs. Partially Observable:**
   * **Fully Observable:** The agent's sensors give it access to the complete state of the environment at any given time (e.g., Chess board).
   * **Partially Observable:** Sensor noise, limited ranges, or missing information obscure parts of the state (e.g., Poker, driving in heavy fog).

2. **Deterministic vs. Stochastic:**
   * **Deterministic:** The next state of the environment is completely determined by the current state and the action executed by the agent (e.g., Crossword puzzles).
   * **Stochastic:** Uncertainty exists; outcomes cannot be fully predicted due to random elements or other agents (e.g., Weather forecasting, driving).

3. **Episodic vs. Sequential:**
   * **Episodic:** The agent's experience is divided into independent atomic episodes. Current decisions do not affect future episodes (e.g., Defect classification on assembly lines).
   * **Sequential:** Current actions affect all future decisions and states (e.g., Chess, steering a car).

4. **Static vs. Dynamic:**
   * **Static:** The environment does not change while the agent is deliberating or making a decision (e.g., Turn-based board games).
   * **Dynamic:** The environment continuously changes while the agent is deliberating (e.g., Autonomous taxi driving).

---

### Q20. Differentiate Simple reflex agent and Goal-based agent with the help of an example. [4 Marks]

| Feature | Simple Reflex Agent | Goal-Based Agent |
| :--- | :--- | :--- |
| **Decision Basis** | Acts purely based on the **current percept**, ignoring historical memory. | Acts based on **current state + internal goal states**. |
| **Logic** | Uses direct Condition-Action rules (`IF condition THEN action`). | Uses planning/search to select actions that bring it closer to a goal. |
| **Adaptability** | Rigid; fails if environment details are missing or hidden. | Flexible; can adapt to new goals without rewriting base logic. |
| **Internal Model** | None (No memory of previous states). | Maintains internal model/world state tracking. |
| **Example** | **Vacuum Cleaner:** If current square is dirty $\rightarrow$ Suck. If clean $\rightarrow$ move. | **Automated Taxi:** Evaluates multiple routes to reach destination efficiently based on user goals. |

---

## SECTION C: 5 to 8-MARK QUESTIONS (MODULE 2)

### Q21. Explain the structure of intelligent agents and discuss different types. [5 / 8 Marks]

#### Structure of Intelligent Agents
An **Agent** is anything that perceives its environment through sensors and acts upon that environment through actuators.
$$\text{Agent} = \text{Architecture} + \text{Program}$$
* **Architecture:** The computing device/hardware platform with physical sensors and actuators.
* **Agent Program:** The concrete implementation of the agent function mapping percept sequences to actions.

```
                   +-------------------+
                   |    Environment    |
                   +--+-------------+--+
                      |             ^
             Percepts |             | Actions
                      v             |
               +------+-------------+-----+
               |       Sensors            |
               |                          |
               |      AGENT PROGRAM       |
               |                          |
               |      Actuators           |
               +--------------------------+
```

#### Four Basic Types of Agent Programs

1. **Simple Reflex Agents:**
   * Selects actions based *only* on the current percept, ignoring history.
   * Built on `condition-action` rules.
   * *Limitation:* Operates successfully only if the environment is fully observable.

2. **Model-Based Reflex Agents:**
   * Maintains an **internal state** to keep track of unobserved parts of the current environment.
   * Uses a model of "how the world works" to update internal memory over time.

3. **Goal-Based Agents:**
   * Combines internal state tracking with explicit **goal information**.
   * Evaluates possible outcomes to choose actions that lead to goal completion using search/planning algorithms.

4. **Utility-Based Agents:**
   * Uses a explicit **utility function** to measure "how happy/satisfied" the agent will be in a particular state.
   * Selects actions that maximize expected utility when tradeoffs exist between competing goals (e.g., speed vs. safety).

---

### Q22. Draw and explain the state space diagram for a two-room vacuum cleaner problem. [5 Marks]

#### Environment Setup
* **Rooms:** Two rooms, $A$ and $B$.
* **State Variables:** 
  1. Vacuum Location: $A$ or $B$ ($2$ possibilities)
  2. Dirt status of Room A: Dirty ($D$) or Clean ($C$) ($2$ possibilities)
  3. Dirt status of Room B: Dirty ($D$) or Clean ($C$) ($2$ possibilities)
* **Total States:** $2 \times 2 \times 2 = 8$ distinct states.

#### State Space Diagram
* **States representation:** $(Location, Status_A, Status_B)$

```
         +-----------------+                    +-----------------+
         |  1: (A, D, D)   |<--- Left / Right ->|  2: (B, D, D)   |
         +--------+--------+                    +--------+--------+
                  |                                      |
             Suck |                                 Suck |
                  v                                      v
         +-----------------+                    +-----------------+
         |  3: (A, C, D)   |<--- Left / Right ->|  4: (B, C, D)   |
         +--------+--------+                    +--------+--------+
                  |                                      |
            Right |                                 Left |
                  v                                      v
         +-----------------+                    +-----------------+
         |  5: (B, C, D)   |                    |  6: (A, D, C)   |
         +--------+--------+                    +--------+--------+
                  |                                      |
             Suck |                                 Suck |
                  v                                      v
         +-----------------+                    +-----------------+
         |  7: (A, C, C)   |<--- Left / Right ->|  8: (B, C, C)   |
         |  [Goal State]   |                    |  [Goal State]   |
         +-----------------+                    +-----------------+
```

#### Description
1. **Actions:** `Left`, `Right`, `Suck`.
2. **Transitions:** Executing `Suck` in a dirty room transforms its status to $C$. Executing `Right` from $A$ shifts location to $B$, and executing `Left` from $B$ shifts location to $A$.
3. **Goal States:** States where both rooms are clean: $(A, C, C)$ or $(B, C, C)$.

---

### Q23. Describe the percepts and actions in the vacuum cleaner environment. Why is this problem considered a good example to illustrate agent-environment interaction? [6 + 2 = 8 Marks]

#### 1. Percepts and Actions in Vacuum Environment [6 Marks]

* **Percepts:**
  The agent receives sensor inputs specifying:
  1. Current location: $\text{Location} \in \{\text{Room A}, \text{Room B}\}$
  2. Dirt status: $\text{Status} \in \{\text{Dirty}, \text{Clean}\}$
  * *Percept Format:* Tuple $[\text{Location}, \text{Status}]$, e.g., $[\text{Room A}, \text{Dirty}]$.

* **Actions:**
  The agent can issue commands to its actuators:
  1. `Left`: Move to the left room.
  2. `Right`: Move to the right room.
  3. `Suck`: Clean the dirt in the current location.
  4. `NoOp`: Do nothing.

* **Agent Function Mapping Example:**
  ```
  Percept Sequence                 -> Action
  -----------------------------------------
  [A, Clean]                       -> Right
  [A, Dirty]                       -> Suck
  [B, Clean]                       -> Left
  [B, Dirty]                       -> Suck
  [[A, Clean], [B, Clean]]         -> NoOp
  ```

---

#### 2. Why it is a Good Example for Agent-Environment Interaction [2 Marks]
1. **Simplicity and Abstraction:** It provides a minimal, discrete, fully dynamic setup without complex real-world continuous physics, making fundamental concepts like states, percept sequences, performance measures, and rationality easy to define mathematically.
2. **Demonstrates Core AI Concepts:** It clearly illustrates all major agent structures (Reflex, Model-based, Goal-based) and environment properties (Observable vs Partially Observable, Deterministic vs Stochastic) within a single controlled scenario.

---

*(This completes all Module 1 and Module 2 solutions from all question papers).*
