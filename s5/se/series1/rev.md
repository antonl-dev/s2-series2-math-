Here is a targeted **Exam Preparation Guide** featuring high-probability test questions, scenario-based problems, and quick formula cheat-sheets covering **Modules 1 & 2**.

---

# QUICK-REVIEW SUMMARY & EXAM QUESTION BANK

---

## 1. Quick Formula & Concept Cheat Sheet

```
+---------------------------------------------------------------------------------------------------+
| 1. COCOMO Formulas:                                                                               |
|    • Effort (E)               = a_b * (KLOC)^(b_b)   [Person-Months (PM)]                         |
|    • Development Time (T_dev) = c_b * (Effort)^(d_b) [Months]                                     |
|    • Average Staff Size (S)   = Effort / T_dev       [Persons]                                    |
|    • Productivity (P)         = KLOC / Effort        [KLOC/PM]                                    |
+---------------------------------------------------------------------------------------------------+
| 2. COCOMO Mode Constants:                                                                         |
|    • Organic      : a_b = 2.4,  b_b = 1.05,  c_b = 2.5,  d_b = 0.38                               |
|    • Semidetached : a_b = 3.0,  b_b = 1.12,  c_b = 2.5,  d_b = 0.35                               |
|    • Embedded     : a_b = 3.6,  b_b = 1.20,  c_b = 2.5,  d_b = 0.32                               |
+---------------------------------------------------------------------------------------------------+
| 3. Communication Channels:                                                                        |
|    • Paths = [n * (n - 1)] / 2   (where n = number of developers)                                 |
+---------------------------------------------------------------------------------------------------+
| 4. Cohesion (Worst -> Best):                                                                      |
|    Coincidental < Logical < Temporal < Procedural < Communicational < Sequential < Functional    |
+---------------------------------------------------------------------------------------------------+
| 5. Coupling (Worst -> Best):                                                                      |
|    Content (Tight) < Common < Control < Stamp < Data (Loose)                                      |
+---------------------------------------------------------------------------------------------------+
```

---

## 2. High-Yield 2-Mark & Short-Answer Questions

### Q1: What is the primary difference between Verification and Validation?
* **Verification:** Checks whether the intermediate software artifacts conform to the specifications established in the preceding phase (*"Are we building the product right?"*). Uses static techniques like reviews, inspections, and walkthroughs.
* **Validation:** Checks whether the final software product meets customer requirements and intended use (*"Are we building the right product?"*). Uses dynamic execution of test cases.

---

### Q2: Why is the Waterfall model unsuitable for projects with volatile requirements?
The Waterfall model strictly enforces a **stage-gate sequential structure**, requiring formal freeze and sign-off on the Requirements Specification (SRS) before design and implementation start. Late requirement changes necessitate massive rework, invalidate signed-off documents, and result in severe cost and schedule overruns.

---

### Q3: What is "Stepwise Refinement"? Who proposed it?
Proposed by **Niklaus Wirth**, Stepwise Refinement is a top-down design strategy where a high-level function is incrementally broken down through successive levels of procedural and data abstractions until it is fully translated into executable source code constructs.

---

### Q4: State the primary role of a Software Project Manager (SPM). List 5 key responsibilities.
The primary role of an SPM is to lead the project team to deliver software that meets requirements within schedule and budget constraints.
* **5 Key Responsibilities:**
  1. Project estimation (size, effort, duration, cost).
  2. Project scheduling and milestones tracking.
  3. Risk identification, mitigation, and monitoring.
  4. Staff selection, allocation, and team management.
  5. Interfacing with stakeholders and monitoring software quality.

---

## 3. High-Yield Scenario-Based Long Questions

---

### Question Scenario A: Life Cycle Model Selection
> **Scenario:** *"You are interacting with the MIS department of a large oil company with multiple departments. They have a complex legacy system. Migrating data from this legacy system is difficult and time-consuming. The company is very particular about rigid processes, strict acceptance criteria, and legal contracts. Which SDLC model should you choose? Justify."*

#### Model Choice: **The Classical Waterfall Model (or Iterative Waterfall / V-Model)**

```
   +------------------------------------------------------------------------+
   |                        JUSTIFICATION FACTORS                           |
   +------------------------------------------------------------------------+
   | 1. High Regulatory & Contractual Rigor:                                |
   |    Waterfall provides exhaustive phase documentation & formal sign-offs.|
   +------------------------------------------------------------------------+
   | 2. Clear, Stable Scope:                                                |
   |    Legacy migration requirements are completely known and unchanging.  |
   +------------------------------------------------------------------------+
   | 3. High Integration & Data Risks:                                      |
   |    Detailed upfront analysis prevents corrupting mission-critical data.|
   +------------------------------------------------------------------------+
```

* **Why not Agile?** Agile values flexible scope over comprehensive contracts and documentation. In this context, lack of fixed contractual specifications and sign-off gates would conflict with the client's corporate compliance standards.

---

### Question Scenario B: Risk-Driven Spiral Model
> **Scenario:** *"Explain how Risk Management is integrated into the Spiral Model. Give examples of risks handled in different phases."*

#### Key Points:
* Unlike other models where risk assessment is ad-hoc, Boehm's Spiral Model includes **Quadrant 2 (Risk Analysis & Evaluation)** as a mandatory step in every single development loop.
* **Phase-wise Risk Management Examples:**
  1. **Loop 1 (Concept/Requirements):** *Risk:* Ambiguous UI requirements $\rightarrow$ *Mitigation:* Rapid UI prototyping for customer feedback.
  2. **Loop 2 (Architectural Design):** *Risk:* Chosen database cannot handle required transaction throughput $\rightarrow$ *Mitigation:* Benchmarking and running load simulations on architectural prototypes.
  3. **Loop 3 (Implementation/Testing):** *Risk:* Integration delays due to sub-module incompatibilities $\rightarrow$ *Mitigation:* Incremental continuous integration and automated test suites.

```
       Spiral Loop 1                   Spiral Loop 2                   Spiral Loop 3
  [ Ambiguous UI Specs ]          [ Throughput Bottlenecks ]      [ Sub-module Incompatibilities ]
            |                               |                               |
            v                               v                               v
    (Build UI Mockup)             (Benchmark DB Prototype)        (Automated Integration Tests)
```

---

### Question Scenario C: Precedence Ordering of Project Estimates
> **Scenario:** *"What is the order in which size, effort, duration, and cost are estimated? Represent the precedence using a task network diagram and explain why this order is critical."*

#### 1. Precedence Task Diagram:

```
                      +-------------------+
                      |   1. SIZE (KLOC)  |
                      +---------+---------+
                                |
                                v
                      +-------------------+
                      | 2. EFFORT (PM)    |
                      +---------+---------+
                                |
                                v
                      +-------------------+
                      | 3. DURATION (Tdev)|
                      +---------+---------+
                                |
                                v
                      +-------------------+
                      |   4. TOTAL COST   |
                      +-------------------+
```

#### 2. Explanation:
1. **Size ($\text{KLOC} / \text{FP}$):** First, estimate the volume of work required based on the system's functional requirements.
2. **Effort ($\text{Person-Months}$):** Size directly determines the required human effort ($E = a \cdot \text{Size}^b$).
3. **Duration ($\text{Nominal Months}$):** Duration is a sub-linear function of effort ($T_{dev} = c \cdot E^d$). You cannot calculate the project timeline without knowing total effort.
4. **Cost ($\text{Currency}$):** Calculated as:
   $$\text{Total Cost} = (\text{Effort} \times \text{Average Labor Cost/Month}) + \text{Hardware/Software Overhead} + \text{Contingency Reserve}$$

---

## 4. Final Review Checklist Before the Exam

- [x] Can you state the **4 Agile Values** and describe **Scrum vs. XP**?
- [x] Can you draw and explain the **V-Model**, **Spiral Model Quadrants**, and **Waterfall Model**?
- [x] Can you solve **Basic COCOMO** numerical calculations for Organic, Semidetached, and Embedded modes?
- [x] Can you rank the types of **Cohesion** (Functional $\rightarrow$ Coincidental) and **Coupling** (Data $\rightarrow$ Content)?
- [x] Can you explain **Brooks' Law** using communication paths: $\frac{n(n-1)}{2}$?
- [x] Can you explain why **increasing cohesion does not automatically decrease coupling**?
