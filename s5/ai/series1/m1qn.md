Here is **Part 1** of your Comprehensive Question Paper Bank Solutions, focusing strictly on **Module 1 (Probability Distributions, Bayes' Theorem, Random Variables)** from all provided exam papers.

The solutions are fully expanded and detailed strictly proportional to their allotted marks.

---

# MODULE 1: SOLUTIONS (PART 1)

---

## SECTION A: 2-MARK QUESTIONS (MODULE 1)

### Q1. Define a random variable representing the number of heads when a coin is tossed three times. Is it discrete or continuous? Justify.
* **Random Variable Definition:** Let $X$ denote the number of heads obtained when a fair coin is tossed three times.
* **Sample Space ($\Omega$):** 
  $$\Omega = \{HHH, HHT, HTH, HTT, THH, THT, TTH, TTT\}$$
* **Possible Values:** $X \in \{0, 1, 2, 3\}$.
* **Type & Justification:** It is a **discrete random variable** because the range of values $X$ can take is countable and finite (specifically discrete non-negative integers).

---

### Q2. A dataset shows that its mean, median, and mode are all equal. What type of distribution is this likely to be, and what does this imply about its shape?
* **Type of Distribution:** It is likely to be a **Symmetric / Normal Distribution** (Gaussian Distribution).
* **Implications for Shape:**
  1. The probability density curve is perfectly **symmetric** around the central value (mean $\mu$).
  2. The distribution has a characteristic **bell-shaped curve**.
  3. The skewness of the distribution is equal to zero ($\text{Skewness} = 0$).

---

### Q3. Differentiate between prior and posterior probabilities.
| Feature | Prior Probability $P(A)$ | Posterior Probability $P(A|B)$ |
| :--- | :--- | :--- |
| **Definition** | Unconditional probability of an event before collecting new evidence/data. | Conditional probability of an event after observing new evidence/data. |
| **Formula Context** | Base probability available from background knowledge. | Updated probability computed using Bayes' Theorem: $P(A|B) = \frac{P(B|A)P(A)}{P(B)}$ |

---

### Q4. Write any four applications of probability distribution.
1. **Risk Management & Insurance:** Modeling claims frequency and pricing insurance premiums using Poisson and Normal distributions.
2. **Quality Control in Manufacturing:** Assessing product defect rates per batch using Binomial distributions.
3. **Machine Learning & AI:** Naïve Bayes classification, Gaussian Mixture Models, and Bayesian inference algorithms.
4. **Queueing Theory & Telecom:** Modeling arrival times of network requests/traffic using Exponential distributions.

---

## SECTION B: 3 to 5-MARK QUESTIONS (MODULE 1)

### Q5. Write and explain discrete and continuous random variables with examples. [5 Marks]

#### 1. Discrete Random Variable
* **Definition:** A random variable $X$ is said to be discrete if its set of possible outcomes is finite or countably infinite. The probabilities are assigned to specific discrete points using a **Probability Mass Function (PMF)** $P(X = x)$.
* **Properties:** 
  1. $0 \le P(X = x_i) \le 1$ for all $i$
  2. $\sum_i P(X = x_i) = 1$
* **Example:** Tossing two fair coins and letting $X$ be the number of heads observed. $X$ can take values from the set $\{0, 1, 2\}$.

#### 2. Continuous Random Variable
* **Definition:** A random variable $X$ is continuous if it can take any real value within a continuous interval or union of intervals $(a, b)$. Probabilities over specific exact values are zero ($P(X = x) = 0$), so probabilities are calculated over intervals using a **Probability Density Function (PDF)** $f(x)$.
* **Properties:**
  1. $f(x) \ge 0$ for all $x$
  2. $\int_{-\infty}^{\infty} f(x) \, dx = 1$
  3. $P(a \le X \le b) = \int_{a}^{b} f(x) \, dx$
* **Example:** The exact height of students in a university class, or the time interval between arrival of messages on a server, measured continuously $X \in (0, \infty)$.

---

### Q6. A company has three suppliers: A (30% of items, 1% defective), B (50% of items, 2% defective), and C (20% of items, 3% defective). A defective item is found. Find the probability it came from Supplier B. [5 Marks]

#### Solution:

**Step 1: Define Events**
* Let $E_1, E_2, E_3$ be the events that an item is supplied by Supplier A, B, and C respectively.
* Let $D$ be the event that the chosen item is defective.

**Step 2: List Given Probabilities**
* **Prior Probabilities:**
  $$P(E_1) = 0.30, \quad P(E_2) = 0.50, \quad P(E_3) = 0.20$$
* **Likelihoods (Conditional Probabilities of Defect):**
  $$P(D|E_1) = 0.01, \quad P(D|E_2) = 0.02, \quad P(D|E_3) = 0.03$$

**Step 3: Total Probability of Defect $P(D)$**
$$P(D) = P(E_1)P(D|E_1) + P(E_2)P(D|E_2) + P(E_3)P(D|E_3)$$
$$P(D) = (0.30 \times 0.01) + (0.50 \times 0.02) + (0.20 \times 0.03)$$
$$P(D) = 0.003 + 0.010 + 0.006 = 0.019$$

**Step 4: Apply Bayes' Theorem**
We need to find $P(E_2|D)$, the probability that the item came from B given it is defective:
$$P(E_2|D) = \frac{P(E_2) \cdot P(D|E_2)}{P(D)}$$
$$P(E_2|D) = \frac{0.50 \times 0.02}{0.019} = \frac{0.010}{0.019} = \frac{10}{19} \approx 0.5263\ (52.63\%)$$

---

### Q7. Three persons A, B, and C have applied for a job in a private company. The chance of their selections is in the ratio $1 : 2 : 4$. The probabilities that A, B, and C can introduce changes to improve the profits of the company are $0.8, 0.5,$ and $0.3$, respectively. If the change does not take place, find the probability that it is due to the appointment of C. [5 Marks]

#### Solution:

**Step 1: Selection Probabilities**
Ratio of selection $= 1 : 2 : 4$. Sum of ratio units $= 1 + 2 + 4 = 7$.
* $P(A) = \frac{1}{7}$
* $P(B) = \frac{2}{7}$
* $P(C) = \frac{4}{7}$

**Step 2: Define Conditional Probabilities**
Let $N$ be the event that **change does NOT take place**.
* $P(\text{Change}|A) = 0.8 \implies P(N|A) = 1 - 0.8 = 0.2$
* $P(\text{Change}|B) = 0.5 \implies P(N|B) = 1 - 0.5 = 0.5$
* $P(\text{Change}|C) = 0.3 \implies P(N|C) = 1 - 0.3 = 0.7$

**Step 3: Total Probability of No Change $P(N)$**
$$P(N) = P(A)P(N|A) + P(B)P(N|B) + P(C)P(N|C)$$
$$P(N) = \left(\frac{1}{7} \times 0.2\right) + \left(\frac{2}{7} \times 0.5\right) + \left(\frac{4}{7} \times 0.7\right)$$
$$P(N) = \frac{0.2 + 1.0 + 2.8}{7} = \frac{4.0}{7}$$

**Step 4: Apply Bayes' Theorem**
Find $P(C|N)$:
$$P(C|N) = \frac{P(C) \cdot P(N|C)}{P(N)} = \frac{\left(\frac{4}{7}\right) \times 0.7}{\frac{4.0}{7}} = \frac{2.8}{4.0} = 0.7\ (70\%)$$

---

### Q8. A random variable $X$ has a function:
$$f(x) = \begin{cases} k(1 - x^2), & -1 \le x \le 1 \\ 0, & \text{otherwise} \end{cases}$$
1. Determine the value of $k$.
2. Verify $f(x)$ is a valid Probability Density Function (PDF).
3. Find $P(X > 0.5)$. [5 Marks]

#### Solution:

**Part 1: Find value of $k$**
For any valid PDF, the total area under the curve must equal 1:
$$\int_{-\infty}^{\infty} f(x) \, dx = 1 \implies \int_{-1}^{1} k(1 - x^2) \, dx = 1$$
Since $1 - x^2$ is an even function:
$$2k \int_{0}^{1} (1 - x^2) \, dx = 1$$
$$2k \left[ x - \frac{x^3}{3} \right]_0^1 = 1 \implies 2k \left( 1 - \frac{1}{3} \right) = 1$$
$$2k \left(\frac{2}{3}\right) = 1 \implies \frac{4}{3}k = 1 \implies k = \frac{3}{4}$$

---

**Part 2: Verify $f(x)$ is a valid PDF**
A function $f(x)$ is a valid PDF if:
1. $f(x) \ge 0$ for all $x$:
   For $x \in [-1, 1]$, $x^2 \le 1 \implies (1 - x^2) \ge 0$. Since $k = 3/4 > 0$, $f(x) \ge 0$ holds.
2. $\int_{-\infty}^{\infty} f(x) \, dx = 1$:
   $$\int_{-1}^{1} \frac{3}{4}(1 - x^2) \, dx = \frac{3}{4} \left[ x - \frac{x^3}{3} \right]_{-1}^{1} = \frac{3}{4} \left[\left(1 - \frac{1}{3}\right) - \left(-1 + \frac{1}{3}\right)\right] = \frac{3}{4} \times \frac{4}{3} = 1$$
Hence, $f(x)$ is a valid PDF.

---

**Part 3: Find $P(X > 0.5)$**
$$P(X > 0.5) = \int_{0.5}^{1} \frac{3}{4}(1 - x^2) \, dx$$
$$= \frac{3}{4} \left[ x - \frac{x^3}{3} \right]_{0.5}^{1} = \frac{3}{4} \left[ \left(1 - \frac{1}{3}\right) - \left(0.5 - \frac{(0.5)^3}{3}\right) \right]$$
$$= \frac{3}{4} \left[ \frac{2}{3} - \left(0.5 - \frac{0.125}{3}\right) \right] = \frac{3}{4} \left[ \frac{2}{3} - \frac{1.375}{3} \right]$$
$$= \frac{3}{4} \left[ \frac{0.625}{3} \right] = \frac{0.625}{4} = 0.15625$$

---

## SECTION C: 8-MARK QUESTIONS (MODULE 1)

### Q9. The probability density function (pdf) of a continuous random variable $X$ is given by:
$$f(x) = \begin{cases} \frac{x}{25}, & 0 \le x \le 5 \\ \frac{10 - x}{25}, & 5 < x \le 10 \\ 0, & \text{otherwise} \end{cases}$$
**Verify whether events $P$ and $Q$ are independent if $P = \{x: 0 \le x \le 5\}$ and $Q = \{x: 2.5 \le x \le 7.5\}$.** [8 Marks]

#### Solution:

#### Step 1: Definition of Independence
Two events $P$ and $Q$ are independent if and only if:
$$P(P \cap Q) = P(P) \cdot P(Q)$$

---

#### Step 2: Compute $P(P)$
$$P(P) = P(0 \le X \le 5) = \int_{0}^{5} \frac{x}{25} \, dx = \left[ \frac{x^2}{50} \right]_0^5 = \frac{25}{50} = 0.5$$

---

#### Step 3: Compute $P(Q)$
$$P(Q) = P(2.5 \le X \le 7.5) = \int_{2.5}^{5} \frac{x}{25} \, dx + \int_{5}^{7.5} \frac{10 - x}{25} \, dx$$

* First Integral:
  $$\int_{2.5}^{5} \frac{x}{25} \, dx = \left[ \frac{x^2}{50} \right]_{2.5}^{5} = \frac{25 - 6.25}{50} = \frac{18.75}{50} = 0.375$$

* Second Integral:
  $$\int_{5}^{7.5} \frac{10 - x}{25} \, dx = \left[ \frac{10x - \frac{x^2}{2}}{25} \right]_{5}^{7.5}$$
  $$= \frac{\left(10(7.5) - \frac{56.25}{2}\right) - \left(10(5) - \frac{25}{2}\right)}{25} = \frac{(75 - 28.125) - (50 - 12.5)}{25} = \frac{46.875 - 37.5}{25} = \frac{9.375}{25} = 0.375$$

* Sum:
  $$P(Q) = 0.375 + 0.375 = 0.75$$

---

#### Step 4: Compute $P(P \cap Q)$
The intersection region $P \cap Q$ is the set overlap:
$$P \cap Q = \{x : 0 \le x \le 5\} \cap \{x : 2.5 \le x \le 7.5\} = \{x : 2.5 \le x \le 5\}$$

$$P(P \cap Q) = \int_{2.5}^{5} \frac{x}{25} \, dx = \left[ \frac{x^2}{50} \right]_{2.5}^{5} = \frac{25 - 6.25}{50} = \frac{18.75}{50} = 0.375$$

---

#### Step 5: Test Independence Condition
* $P(P) \cdot P(Q) = 0.5 \times 0.75 = 0.375$
* $P(P \cap Q) = 0.375$

Since $P(P \cap Q) = P(P) \cdot P(Q)$, the events $P$ and $Q$ are **INDEPENDENT**.

---

### Q10. Find probability distribution and distribution function for the number of heads when 3 coins are tossed. [4 Marks]

#### Solution:

Let $X$ = Number of heads obtained when 3 fair coins are tossed. Possible values $X = \{0, 1, 2, 3\}$. Total outcomes $2^3 = 8$.

#### 1. Probability Distribution Table (PMF)
* $P(X=0) = P(\{TTT\}) = \frac{1}{8}$
* $P(X=1) = P(\{HTT, THT, TTH\}) = \frac{3}{8}$
* $P(X=2) = P(\{HHT, HTH, THH\}) = \frac{3}{8}$
* $P(X=3) = P(\{HHH\}) = \frac{1}{8}$

| $x$ | $0$ | $1$ | $2$ | $3$ |
| :---: | :---: | :---: | :---: | :---: |
| **$P(X=x)$** | $\frac{1}{8}$ | $\frac{3}{8}$ | $\frac{3}{8}$ | $\frac{1}{8}$ |

#### 2. Cumulative Distribution Function (CDF), $F(x) = P(X \le x)$
$$F(x) = \begin{cases} 0, & x < 0 \\ \frac{1}{8}, & 0 \le x < 1 \\ \frac{4}{8} = \frac{1}{2}, & 1 \le x < 2 \\ \frac{7}{8}, & 2 \le x < 3 \\ 1, & x \ge 3 \end{cases}$$

---

### Q11. A person is moving from house to office using three ways by car, train, and bus. Probability of all three are equal. Probability of getting late if he is traveling by car is 0.3, by bus is 0.4, by train is 0.1. Now it is found that he is late today.
1. What is the probability that he is traveling by using the bus? [5 Marks]
2. Also find the probability of traveling by car and train given he is late. [3 Marks]

#### Solution:

**Step 1: Event Definitions & Prior Probabilities**
* Let $C, T, B$ be events of traveling by Car, Train, and Bus.
* $P(C) = P(T) = P(B) = \frac{1}{3}$
* Let $L$ be the event of being late.
* Likelihoods: $P(L|C) = 0.3$, $P(L|B) = 0.4$, $P(L|T) = 0.1$

**Step 2: Total Probability of Being Late $P(L)$**
$$P(L) = P(C)P(L|C) + P(B)P(L|B) + P(T)P(L|T)$$
$$P(L) = \left(\frac{1}{3} \times 0.3\right) + \left(\frac{1}{3} \times 0.4\right) + \left(\frac{1}{3} \times 0.1\right) = \frac{0.3 + 0.4 + 0.1}{3} = \frac{0.8}{3} = \frac{4}{15}$$

---

#### Part (a): Probability of using Bus given Late, $P(B|L)$ [5 Marks]
$$P(B|L) = \frac{P(B) \cdot P(L|B)}{P(L)} = \frac{\frac{1}{3} \times 0.4}{\frac{0.8}{3}} = \frac{0.4}{0.8} = 0.5\ (50\%)$$

---

#### Part (b): Probability of using Car given Late $P(C|L)$ and Train given Late $P(T|L)$ [3 Marks]

* **Probability of using Car:**
  $$P(C|L) = \frac{P(C) \cdot P(L|C)}{P(L)} = \frac{\frac{1}{3} \times 0.3}{\frac{0.8}{3}} = \frac{0.3}{0.8} = 0.375\ (37.5\%)$$

* **Probability of using Train:**
  $$P(T|L) = \frac{P(T) \cdot P(L|T)}{P(L)} = \frac{\frac{1}{3} \times 0.1}{\frac{0.8}{3}} = \frac{0.1}{0.8} = 0.125\ (12.5\%)$$

---

*(This completes all Module 1 questions. Ready for Part 2: Module 2 - AI Agents, Environments & Vacuum Cleaner Problem).*
