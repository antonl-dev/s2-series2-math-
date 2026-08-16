# Series Test-I: Model Solutions (Modules 1 & 2)

---

## PART A (Answer All Questions — $5 \times 2 = 10\text{ Marks}$)

---

### Q1. Which are the major phases in the waterfall model of software development? Which phase consumes the maximum effort for developing a typical software?
*(2 Marks — BL: 1, CO: 1)*

#### 1. Major Phases of the Classical Waterfall Model:
1. Feasibility Study
2. Requirement Analysis and Specification (SRS)
3. Design (High-Level and Low-Level Design)
4. Coding and Unit Testing
5. Integration and System Testing
6. Maintenance

```
  [Feasibility] -> [Requirements] -> [Design] -> [Coding] -> [Testing] -> [Maintenance]
```

#### 2. Maximum Effort Phase:
* Over the **entire software life cycle**, the **Maintenance phase** consumes the maximum effort (typically **60% to 70%** of total lifecycle cost).
* During the **active development lifecycle** (excluding post-delivery maintenance), the **Testing and Integration phase** consumes the maximum effort (**40% to 50%** of development effort).

---

### Q2. What do you understand by the term phase containment of errors? Why is phase containment of errors is considered to be important? How can phase containment of errors be achieved in a software development project?
*(2 Marks — BL: 2, CO: 1)*

#### 1. Definition:
**Phase containment of errors** refers to the practice of detecting, isolating, and correcting defects within the exact same development phase in which they are introduced, preventing them from leaking into subsequent phases.

#### 2. Importance:
* **Cost Escalation (Boehm's Cost-of-Change curve):** The cost of correcting an error increases exponentially as the project advances (e.g., an error costing $\$1$ to fix in requirements costs $\$10$ in design, $\$50$ in testing, and $>\$100$ in post-release maintenance).
* It minimizes rework, stabilizes design baselines, and ensures schedule integrity.

```
  Phase Introduced  -------> Phase Detected -------> Cost Multiplier
  Requirements               Requirements            1x
  Requirements               Design                  3x - 5x
  Requirements               Coding                  10x
  Requirements               System Testing          40x - 50x
  Requirements               Post-Release (Field)    100x+
```

#### 3. How to Achieve It:
* Formal Technical Reviews (FTR) and peer inspections at the end of each phase.
* Structured walkthroughs and requirement validation checklists.
* Automated static code analysis, design verification, and thorough unit testing.

---

### Q3. For the scenario described below, which life cycle model would you choose? Give the reason why you would choose this model?
> *"You are interacting with the MIS department of a very large oil company having multiple departments. They have a complex legacy system. Migrating the data from this legacy system is not an easy task and would take considerable time. The oil company is very particular about processes, acceptance criteria and legal contracts."*

*(2 Marks — BL: 3, CO: 1)*

#### 1. Recommended Model:
**The Classical Waterfall Model** (or **Iterative Waterfall Model / V-Model**).

#### 2. Justification:
1. **Contractual & Process Rigor:** The company requires strict adherence to processes, sign-offs, and legally binding acceptance criteria, which directly aligns with the document-driven, stage-gate Waterfall model.
2. **Stable, Well-Understood Requirements:** Data migration parameters, database schemas, and validation rules from the legacy system can be completely specified up front.
3. **Data Integrity & Traceability:** Waterfall ensures that comprehensive design reviews and migration mappings are fully verified before execution, avoiding corrupted enterprise data.

---

### Q4. Write five major responsibilities of a software project manager? As the manager of a software project to develop a product for business application, if you estimate the effort required for completion of the project to be 50 person-months, can you complete the project by employing 50 developers for a period of one month? Justify your answer.
*(2 Marks — BL: 2, CO: 5)*

#### 1. Five Major Responsibilities of a Software Project Manager (SPM):
1. **Project Estimation:** Estimating software size, effort, schedule, and cost.
2. **Project Scheduling & Tracking:** Formulating Work Breakdown Structures (WBS), Gantt charts, and monitoring progress milestones.
3. **Risk Management:** Identifying technical/operational risks, assessing exposure, and executing mitigation strategies.
4. **Resource & Team Management:** Allocating tasks, managing personnel, and resolving intra-team conflicts.
5. **Quality Assurance & Client Interfacing:** Ensuring compliance with quality standards (e.g., ISO, CMMI) and serving as the primary liaison for stakeholders.

#### 2. Effort Justification ($50\text{ person-months} \neq 50\text{ people} \times 1\text{ month}$):
* **No, it is impossible to complete the project in $1\text{ month}$ using $50\text{ developers}$.**
* **Justification (Brooks' Law & Task Dependencies):**
  1. **Task Dependencies (Sequential Constraints):** Software development is not partitioned into completely independent sub-tasks. System architecture must precede design; design must precede coding; coding must precede integration.
  2. **Communication Overhead:** The number of communication paths grows quadratically:
     $$\text{Paths} = \frac{n(n-1)}{2} = \frac{50 \times 49}{2} = 1225\text{ channels}$$
     Managing $1225$ communication lines creates coordination overhead that stalls progress.
  3. **Brooks' Law:** *"Adding manpower to a late software project makes it later."*

---

### Q5. What do you mean by project size? What are the popular metrics to measure project size? What are the issues in measuring the software size using LOC as metric?
*(2 Marks — BL: 2, CO: 5)*

#### 1. Software Project Size:
Software project size is a quantifiable measure of the total problem magnitude, volume of code, and functional complexity delivered by the software application.

#### 2. Popular Size Metrics:
* **Lines of Code (LOC / KLOC):** Counting physical or logical source code lines.
* **Function Point (FP) Analysis:** Measures functional size from a user perspective based on inputs, outputs, inquiries, files, and interfaces.
* **Object Points / Use Case Points (UCP):** Used in object-oriented and visual languages.

#### 3. Issues with LOC as a Metric:
1. **Programming Language Dependency:** Implementing a feature in Python requires far fewer lines of code than doing so in Assembly or C, skewing productivity calculations.
2. **Penalizes Concise, High-Quality Code:** A developer who writes efficient, modular, and refactored code receives a lower size score than one who writes verbose, redundant code.
3. **Cannot Be Used Early:** LOC cannot be directly counted during initial project scoping or requirements phases before implementation begins.
4. **Ambiguous Standards:** Discrepancies exist across organizations regarding whether to count comments, whitespace, data definitions, or header inclusions.

---
---

## PART B (Answer Any One Full Question From Each Module)

---

## MODULE I

---

### Q6. a) 
#### i. Differentiate between software engineering and System Engineering? Give examples on each.
*(3 Marks — BL: 2, CO: 1)*

| Parameter | System Engineering | Software Engineering |
| :--- | :--- | :--- |
| **Scope** | Broad discipline; encompasses hardware, software, human-ware, infrastructure, policies, and mechanical components. | Focused subset of system engineering; restricted to software component development. |
| **Primary Goal** | Optimizes the complete end-to-end system architecture, operational safety, and system integration. | Focuses on software architecture, design patterns, maintainability, algorithms, data structures, and code quality. |
| **Deliverables** | Hardware blueprints, mechanical designs, software systems, user workflows, and system specifications. | Executable binaries, source code, test suites, API specifications, and software manuals. |
| **Real-World Example** | **Designing an Autonomous Electric Vehicle (Tesla):** Integrating battery management, physical LiDAR/Radar hardware, vehicle chassis, electronic control units (ECUs), and driving policies. | **Developing the Auto-Pilot Path Planning Software:** Developing algorithmic image-processing software, obstacle-avoidance logic, and steering motor controllers. |

---

#### ii. Explain structured analysis and structured Design in Design phase for Software development.
*(4 Marks — BL: 2, CO: 1)*

#### 1. Structured Analysis (SA):
* **Concept:** A top-down, function-oriented modeling technique that converts unstructured user statements into formal, graphical requirement models. It focuses on the **flow and transformation of data** across the system.
* **Key Modeling Tools:**
  * **Data Flow Diagrams (DFD):** Depicts how data enters, is processed by logical functions, stored in datastores, and generated as outputs across different abstraction levels (Context-Level DFD/Level-0 to Level-2 DFD).
  * **Data Dictionary:** Central repository defining every data element, data structure, and composite type flowing through the DFDs.
  * **Process Specifications (PSpec):** Describes the input-output logic of primitive (lowest-level) DFD processes using structured English or decision tables.

```
       +------------------+                    +------------------+
       | External Entity  | === Data Flow ===> |     Process      |
       +------------------+                    +--------+---------+
                                                        |
                                                  Data Store Read/Write
                                                        v
                                               +------------------+
                                               |    Data Store    |
                                               +------------------+
```

#### 2. Structured Design (SD):
* **Concept:** Transforms the functional DFD data models from the analysis phase into a structured, modular software architecture represented as a **Structure Chart**.
* **Key Transformation Mechanisms:**
  * **Transform Analysis:** Applied when the DFD exhibits a clear linear flow: *Input $\rightarrow$ Process/Transform $\rightarrow$ Output*. Converts data transformations into a hierarchical Structure Chart.
  * **Transaction Analysis:** Applied when an input transaction routes execution down one of several distinct operational paths based on an input transaction code.
* **Structure Chart Representation:** Shows module hierarchies, module invocation, and interface data/control passings (High Cohesion, Low Coupling).

```
                            [ Master Controller ]
                               /             \
                   (Input Data)               (Output Data)
                             v                 v
                 [ Read Input Data ]      [ Format & Print ]
```

---

### Q6. b) Compare the following life cycle models based on their distinguishing factors, strength and weaknesses:
1. **Waterfall model**
2. **Iterative waterfall model**
3. **Spiral model**

*(8 Marks — BL: 2, CO: 1)*

| Comparison Parameter | 1. Classical Waterfall Model | 2. Iterative Waterfall Model | 3. Spiral Model |
| :--- | :--- | :--- | :--- |
| **Distinguishing Architectural Philosophy** | Purely sequential, linear, document-driven; each phase finishes before next begins; no feedback. | Sequential phase flow with **feedback paths** between adjacent stages to correct upstream errors. | **Risk-driven**, evolutionary iterative model organized into four repeating quadrants. |
| **Risk Handling** | No explicit risk management; high risk of late-stage failure. | Moderate; errors corrected via adjacent iteration, but no formal risk stage. | **Central focus;** explicit risk analysis, mitigation, and prototyping in Quadrant 2 of every cycle. |
| **Requirement Flexibility** | Completely rigid; requires frozen specifications at the beginning. | Low-to-moderate; accommodates corrections to existing requirements, but rejects new ones. | Highly flexible; accommodates new requirements in subsequent spiral loops. |
| **Strengths** | • Simple and easy to understand.<br>• Rigid phase gates ensure high documentation standard.<br>• Easy tracking of project milestones. | • Feedback channels allow error correction during later phases.<br>• More realistic than pure waterfall. | • Systematic, proactive risk mitigation.<br>• Working prototypes delivered early.<br>• Ideal for mission-critical, large-scale systems. |
| **Weaknesses** | • High risk of total project failure during late testing.<br>• Working software delivered only at the very end.<br>• Cannot handle evolving requirements. | • Difficult to incorporate completely new requirements.<br>• Feedback causes phase-transition overhead. | • Expensive and complex to manage.<br>• Requires specialized risk analysis expertise.<br>• Unsuitable for small, low-risk projects. |
| **Best Suited For** | Small, well-understood systems with strict contractual specifications. | Well-understood systems where minor requirements clarifications may arise during development. | High-budget, complex, safety-critical, enterprise applications with high technical uncertainty. |

---

### OR

---

### Q7. a) Enlist the importance of SRS document? Develop a SRS document for a software project: Online Course Management System (OCMS).
*(7 Marks — BL: 3, CO: 1)*

#### 1. Importance of the Software Requirements Specification (SRS) Document:
1. **Contractual Agreement:** Serves as a legally binding agreement between client and developers on what the system will deliver.
2. **Baseline for Design & Implementation:** Forms the direct input for High-Level Architectural Design and Low-Level Component Design.
3. **Baseline for Validation & Testing:** Test engineers create System and Acceptance Test Cases directly from SRS functional requirements.
4. **Reduces Rework:** Clarifies ambiguities, inconsistencies, and omissions before coding begins.
5. **Project Estimation Reference:** Provides the functional foundation for size ($FP/LOC$), effort, and cost estimation.

---

#### 2. SRS Document for Online Course Management System (OCMS)
*(Structured according to IEEE Std 830-1998)*

```
================================================================================
SOFTWARE REQUIREMENTS SPECIFICATION (SRS)
PROJECT: Online Course Management System (OCMS)
================================================================================
```

#### 1. Introduction
* **1.1 Purpose:** Defines the software requirements for the OCMS platform, providing course registration, automated grading, content delivery, and progress tracking for educational institutions.
* **1.2 Scope:** A web-based platform serving three primary user roles: Students, Instructors, and Administrators.

#### 2. Overall Description
* **2.1 Product Perspective:** An independent, cloud-hosted web application with a responsive web front-end and a secure back-end relational database.
* **2.2 User Classes & Characteristics:**
  * *Student:* Views available courses, registers, views video/reading material, submits assignments, takes quizzes.
  * *Instructor:* Uploads syllabus/lectures, creates assignments/quizzes, grades student submissions.
  * *Administrator:* Manages user accounts, enforces access controls, manages system configurations.

#### 3. Specific Functional Requirements
* **FR-1: User Authentication & Authorization:**
  * The system shall authenticate users via email and password with role-based access control (RBAC).
* **FR-2: Course Creation & Management (Instructor):**
  * The system shall allow instructors to create course modules, set enrollment capacities, and upload multimedia content ($\text{PDF}, \text{MP4}$).
* **FR-3: Enrollment & Registration (Student):**
  * The system shall allow eligible students to browse the catalog, enroll in open courses, and drop enrolled courses within designated deadlines.
* **FR-4: Assignment & Assessment Engine:**
  * The system shall allow students to upload assignment files ($<25\text{MB}$) and execute timed multiple-choice assessments with immediate grading.
* **FR-5: Performance & Grading Module:**
  * The system shall compute semester GPA/grades and generate downloadable PDF grade transcripts.

#### 4. Non-Functional Requirements (NFR)
* **NFR-1 (Performance):** The system shall handle $1,000$ concurrent active users with page response latency under $2\text{ seconds}$.
* **NFR-2 (Security):** All user credentials and data transfers shall be encrypted using TLS 1.3, and user passwords hashed via bcrypt.
* **NFR-3 (Availability):** The system shall maintain an uptime of $99.9\%$ during semester examination cycles.
* **NFR-4 (Usability):** The user interface shall comply with WCAG 2.1 Level AA accessibility standards.

---

### Q7. b) Briefly explain the agile software development model. Give an example of a project for which the agile model would be suitable and one project for which the agile model would not be appropriate also enlist 4 agile models used in industry.
*(8 Marks — BL: 2, CO: 1)*

#### 1. The Agile Software Development Model:
Agile is an iterative and incremental development philosophy centered on customer collaboration, rapid feedback loops, team autonomy, and adaptive delivery of working software in short timeboxes (**Sprints / Iterations**, typically 1–4 weeks).

```
   [Product Backlog] -> [Sprint Planning] -> [Sprint Backlog (1-4 Weeks)]
                                                        |
                                                        v
   [Shippable Product Increment] <--- [Sprint Review & Retro] <--- [Daily Scrum]
```

#### Core Values (Agile Manifesto):
1. **Individuals and interactions** over processes and tools.
2. **Working software** over comprehensive documentation.
3. **Customer collaboration** over contract negotiation.
4. **Responding to change** over following a plan.

---

#### 2. Project Suitability Examples:

* **Suitable Project Example: E-Commerce Mobile App for a Fashion Startup**
  * *Reasoning:* Market trends and consumer preferences shift rapidly. Releasing a Minimum Viable Product (MVP) in 3 weeks lets the business test features, receive customer feedback, and iterate product features (e.g., adding UPI payments, one-click checkout) without costly upfront architecture.

* **Unsuitable Project Example: Flight Control and Avionics Software for Passenger Aircraft (Boeing/Airbus)**
  * *Reasoning:* Safety-critical systems require complete formal specifications, exhaustive mathematical verification, rigid safety certifications (DO-178C standard), and strict regulatory sign-offs. Evolving requirements on the fly or deploying rapidly without exhaustive end-to-end documentation introduces catastrophic safety risks.

---

#### 3. Four Agile Models Used in Industry:
1. **Scrum:** Structured around fixed 2–4 week sprints, daily stand-up meetings, sprint retrospectives, and defined roles (Product Owner, Scrum Master, Cross-functional Dev Team).
2. **Extreme Programming (XP):** Engineering-centric framework emphasizing software engineering practices: Pair Programming, Test-Driven Development (TDD), Continuous Integration (CI), and simple design.
3. **Kanban:** Visual workflow management system emphasizing continuous delivery, transparent bottlenecks, and strictly enforced **Work-In-Progress (WIP)** limits.
4. **Feature-Driven Development (FDD):** Client-centric, short-iteration process focused on designing and building systems feature-by-feature through formal object-oriented domain walkthroughs.

---
---

## MODULE II

---

### Q8. a) What is the order in which the following are estimated - cost, effort, duration, size? Represent the precedence ordering among these activities using a task network diagram.
*(5 Marks — BL: 2, CO: 5)*

#### 1. Order of Estimation:
Software project parameters must be estimated in the following logical sequence:
1. **Size** (Measured in KLOC or Function Points)
2. **Effort** (Measured in Person-Months)
3. **Duration / Schedule** (Measured in Calendar Months)
4. **Cost** (Measured in Total Budget / Currency Units)

```
  Step 1: Size (KLOC / FP)
     |
     v
  Step 2: Effort = a * (Size)^b
     |
     v
  Step 3: Duration = c * (Effort)^d
     |
     v
  Step 4: Cost = (Effort * Labor Rate) + Hardware/Overhead Reserves
```

#### 2. Precedence Task Network Diagram:

```
  +--------------------+
  | 1. SIZE ESTIMATION |
  | (KLOC / FP Models) |
  +---------+----------+
            |
            v
  +--------------------+
  | 2. EFFORT          |
  |    ESTIMATION      |
  | (e.g., COCOMO E)   |
  +---------+----------+
            |
            +---------------------------------------+
            |                                       |
            v                                       v
  +--------------------+                 +--------------------+
  | 3. DURATION /      |                 | 4. HARDWARE, STAFF |
  |    SCHEDULE (Tdev) |                 |    & SUPPORT COSTS |
  +---------+----------+                 +----------+---------+
            |                                       |
            +-------------------+-------------------+
                                |
                                v
                     +--------------------+
                     | 5. TOTAL PROJECT   |
                     |    COST ESTIMATION |
                     +--------------------+
```

#### 3. Precedence Justification:
* **Size** is the fundamental independent variable derived from user functional requirements.
* **Effort** depends directly on the estimated size: $\text{Effort} = f(\text{Size})$.
* **Duration** depends non-linearly on effort: $\text{Duration} = f(\text{Effort})$.
* **Cost** aggregates total effort multiplied by average developer wages plus fixed hardware/software environment costs: $\text{Cost} = f(\text{Effort}, \text{Duration}, \text{Overhead})$.

---

### Q8. b) Briefly explain the following software Cost estimation techniques:
1. **Empirical**
2. **Heuristic**
3. **Analytical**

*(10 Marks — BL: 2, CO: 5)*

```
                          +-----------------------------------+
                          |  Software Cost Estimation Models  |
                          +-----------------+-----------------+
                                            |
         +----------------------------------+----------------------------------+
         |                                  |                                  |
         v                                  v                                  v
  +--------------+                   +--------------+                   +--------------+
  |  EMPIRICAL   |                   |  HEURISTIC   |                   |  ANALYTICAL  |
  +--------------+                   +--------------+                   +--------------+
  • Expert Judgement                 • Single-Variable Models           • Putnam's SLIM Model
  • Delphi / Wideband Delphi         • Multi-Variable (COCOMO)          • Norden-Rayleigh Curves
  • Historical Data Matching         • Parametric Equations             • Theoretical Derivations
```

---

#### 1. Empirical Estimation Techniques
* **Concept:** Empirical techniques rely on past project experience, historical metrics, and expert human intuition rather than formal mathematical formulas.
* **Key Approaches:**
  * **Expert Judgement:** An experienced estimator or team assesses the system specification and estimates effort based on memory of similar previous systems.
    * *Drawback:* Subjective, biased, and susceptible to individual over/under-estimation.
  * **Wideband Delphi Technique:**
    1. A coordinator distributes the project specification to a panel of anonymous experts.
    2. Experts independently and anonymously produce estimates with rationale.
    3. The coordinator collates the results into a summary chart and redistributes it.
    4. Experts discuss variations anonymously and produce a revised estimate.
    5. The process repeats until estimates converge to a group consensus.
    * *Advantage:* Minimizes individual bias and prevents junior members from being swayed by senior personnel.

---

#### 2. Heuristic (Parametric) Estimation Techniques
* **Concept:** Assumes that the relationship among primary project variables (Size, Effort, Time) can be modeled using mathematical, empirical equations derived from statistical regression over large databases of completed historical projects.
* **General Mathematical Form:**
  $$\text{Effort} = a \cdot (\text{Size})^b$$
* **Classification:**
  * **Single-Variable Models:** Base effort solely on a single input variable (typically Size in KLOC). Example: Doty Model ($\text{Effort} = 5.288 \times (\text{KLOC})^{1.047}$).
  * **Multi-Variable Models (e.g., Boehm's Intermediate COCOMO):** Combines size with subjective assessments of multiple project attributes (**Cost Drivers** / Effort Multipliers like product complexity, analyst capability, execution time constraints).
    $$\text{Effort} = a \times (\text{KLOC})^b \times \prod_{i=1}^{15} \text{Cost Driver}_i$$

---

#### 3. Analytical Estimation Techniques
* **Concept:** Analytical techniques derive cost and effort based on mathematical and scientific laws governing software processes, modeling software development after physical resource-consumption systems over time.
* **Putnam’s Resource Allocation Model (SLIM):**
  * Proposed by Larry Putnam; models developer staffing profiles over time using the continuous **Norden-Rayleigh Manpower Distribution Curve**.

```
    Staffing Level (Effort/Time)
         ^
         |             /\
         |            /  \     <--- Rayleigh Manpower Distribution Curve
         |           /    \
         |          /      \
         |         /        \
         +--------+----------+--------> Time (t)
               Design      Coding    Testing/Release
```

* **Software Equation (Putnam):**
  $$S = C_k \cdot K^{1/3} \cdot t_d^{4/3}$$
  * Where:
    * $S =$ Size in source lines of code (LOC)
    * $C_k =$ State-of-technology environment factor
    * $K =$ Total life cycle effort (in Person-Years)
    * $t_d =$ Total development time (in Years)
* **Significance:** Demonstrates the non-linear trade-off between schedule compression and total effort: drastically shortening delivery duration ($t_d$) demands an exponentially higher total effort ($K$).

---

### OR

---

### Q9. a) Explain about basic COCOMO model?
*(6 Marks — BL: 2, CO: 5)*

#### 1. Overview:
The **COCOMO (Constructive Cost Model)**, developed by **Barry Boehm** in 1981, is a heuristic/empirical model that estimates software development effort, schedule duration, and team sizing based on estimated project size in Thousands of Lines of Code (**KLOC**).

#### 2. Three Development Modes in Basic COCOMO:
1. **Organic Mode:** Small, experienced teams working in familiar, stable operating environments with well-understood, non-rigid requirements (e.g., payroll systems, basic business utilities).
2. **Semidetached Mode:** Medium-sized teams with mixed experience levels facing moderately constrained environments with partially flexible requirements (e.g., database management systems, compilers).
3. **Embedded Mode:** Highly complex systems developed under stringent, unforgiving hardware, software, and operational regulations (e.g., flight control systems, real-time medical instruments).

---

#### 3. Mathematical Formulation of Basic COCOMO:

$$\text{Effort } (E) = a_b \times (\text{KLOC})^{b_b}\quad \text{[in Person-Months (PM)]}$$

$$\text{Development Time } (T_{dev}) = c_b \times (\text{Effort})^{d_b}\quad \text{[in Months]}$$

$$\text{Average Staff Size } (S) = \frac{\text{Effort}}{T_{dev}}\quad \text{[in Persons]}$$

$$\text{Productivity } (P) = \frac{\text{KLOC}}{\text{Effort}}\quad \text{[in KLOC/PM]}$$

#### Model Coefficients Table:

| Development Mode | $a_b$ | $b_b$ | $c_b$ | $d_b$ |
| :--- | :---: | :---: | :---: | :---: |
| **Organic** | $2.4$ | $1.05$ | $2.5$ | $0.38$ |
| **Semidetached** | $3.0$ | $1.12$ | $2.5$ | $0.35$ |
| **Embedded** | $3.6$ | $1.20$ | $2.5$ | $0.32$ |

* The scaling exponent $b_b > 1$ models the **diseconomy of scale**: as project size grows, communication and integration overhead cause effort to scale super-linearly.

---

### Q9. b) Suppose that a project was estimated to be 400 KLOC. Calculate the effort and development time for each of the three modes i.e., organic, semidetached and embedded using basic COCOMO model.
*(9 Marks — BL: 3, CO: 5)*

#### Given:
$$\text{Project Size} = 400\text{ KLOC}$$

---

### 1. Organic Mode Calculation

* **Coefficients:** $a_b = 2.4,\ b_b = 1.05,\ c_b = 2.5,\ d_b = 0.38$

#### A. Effort ($E$):
$$E = a_b \times (\text{KLOC})^{b_b}$$
$$E = 2.4 \times (400)^{1.05}$$

$$\log_{10}(400) \approx 2.60205999$$
$$1.05 \times 2.60205999 = 2.73216299$$
$$(400)^{1.05} = 10^{2.73216299} \approx 541.67$$

$$E = 2.4 \times 541.67 = \mathbf{1300.01\text{ Person-Months}}$$

#### B. Development Time ($T_{dev}$):
$$T_{dev} = c_b \times (E)^{d_b}$$
$$T_{dev} = 2.5 \times (1300.01)^{0.38}$$

$$\log_{10}(1300.01) \approx 3.1139467$$
$$0.38 \times 3.1139467 = 1.18330$$
$$(1300.01)^{0.38} = 10^{1.18330} \approx 15.251$$

$$T_{dev} = 2.5 \times 15.251 = \mathbf{38.13\text{ Months}}$$

---

### 2. Semidetached Mode Calculation

* **Coefficients:** $a_b = 3.0,\ b_b = 1.12,\ c_b = 2.5,\ d_b = 0.35$

#### A. Effort ($E$):
$$E = a_b \times (\text{KLOC})^{b_b}$$
$$E = 3.0 \times (400)^{1.12}$$

$$\log_{10}(400) \approx 2.60205999$$
$$1.12 \times 2.60205999 = 2.914307$$
$$(400)^{1.12} = 10^{2.914307} \approx 820.93$$

$$E = 3.0 \times 820.93 = \mathbf{2462.79\text{ Person-Months}}$$

#### B. Development Time ($T_{dev}$):
$$T_{dev} = c_b \times (E)^{d_b}$$
$$T_{dev} = 2.5 \times (2462.79)^{0.35}$$

$$\log_{10}(2462.79) \approx 3.391425$$
$$0.35 \times 3.391425 = 1.1870$$
$$(2462.79)^{0.35} = 10^{1.1870} \approx 15.3815$$

$$T_{dev} = 2.5 \times 15.3815 = \mathbf{38.45\text{ Months}}$$

---

### 3. Embedded Mode Calculation

* **Coefficients:** $a_b = 3.6,\ b_b = 1.20,\ c_b = 2.5,\ d_b = 0.32$

#### A. Effort ($E$):
$$E = a_b \times (\text{KLOC})^{b_b}$$
$$E = 3.6 \times (400)^{1.20}$$

$$\log_{10}(400) \approx 2.60205999$$
$$1.20 \times 2.60205999 = 3.122472$$
$$(400)^{1.20} = 10^{3.122472} \approx 1325.80$$

$$E = 3.6 \times 1325.80 = \mathbf{4772.88\text{ Person-Months}}$$

#### B. Development Time ($T_{dev}$):
$$T_{dev} = c_b \times (E)^{d_b}$$
$$T_{dev} = 2.5 \times (4772.88)^{0.32}$$

$$\log_{10}(4772.88) \approx 3.67878$$
$$0.32 \times 3.67878 = 1.17721$$
$$(4772.88)^{0.32} = 10^{1.17721} \approx 15.0388$$

$$T_{dev} = 2.5 \times 15.0388 = \mathbf{37.60\text{ Months}}$$

---

### Summary of Numerical Results Table:

| Mode | Calculated Effort ($E$) | Calculated Duration ($T_{dev}$) | Average Staffing ($S = \frac{E}{T_{dev}}$) |
| :--- | :---: | :---: | :---: |
| **Organic** | $\mathbf{1300.01\text{ PM}}$ | $\mathbf{38.13\text{ Months}}$ | $\approx 34.1\text{ Developers}$ |
| **Semidetached** | $\mathbf{2462.79\text{ PM}}$ | $\mathbf{38.45\text{ Months}}$ | $\approx 64.1\text{ Developers}$ |
| **Embedded** | $\mathbf{4772.88\text{ PM}}$ | $\mathbf{37.60\text{ Months}}$ | $\approx 126.9\text{ Developers}$ |
