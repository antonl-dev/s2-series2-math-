Here is **Part 1 of 2** of your complete, high-density study notes covering **MODULE 1**.

This document integrates every concept, definition, mathematical proof, step-by-step example, and property from your syllabus, exam question papers, and official lecture notes. No details have been omitted or truncated.

---

# MODULE 1: PROBABILITY, RANDOM VARIABLES & BAYES' THEOREM

---

## 1. FUNDAMENTALS OF PROBABILITY

### 1.1 Core Definitions & Terminology
* **Probability:** The quantitative measure of the likelihood that a uncertain event will occur. It is bounded strictly on the closed interval $[0, 1]$.
  $$\text{If } P(E) = 0 \implies \text{Impossible event}$$
  $$\text{If } P(E) = 1 \implies \text{Certain event}$$
* **Experiment:** A process or action that leads to one of several possible outcomes (e.g., rolling a die, tossing a coin).
* **Sample Space ($S$ or $\Omega$):** The set of all possible outcomes of a random experiment.
  * *Coin Toss:* $S = \{H, T\}$
  * *Rolling a Die:* $S = \{1, 2, 3, 4, 5, 6\}$
  * *Tossing 3 Coins:* $S = \{HHH, HHT, HTH, HTT, THH, THT, TTH, TTT\}$
* **Event ($E$):** Any subset of the sample space $S$ ($E \subseteq S$).
* **Classical Probability Formula:**
  $$P(E) = \frac{n(E)}{n(S)} = \frac{\text{Number of favorable outcomes}}{\text{Total number of possible outcomes}}$$

#### Solved Example 1 (Basic Probability):
> **Question:** A bag contains 3 Red balls and 7 Blue balls. Find the probability of selecting a Red ball.
> 
> **Solution:**
> * Total number of outcomes $n(S) = 3 + 7 = 10$.
> * Number of favorable outcomes $n(\text{Red}) = 3$.
> * $P(\text{Red}) = \frac{3}{10} = 0.3$.

---

### 1.2 Event Relationships & Operations

#### 1. Intersection of Events ($A \cap B$ or $A \cdot B$)
The intersection represents the event that **both** event $A$ and event $B$ occur simultaneously in a single experiment.

> **Example:** A fair die is rolled once ($S = \{1,2,3,4,5,6\}$). Let $A$ be the event of getting an even number ($A = \{2,4,6\}$) and $B$ be the event of getting a number $> 3$ ($B = \{4,5,6\}$).
> * $A \cap B = \{4, 6\}$
> * $n(A \cap B) = 2$
> * $P(A \cap B) = \frac{2}{6} = \frac{1}{3}$

#### 2. Mutually Exclusive Events
Two events $A$ and $B$ are mutually exclusive (disjoint) if they **cannot occur at the same time**. They share no common outcomes.
* **Condition:** $A \cap B = \emptyset$
* **Probability:** $P(A \cap B) = 0$
* *Example:* Getting both a Head and a Tail in a single coin toss.

#### 3. Independent Events
Two events are independent if the occurrence or non-occurrence of one event **has no effect whatsoever** on the probability of the occurrence of the other.
* **Mathematical Condition:**
  $$P(A \cap B) = P(A) \times P(B)$$
* *Example:* Flipping a coin twice. The outcome of the first flip ($A = H$) does not affect the outcome of the second flip ($B = H$).

#### 4. Dependent Events
Two events are dependent if the occurrence of one event alters the conditional probability of the second event.
* **Mathematical Condition:**
  $$P(A \cap B) = P(A) \times P(B|A) \quad (\text{if } A \text{ occurs first})$$
  $$P(A \cap B) = P(B) \times P(A|B) \quad (\text{if } B \text{ occurs first})$$
* *Example:* Drawing two cards or selecting students from a class of 5 boys and 5 girls **without replacement**.

---

## 2. CONDITIONAL PROBABILITY & BAYES' THEOREM

### 2.1 Conditional Probability
Conditional probability measure the probability of an event $A$ occurring, given that another event $B$ has already occurred. It is denoted as $P(A|B)$.

#### Formula:
$$P(A|B) = \frac{P(A \cap B)}{P(B)}, \quad \text{provided } P(B) > 0$$

* If $A$ and $B$ are **Independent**, then knowing $B$ provides no new information about $A$:
  $$P(A|B) = P(A) \quad \text{and} \quad P(B|A) = P(B)$$

### 2.2 Multiplication Rule of Probability
From the definition of conditional probability, the joint probability of both events occurring is:
$$P(A \cap B) = P(A) \cdot P(B|A) = P(B) \cdot P(A|B)$$

---

### 2.3 Law of Total Probability
Let $E_1, E_2, E_3, \dots, E_n$ be a set of $n$ events such that they are:
1. **Mutually Exclusive:** $E_i \cap E_j = \emptyset$ for all $i \neq j$.
2. **Exhaustive:** $\bigcup_{i=1}^{n} E_i = S$ (they completely cover the sample space).

For any arbitrary event $A$ in the same sample space $S$:
$$P(A) = \sum_{i=1}^{n} P(A \cap E_i) = \sum_{i=1}^{n} P(A|E_i)P(E_i)$$
$$P(A) = P(A|E_1)P(E_1) + P(A|E_2)P(E_2) + \dots + P(A|E_n)P(E_n)$$

---

### 2.4 Bayes' Theorem
Bayes' Theorem provides a mathematical method for **updating prior probabilities** in light of new observed evidence.

#### Formula:
$$P(E_k|A) = \frac{P(A|E_k) P(E_k)}{P(A)} = \frac{P(A|E_k) P(E_k)}{\sum_{i=1}^{n} P(A|E_i) P(E_i)}$$

#### Terminology Breakdown:
$$\text{Posterior Probability} = \frac{\text{Likelihood} \times \text{Prior Probability}}{\text{Evidence (Marginal Probability)}}$$

* **Prior Probability $P(E_k)$:** The initial assessment of the likelihood of event $E_k$ before observing evidence $A$.
* **Likelihood $P(A|E_k)$:** The probability of observing evidence $A$ assuming that the hypothesis $E_k$ is true.
* **Evidence / Marginal Probability $P(A)$:** The total probability of observing evidence $A$ across all possible hypotheses.
* **Posterior Probability $P(E_k|A)$:** The updated probability of hypothesis $E_k$ after evidence $A$ has been observed.

---

### 2.5 Solved Exam & Practice Questions (Bayes' Theorem)

#### Question 1 (Factory Suppliers):
> **Problem:** A company has three suppliers: A (30% of items, 1% defective), B (50% of items, 2% defective), and C (20% of items, 3% defective). A defective item is found. Find the probability it came from Supplier B.
> 
> **Solution:**
> 1. **Define Events:** Let $E_1, E_2, E_3$ be the events that an item is supplied by A, B, and C respectively. Let $D$ be the event that the chosen item is defective.
> 2. **Priors:** $P(E_1) = 0.30$, $P(E_2) = 0.50$, $P(E_3) = 0.20$.
> 3. **Likelihoods:** $P(D|E_1) = 0.01$, $P(D|E_2) = 0.02$, $P(D|E_3) = 0.03$.
> 4. **Total Probability $P(D)$:**
>    $$P(D) = (0.30 \times 0.01) + (0.50 \times 0.02) + (0.20 \times 0.03) = 0.003 + 0.010 + 0.006 = 0.019$$
> 5. **Apply Bayes' Theorem:**
>    $$P(E_2|D) = \frac{P(E_2)P(D|E_2)}{P(D)} = \frac{0.50 \times 0.02}{0.019} = \frac{0.010}{0.019} = \frac{10}{19} \approx 0.5263 \ (52.63\%)$$

---

#### Question 2 (Job Candidates & Profit Changes):
> **Problem:** Three persons A, B, and C apply for a job. Their selection chances are in ratio $1:2:4$. The probabilities that A, B, and C introduce profit-improving changes are $0.8, 0.5, 0.3$ respectively. If the change does NOT take place, find the probability it is due to the appointment of C.
> 
> **Solution:**
> 1. **Selection Priors:** Sum of ratio units $= 1+2+4 = 7$.
>    $$P(A) = 1/7, \quad P(B) = 2/7, \quad P(C) = 4/7$$
> 2. **Define Event $N$:** $N =$ Change does NOT take place.
>    * $P(N|A) = 1 - 0.8 = 0.2$
>    * $P(N|B) = 1 - 0.5 = 0.5$
>    * $P(N|C) = 1 - 0.3 = 0.7$
> 3. **Total Probability $P(N)$:**
>    $$P(N) = \left(\frac{1}{7} \times 0.2\right) + \left(\frac{2}{7} \times 0.5\right) + \left(\frac{4}{7} \times 0.7\right) = \frac{0.2 + 1.0 + 2.8}{7} = \frac{4.0}{7}$$
> 4. **Bayes' Theorem for $P(C|N)$:**
>    $$P(C|N) = \frac{P(C)P(N|C)}{P(N)} = \frac{\left(\frac{4}{7}\right) \times 0.7}{\frac{4.0}{7}} = \frac{2.8}{4.0} = 0.7 \ (70\%)$$

---

#### Question 3 (Commute Methods & Lateness):
> **Problem:** A person travels by car, train, or bus with equal probabilities. Lateness probabilities are: Car = 0.3, Bus = 0.4, Train = 0.1. Given that the person is late today:
> 1. Find the probability he traveled by bus.
> 2. Find the probabilities for car and train.
> 
> **Solution:**
> 1. **Priors:** $P(C) = P(B) = P(T) = 1/3$.
> 2. **Likelihoods:** $P(L|C) = 0.3$, $P(L|B) = 0.4$, $P(L|T) = 0.1$.
> 3. **Total Probability of Being Late $P(L)$:**
>    $$P(L) = \frac{1}{3}(0.3 + 0.4 + 0.1) = \frac{0.8}{3} = \frac{4}{15}$$
> 4. **Calculations:**
>    * **Bus:** $P(B|L) = \frac{\frac{1}{3} \times 0.4}{\frac{0.8}{3}} = \frac{0.4}{0.8} = 0.5$
>    * **Car:** $P(C|L) = \frac{\frac{1}{3} \times 0.3}{\frac{0.8}{3}} = \frac{0.3}{0.8} = 0.375$
>    * **Train:** $P(T|L) = \frac{\frac{1}{3} \times 0.1}{\frac{0.8}{3}} = \frac{0.1}{0.8} = 0.125$

---

## 3. RANDOM VARIABLES & PROBABILITY DISTRIBUTIONS

### 3.1 Concept of a Random Variable
A **random variable** $X$ is a real-valued function defined over a sample space $S$ ($X: S \to \mathbb{R}$). It associates a real number with each possible outcome of a random experiment.

---

### 3.2 Discrete vs. Continuous Random Variables

| Feature | Discrete Random Variable | Continuous Random Variable |
| :--- | :--- | :--- |
| **Value Domain** | Takes countable values (finite or countably infinite integers). | Takes any continuous real value within an interval $(a, b)$. |
| **Probability Mapping** | Probability Mass Function (PMF): $P(X = x)$ | Probability Density Function (PDF): $f(x)$ |
| **Probability at a Single Point** | $P(X = x) \ge 0$ (Can be non-zero). | **$P(X = x) = 0$ strictly for any single exact point.** |
| **Probability Calculation** | Summation: $P(X \in A) = \sum_{x \in A} P(X = x)$ | Integration over interval: $P(a \le X \le b) = \int_{a}^{b} f(x) \, dx$ |
| **Normalization Condition** | $\sum_{i} P(X = x_i) = 1$ | $\int_{-\infty}^{\infty} f(x) \, dx = 1$ |
| **Examples** | Number of heads in 3 coin tosses; count of defective bulbs. | Height/weight of students; elevator waiting time. |

---

### 3.3 Deep Dive: Why is $P(X = x) = 0$ for Continuous Variables?
For a continuous random variable:
$$\text{Probability} = \frac{\text{Length/Area of Target Interval}}{\text{Total Length/Area of Sample Domain}}$$
* A continuous interval contains an **infinite** number of exact points.
* A single point has **zero width/length** ($\Delta x = 0$).
* Thus:
  $$P(X = c) = \frac{0}{\infty} = 0$$
* *Key Takeaway:* A probability of 0 in continuous mathematics does **not** mean the event is impossible; it simply means the chance of hitting that exact single real value out of infinite continuous choices is infinitesimally small. Hence, for continuous variables:
  $$P(a \le X \le b) = P(a < X \le b) = P(a \le X < b) = P(a < X < b)$$

---

### 3.4 Cumulative Distribution Function (CDF)
The **Cumulative Distribution Function (CDF)**, $F_X(x)$, measures the total accumulated probability that $X$ takes a value less than or equal to $x$.
$$F_X(x) = P(X \le x), \quad \forall x \in \mathbb{R}$$

#### Properties of CDF $F(x)$:
1. $0 \le F(x) \le 1$ for all real $x$.
2. $F(x)$ is a **non-decreasing function**: If $x_1 < x_2 \implies F(x_1) \le F(x_2)$.
3. $\lim_{x \to -\infty} F(x) = 0$ and $\lim_{x \to \infty} F(x) = 1$.
4. **Relationship between PDF and CDF:**
   * $F(x) = \int_{-\infty}^{x} f(t) \, dt$
   * $f(x) = \frac{d}{dx} F(x)$ (where $F(x)$ is differentiable).

---

### 3.5 Solved Examples on Random Variables & Functions

#### Example 1 (Coins PMF & CDF):
> **Problem:** A coin is tossed twice. Let $X =$ Number of Heads. Find the PMF and CDF.
> 
> **Solution:**
> * Sample Space $S = \{TT, HT, TH, HH\}$. $X \in \{0, 1, 2\}$.
> 
> **1. PMF Table:**
> * $P(X=0) = P(\{TT\}) = 1/4$
> * $P(X=1) = P(\{HT, TH\}) = 2/4 = 1/2$
> * $P(X=2) = P(\{HH\}) = 1/4$
> 
> **2. Step-by-Step CDF $F(x) = P(X \le x)$ Construction:**
> * Case $x < 0$: $F(x) = 0$
> * Case $0 \le x < 1$: $F(x) = P(X=0) = 1/4$
> * Case $1 \le x < 2$: $F(x) = P(X=0) + P(X=1) = 1/4 + 1/2 = 3/4$
> * Case $x \ge 2$: $F(x) = P(X=0) + P(X=1) + P(X=2) = 1$
> 
> **Final Piecewise CDF:**
> $$F(x) = \begin{cases} 0, & x < 0 \\ \frac{1}{4}, & 0 \le x < 1 \\ \frac{3}{4}, & 1 \le x < 2 \\ 1, & x \ge 2 \end{cases}$$

---

#### Example 2 (PDF Constant Determination & Probability):
> **Problem:** A random variable $X$ has PDF $f(x) = \begin{cases} k(1 - x^2), & -1 \le x \le 1 \\ 0, & \text{otherwise} \end{cases}$
> 1. Determine $k$.
> 2. Verify $f(x)$ is valid.
> 3. Find $P(X > 0.5)$.
> 
> **Solution:**
> **1. Find $k$:**
> $$\int_{-1}^{1} k(1 - x^2) \, dx = 1 \implies 2k \left[ x - \frac{x^3}{3} \right]_0^1 = 1 \implies 2k \left(1 - \frac{1}{3}\right) = 1 \implies \frac{4}{3}k = 1 \implies k = \frac{3}{4}$$
> 
> **2. Verify Validity:**
> * $f(x) = \frac{3}{4}(1 - x^2) \ge 0$ for all $x \in [-1, 1]$.
> * Total integral $= 1$. Thus, valid.
> 
> **3. Calculate $P(X > 0.5)$:**
> $$P(X > 0.5) = \int_{0.5}^{1} \frac{3}{4}(1 - x^2) \, dx = \frac{3}{4} \left[ x - \frac{x^3}{3} \right]_{0.5}^{1}$$
> $$= \frac{3}{4} \left[ \left(1 - \frac{1}{3}\right) - \left(0.5 - \frac{0.125}{3}\right) \right] = \frac{3}{4} \left[ \frac{2}{3} - \frac{1.375}{3} \right] = \frac{3}{4} \left( \frac{0.625}{3} \right) = \frac{0.625}{4} = 0.15625$$

---

#### Example 3 (Checking Independence of Continuous Regions):
> **Problem:** Given PDF $f(x) = \begin{cases} \frac{x}{25}, & 0 \le x \le 5 \\ \frac{10-x}{25}, & 5 < x \le 10 \\ 0, & \text{otherwise} \end{cases}$
> Verify if $P = \{0 \le x \le 5\}$ and $Q = \{2.5 \le x \le 7.5\}$ are independent.
> 
> **Solution:**
> 1. **Compute $P(P)$:**
>    $$P(P) = \int_{0}^{5} \frac{x}{25} \, dx = \left[ \frac{x^2}{50} \right]_0^5 = \frac{25}{50} = 0.5$$
> 2. **Compute $P(Q)$:**
>    $$P(Q) = \int_{2.5}^{5} \frac{x}{25} \, dx + \int_{5}^{7.5} \frac{10-x}{25} \, dx$$
>    * $\int_{2.5}^{5} \frac{x}{25} \, dx = \frac{25 - 6.25}{50} = 0.375$
>    * $\int_{5}^{7.5} \frac{10-x}{25} \, dx = \left[ \frac{10x - x^2/2}{25} \right]_5^{7.5} = \frac{46.875 - 37.5}{25} = 0.375$
>    * $P(Q) = 0.375 + 0.375 = 0.75$
> 3. **Compute $P(P \cap Q)$:** $P \cap Q = \{2.5 \le x \le 5\}$
>    $$P(P \cap Q) = \int_{2.5}^{5} \frac{x}{25} \, dx = 0.375$$
> 4. **Check Condition:**
>    $$P(P) \times P(Q) = 0.5 \times 0.75 = 0.375 = P(P \cap Q)$$
>    Conclusion: Events $P$ and $Q$ are **INDEPENDENT**.

---

## 4. EXPECTED VALUE, VARIANCE & NORMAL DISTRIBUTION

### 4.1 Mean (Expected Value)
The **Expected Value** $E(X)$ or $\mu$ is the probability-weighted average of all possible values taken by a random variable.

* **Discrete Case:**
  $$E(X) = \mu = \sum_{i} x_i P(X = x_i)$$
* **Continuous Case:**
  $$E(X) = \mu = \int_{-\infty}^{\infty} x f(x) \, dx$$

#### Solved Example (Rolling a Die):
* $X \in \{1, 2, 3, 4, 5, 6\}$, each with $P(x) = 1/6$.
* $E(X) = (1 \times \frac{1}{6}) + (2 \times \frac{1}{6}) + \dots + (6 \times \frac{1}{6}) = \frac{21}{6} = 3.5$

---

### 4.2 Variance & Standard Deviation
Variance $\text{Var}(X)$ or $\sigma^2$ measures the dispersion/spread of the random variable around its mean.

#### Formula:
$$\text{Var}(X) = \sigma^2 = E[(X - \mu)^2] = E(X^2) - [E(X)]^2$$

* **Computation for $E(X^2)$:**
  * *Discrete:* $E(X^2) = \sum x_i^2 P(x_i)$
  * *Continuous:* $E(X^2) = \int_{-\infty}^{\infty} x^2 f(x) \, dx$
* **Standard Deviation ($\sigma$):**
  $$\sigma = \sqrt{\text{Var}(X)}$$

#### Comparison: Variance vs. Standard Deviation

| Property | Variance ($\sigma^2$) | Standard Deviation ($\sigma$) |
| :--- | :--- | :--- |
| **Definition** | Average squared deviation from the mean. | Average deviation from the mean in original units. |
| **Units** | Square of original units (e.g., $\text{cm}^2$). | Same units as original data (e.g., $\text{cm}$). |
| **Interpretability**| Harder to visually interpret on raw data. | Easily interpreted relative to dataset scale. |

---

### 4.3 Normal Probability Distribution (Gaussian Distribution)

#### 1. Definition & PDF Formula
The Normal distribution is a continuous probability distribution for a real-valued random variable. Its PDF is defined by mean $\mu$ and standard deviation $\sigma$:
$$f(x; \mu, \sigma) = \frac{1}{\sigma \sqrt{2\pi}} \exp\left( -\frac{(x - \mu)^2}{2\sigma^2} \right), \quad -\infty < x < \infty$$

#### 2. Key Properties of Normal Distribution:
1. **Symmetry:** Perfectly symmetric bell-shaped curve centered around the mean $\mu$.
2. **Central Tendency Equality:** Mean $=$ Median $=$ Mode $= \mu$.
3. **Total Area:** Total area under the curve $= 1$.
4. **Inflection Points:** The curve changes concavity at $x = \mu - \sigma$ and $x = \mu + \sigma$.
5. **Empirical Rule (68-95-99.7 Rule):**
   * $\approx 68.27\%$ of area lies within $\mu \pm 1\sigma$
   * $\approx 95.45\%$ of area lies within $\mu \pm 2\sigma$
   * $\approx 99.73\%$ of area lies within $\mu \pm 3\sigma$

```
                         Mean = Median = Mode
                                  |
                                  v
                                .---.
                              /   |   \
                             /    |    \
                            /     |     \
                           /      |      \
     ---------------------'-------+-------'---------------------
                         $\mu-1\sigma$   $\mu$   $\mu+1\sigma$
                         |<--- 68.27% --->|
```

#### 3. Standard Normal Distribution ($Z$-score Transformation)
A normal distribution with $\mu = 0$ and $\sigma = 1$ is called the **Standard Normal Distribution**.
Any normal variable $X \sim N(\mu, \sigma^2)$ can be standardized into $Z \sim N(0, 1)$ using:
$$Z = \frac{X - \mu}{\sigma}$$

---

*(This concludes **Part 1: Module 1 Notes**. Proceeding to **Part 2: Module 2 Notes**).*
