# Unit 4: Swarm Intelligence Techniques

**Course:** PEC-CSE-405G | **Author:** [Deepak Modi](https://deepakmodi.tech)

**Syllabus:**      
Particle Swarm Optimization, Ant Colony Optimization, Artificial Bees and Firefly Algorithm etc., Hybridization and Comparisons of Swarm Techniques, Application of Swarm Techniques in Different Domains and Real World Problems.

---

## 🎯 PYQ Analysis for Unit 4

### High Priority Topics ⭐⭐⭐ (15 marks questions)
1. **Ant Colony Optimization** (2022-Feb, 2022-Jul, 2024-May, 2024-Dec)
2. **Applications of Swarm Techniques** (2022-Feb, 2022-Jul, 2022-Dec, 2023, 2024-May, 2024-Dec)

### Medium Priority Topics ⭐⭐ (7-8 marks)
3. **Particle Swarm Optimization** (2022-Dec, 2024-Dec)
4. **Artificial Bees Algorithm** (2022-Jul, 2023)
5. **Firefly Algorithm** (2022-Dec, 2023)
6. **Hybridization and Comparisons** (2022-Feb, 2024-Dec)
7. **Swarm Optimization** (2023)

### Short Answer Topics ⭐ (2.5-3 marks)
8. **Characteristics of Artificial Bees** (2022-Feb)

---

## **1. Particle Swarm Optimization (PSO)**

> PYQ: Particle swarm optimization. (2022-Dec, 8 marks)      
> PYQ: Ant colony optimization and particle swarm optimization. (2024-Dec, 8 marks)

### 1.1 Introduction to PSO

**Particle Swarm Optimization (PSO)** is a population-based optimization algorithm inspired by the social behavior of bird flocking or fish schooling. Developed by Kennedy and Eberhart in 1995.

> **"PSO is inspired by the social behavior of birds flocking in search of food."**

### 1.2 Basic Concept

**Key Idea:** Each particle (potential solution) moves through the search space, adjusting its position based on:
1. Its own best position found so far (personal best - pbest)
2. The best position found by the entire swarm (global best - gbest)

```
Bird Flocking Analogy:
│
├── Each bird = Particle (solution)
├── Food location = Optimal solution
├── Bird's experience = Personal best (pbest)
└── Flock's knowledge = Global best (gbest)
```

### 1.3 PSO Algorithm

**Components:**

| Component | Description |
|-----------|-------------|
| **Particle** | Candidate solution with position and velocity |
| **Position (x)** | Current location in search space |
| **Velocity (v)** | Direction and speed of movement |
| **pbest** | Best position found by particle |
| **gbest** | Best position found by entire swarm |

**Algorithm Steps:**

```
1. Initialize
   ├── Random positions for all particles
   ├── Random velocities
   └── Set pbest = current position, gbest = best of all pbest

2. For each iteration:
   │
   ├── For each particle:
   │   │
   │   ├── Update velocity:
   │   │   v = w×v + c₁×r₁×(pbest - x) + c₂×r₂×(gbest - x)
   │   │
   │   ├── Update position:
   │   │   x = x + v
   │   │
   │   ├── Evaluate fitness
   │   │
   │   ├── Update pbest if current position is better
   │   │
   │   └── Update gbest if any pbest is better
   │
   └── Check termination condition

3. Return gbest as optimal solution
```

**Velocity Update Formula:**

```
v(t+1) = w × v(t) + c₁ × r₁ × (pbest - x(t)) + c₂ × r₂ × (gbest - x(t))

Where:
w  = Inertia weight (controls exploration vs exploitation)
c₁ = Cognitive coefficient (personal learning factor)
c₂ = Social coefficient (social learning factor)
r₁, r₂ = Random numbers between [0,1]
```

**Three Components:**
1. **Inertia:** Keeps particle moving in same direction
2. **Cognitive:** Pulls particle toward its best position
3. **Social:** Pulls particle toward swarm's best position

### 1.4 PSO Parameters

| Parameter | Typical Value | Purpose |
|-----------|---------------|---------|
| **Swarm Size** | 20-50 | Number of particles |
| **Inertia (w)** | 0.4-0.9 | Balance exploration/exploitation |
| **c₁ (Cognitive)** | 2.0 | Personal learning rate |
| **c₂ (Social)** | 2.0 | Social learning rate |
| **Max Velocity** | Problem-dependent | Prevent particles from moving too fast |

### 1.5 PSO Example

**Problem:** Minimize f(x,y) = x² + y²

```
Iteration 1:
Particle 1: position (3, 4), fitness = 25
Particle 2: position (2, 1), fitness = 5
Particle 3: position (5, 2), fitness = 29

gbest = Particle 2 (fitness = 5)

Iteration 2:
All particles move toward gbest (2, 1)
Particle 1: moves to (2.5, 3)
Particle 2: moves to (1.8, 0.9)
Particle 3: moves to (4, 1.5)

gbest updated to Particle 2 (1.8, 0.9)

Continue until convergence...
```

### 1.6 Advantages and Disadvantages

**Advantages:**

| Advantage | Description |
|-----------|-------------|
| Simple | Few parameters to tune |
| Fast convergence | Quickly finds good solutions |
| No gradient needed | Works with non-differentiable functions |
| Flexible | Applicable to various problems |

**Disadvantages:**

| Disadvantage | Description |
|--------------|-------------|
| Premature convergence | May get stuck in local optima |
| Parameter sensitivity | Performance depends on parameter tuning |
| No guarantee | No guarantee of global optimum |

### 1.7 Applications of PSO

- **Function Optimization**: Finding minima/maxima
- **Neural Network Training**: Optimizing weights
- **Feature Selection**: Selecting best features
- **Scheduling**: Job scheduling, task allocation
- **Power Systems**: Load dispatch, voltage control

---

## **2. Ant Colony Optimization (ACO)**

> PYQ: What is the ant colony optimization technique? Write various types of algorithms in ant colony optimization. Differentiate ant colony optimization vs particle swarm optimization. (2022-Feb, 15 marks)      
> PYQ: Ant colony optimization. (2022-Jul, 8 marks)      
> PYQ: Discuss the ant colony optimization technique in detail. (2024-May, 15 marks)

### 2.1 Introduction to ACO

**Ant Colony Optimization (ACO)** is inspired by the foraging behavior of ants. Ants find shortest paths between their nest and food sources using pheromone trails. Developed by Marco Dorigo in 1992.

> **"ACO mimics the way real ants find shortest paths using pheromone communication."**

### 2.2 Biological Inspiration

**How Real Ants Work:**

```
Ant Foraging Behavior:
│
├── 1. Ants leave nest randomly searching for food
│
├── 2. When ant finds food, it returns to nest
│      leaving pheromone trail
│
├── 3. Other ants follow stronger pheromone trails
│
├── 4. Shorter paths get more pheromone
│      (ants complete round trip faster)
│
├── 5. Pheromone evaporates over time
│
└── 6. Eventually, shortest path has strongest trail
```

**Key Mechanisms:**
1. **Positive Feedback**: Good solutions attract more ants
2. **Pheromone Evaporation**: Prevents premature convergence
3. **Stigmergy**: Indirect communication through environment

### 2.3 ACO Algorithm for TSP

**Problem:** Traveling Salesman Problem - find shortest tour visiting all cities once.

**Algorithm:**

```
1. Initialize
   ├── Place m ants on random cities
   └── Initialize pheromone trails τ₀ on all edges

2. For each iteration:
   │
   ├── For each ant k:
   │   │
   │   ├── Build tour by selecting next city based on:
   │   │   │
   │   │   ├── Pheromone level (τ)
   │   │   └── Heuristic information (η = 1/distance)
   │   │
   │   └── Calculate tour length
   │
   ├── Update pheromones:
   │   │
   │   ├── Evaporation: τ = (1-ρ) × τ
   │   │
   │   └── Deposit: τ = τ + Δτ (on edges of good tours)
   │
   └── Record best tour found

3. Return best tour
```

**Probability of Moving from City i to j:**

```
         [τᵢⱼ]^α × [ηᵢⱼ]^β
P(i,j) = ─────────────────────
         Σ [τᵢₖ]^α × [ηᵢₖ]^β
         k∈allowed

Where:
τᵢⱼ = Pheromone on edge (i,j)
ηᵢⱼ = Heuristic value (1/distance)
α = Pheromone importance
β = Heuristic importance
```

### 2.4 Types of ACO Algorithms

#### 1. Ant System (AS)
- Original ACO algorithm
- All ants deposit pheromone
- Simple but slow convergence

#### 2. Ant Colony System (ACS)
- Only best ant deposits pheromone
- Local pheromone update during tour construction
- Faster convergence

#### 3. Max-Min Ant System (MMAS)
- Pheromone values bounded [τₘᵢₙ, τₘₐₓ]
- Only best ant updates pheromone
- Better exploration

#### 4. Rank-Based Ant System
- Ants ranked by tour quality
- Pheromone deposit proportional to rank
- Balanced exploration/exploitation

### 2.5 ACO Example

**Problem:** 4-city TSP

```
Cities: A, B, C, D
Distances:
A-B: 10, A-C: 15, A-D: 20
B-C: 35, B-D: 25
C-D: 30

Initial pheromone: τ = 0.1 on all edges

Iteration 1:
Ant 1 tour: A→B→D→C→A, length = 90
Ant 2 tour: A→C→B→D→A, length = 95
Ant 3 tour: A→D→C→B→A, length = 90

Best tour: A→B→D→C→A (length = 90)
Update pheromone on edges: A-B, B-D, D-C, C-A

Iteration 2:
More ants likely to follow A→B→D→C→A due to higher pheromone
...
```

### 2.6 ACO vs PSO

> PYQ: Differentiate ant colony optimization vs particle swarm optimization. (2022-Feb, 15 marks)

| Aspect | Ant Colony Optimization | Particle Swarm Optimization |
|--------|------------------------|----------------------------|
| **Inspiration** | Ant foraging behavior | Bird flocking, fish schooling |
| **Communication** | Indirect (pheromone) | Direct (position sharing) |
| **Solution Construction** | Incremental (step by step) | Complete solution updated |
| **Memory** | Pheromone trails | Personal and global best |
| **Best For** | Discrete problems (TSP, routing) | Continuous optimization |
| **Convergence** | Slower but thorough | Faster convergence |
| **Parameters** | α, β, ρ, m (ants) | w, c₁, c₂, swarm size |

### 2.7 Applications of ACO

| Domain | Application |
|--------|-------------|
| **Routing** | Vehicle routing, network routing |
| **Scheduling** | Job shop scheduling, project scheduling |
| **Assignment** | Quadratic assignment problem |
| **Graph Problems** | TSP, graph coloring |
| **Telecommunications** | Network optimization |

---

## **3. Artificial Bee Colony (ABC) Algorithm**

> PYQ: Write any two characteristics of artificial bees. (2022-Feb, 1.875 marks)      
> PYQ: Artificial bees algorithm. (2022-Jul, 7 marks)      
> PYQ: Artificial bees and firefly algorithms. (2023, 7.5 marks)

### 3.1 Introduction

**Artificial Bee Colony (ABC)** algorithm is inspired by the intelligent foraging behavior of honey bee swarms. Proposed by Karaboga in 2005.

### 3.2 Bee Roles

```
Honey Bee Colony:
│
├── Employed Bees (50%)
│   └── Exploit known food sources
│
├── Onlooker Bees (50%)
│   └── Select food sources based on employed bees' info
│
└── Scout Bees
    └── Randomly search for new food sources
```

### 3.3 Characteristics of Artificial Bees

> PYQ: Write any two characteristics of artificial bees. (2022-Feb, 1.875 marks)

| Characteristic | Description |
|----------------|-------------|
| **Self-Organization** | No central control, collective decision |
| **Division of Labor** | Different roles (employed, onlooker, scout) |
| **Information Sharing** | Waggle dance to communicate food source quality |
| **Adaptive Foraging** | Switch between exploration and exploitation |
| **Memory** | Remember food source locations and quality |

### 3.4 ABC Algorithm

**Steps:**

```
1. Initialize
   └── Random food sources (solutions)

2. Employed Bee Phase:
   ├── Each employed bee exploits a food source
   ├── Produce new solution by modifying current one
   └── Greedy selection (keep better solution)

3. Onlooker Bee Phase:
   ├── Calculate probability for each food source
   ├── Onlookers select sources probabilistically
   └── Exploit selected sources

4. Scout Bee Phase:
   ├── If food source not improved for "limit" trials
   └── Replace with random new source (scout bee)

5. Memorize best solution found

6. Repeat until termination
```

**Solution Update:**

```
vᵢⱼ = xᵢⱼ + φᵢⱼ(xᵢⱼ - xₖⱼ)

Where:
vᵢⱼ = New solution
xᵢⱼ = Current solution
xₖⱼ = Randomly selected neighbor solution
φᵢⱼ = Random number [-1, 1]
```

### 3.5 Advantages and Applications

**Advantages:**
- Simple, few parameters
- Good balance between exploration and exploitation
- Robust and flexible

**Applications:**
- Function optimization
- Neural network training
- Image processing
- Clustering

---

## **4. Firefly Algorithm (FA)**

> PYQ: Firefly algorithm. (2022-Dec, 7 marks)      
> PYQ: Artificial bees and firefly algorithms. (2023, 7.5 marks)

### 4.1 Introduction

**Firefly Algorithm (FA)** is inspired by the flashing behavior of fireflies. Developed by Xin-She Yang in 2008.

### 4.2 Firefly Behavior

**Key Principles:**

1. **Attractiveness**: Fireflies are attracted to brighter fireflies
2. **Light Intensity**: Decreases with distance
3. **Movement**: Firefly moves toward brighter ones
4. **Brightness**: Related to objective function value

```
Firefly Flashing:
│
├── Brighter firefly = Better solution
├── Distance affects attraction
└── Fireflies move toward brighter ones
```

### 4.3 Algorithm Components

**Attractiveness Formula:**

```
β(r) = β₀ × e^(-γr²)

Where:
β₀ = Attractiveness at r=0
γ = Light absorption coefficient
r = Distance between fireflies
```

**Movement Equation:**

```
xᵢ = xᵢ + β₀×e^(-γr²ᵢⱼ)×(xⱼ - xᵢ) + α×(rand - 0.5)

Where:
xᵢ = Position of firefly i
xⱼ = Position of brighter firefly j
α = Randomization parameter
```

### 4.4 FA Algorithm Steps

```
1. Initialize firefly population with random positions

2. Define light intensity I (based on objective function)

3. For each iteration:
   │
   ├── For each firefly i:
   │   │
   │   ├── For each firefly j:
   │   │   │
   │   │   ├── If I(j) > I(i):
   │   │   │   └── Move i toward j
   │   │   │
   │   │   └── Update attractiveness
   │   │
   │   └── Evaluate new solutions
   │
   └── Rank fireflies and find best

4. Return best solution
```

### 4.5 Applications

- Multimodal optimization
- Feature selection
- Image processing
- Scheduling problems
- Engineering design

---

## **5. Hybridization and Comparisons**

> PYQ: Why hybridization? What is the role of hybridization in swarm? How is hybridization calculated using swarm techniques? (2022-Feb, 7 marks)      
> PYQ: Hybridization and comparisons of swarm techniques. (2024-Dec, 7 marks)

### 5.1 Why Hybridization?

**Motivation:**

| Reason | Explanation |
|--------|-------------|
| **Overcome Limitations** | Single algorithm may have weaknesses |
| **Combine Strengths** | Leverage advantages of multiple algorithms |
| **Better Performance** | Achieve better solution quality |
| **Faster Convergence** | Reduce computation time |
| **Robustness** | More reliable across different problems |

### 5.2 Types of Hybridization

#### 1. Component-Level Hybridization
- Replace components of one algorithm with another
- Example: PSO with ACO pheromone update

#### 2. Sequential Hybridization
- Run algorithms one after another
- Example: GA for global search → Local search for refinement

#### 3. Parallel Hybridization
- Run multiple algorithms simultaneously
- Example: Multiple swarms with different parameters

#### 4. Embedded Hybridization
- One algorithm embedded within another
- Example: Local search within GA

### 5.3 Hybrid Swarm Techniques

**Examples:**

| Hybrid | Components | Benefit |
|--------|-----------|---------|
| **PSO-GA** | PSO + Genetic Algorithm | Fast convergence + diversity |
| **ACO-PSO** | ACO + PSO | Discrete + continuous optimization |
| **ABC-DE** | ABC + Differential Evolution | Exploration + exploitation |
| **FA-SA** | Firefly + Simulated Annealing | Global + local search |

### 5.4 Comparison of Swarm Techniques

| Algorithm | Inspiration | Best For | Convergence | Complexity |
|-----------|------------|----------|-------------|------------|
| **PSO** | Bird flocking | Continuous optimization | Fast | Low |
| **ACO** | Ant foraging | Discrete/combinatorial | Medium | Medium |
| **ABC** | Bee foraging | Function optimization | Medium | Low |
| **FA** | Firefly flashing | Multimodal problems | Fast | Low |
| **GA** | Natural selection | General optimization | Slow | High |

### 5.5 Performance Comparison

**Strengths and Weaknesses:**

```
PSO:
✓ Fast convergence
✓ Simple implementation
✗ Premature convergence
✗ Poor for discrete problems

ACO:
✓ Excellent for TSP/routing
✓ Positive feedback mechanism
✗ Slow convergence
✗ Many parameters

ABC:
✓ Good exploration
✓ Few parameters
✗ Slow convergence
✗ Limited local search

FA:
✓ Handles multimodal functions
✓ Automatic subdivision
✗ Parameter sensitive
✗ Computationally expensive
```

---

## **6. Applications of Swarm Techniques**

> PYQ: Discuss various applications of swarm techniques in different domains and real-world problems with suitable examples. (2022-Feb, 8 marks)      
> PYQ: Discuss various applications of swarm techniques in different real-world problems. (2022-Jul, 2022-Dec, 15 marks)      
> PYQ: Discuss the applications of swarm techniques in different domains and real-world problems. (2023, 15 marks)      
> PYQ: Explain the applications of swarm techniques in different domains and real-world problems. (2024-May, 15 marks)      
> PYQ: Discuss various applications of swarm intelligence techniques in various domains and provide examples of how they effectively solve real-world optimization problems. (2024-Dec, 15 marks)

### 6.1 Engineering Applications

#### 1. Structural Design
**Problem:** Optimize building/bridge design for strength and cost

**Swarm Technique:** PSO, GA
- **Variables**: Material dimensions, reinforcement
- **Objective**: Minimize cost while meeting safety constraints
- **Example**: Bridge truss optimization

#### 2. Power Systems
**Problem:** Economic load dispatch - allocate power generation to minimize cost

**Swarm Technique:** PSO, ACO
- **Variables**: Power output of each generator
- **Constraints**: Power demand, generator limits
- **Benefit**: Reduced fuel costs, improved efficiency

#### 3. Manufacturing
**Problem:** Job shop scheduling - assign jobs to machines

**Swarm Technique:** ACO, PSO
- **Objective**: Minimize makespan (total completion time)
- **Constraints**: Machine availability, job precedence
- **Example**: Factory production scheduling

### 6.2 Telecommunications

#### 1. Network Routing
**Problem:** Find optimal paths for data packets

**Swarm Technique:** ACO
- **Inspiration**: Ants finding shortest paths
- **Benefit**: Adaptive routing, load balancing
- **Example**: AntNet routing protocol

#### 2. Wireless Sensor Networks
**Problem:** Optimize sensor placement and data aggregation

**Swarm Technique:** PSO, ABC
- **Objectives**: Coverage, energy efficiency
- **Example**: Environmental monitoring networks

### 6.3 Transportation and Logistics

#### 1. Vehicle Routing Problem (VRP)
**Problem:** Plan delivery routes for fleet of vehicles

**Swarm Technique:** ACO
- **Constraints**: Vehicle capacity, time windows
- **Objective**: Minimize total distance/cost
- **Example**: Amazon delivery optimization

#### 2. Traffic Signal Control
**Problem:** Optimize traffic light timings

**Swarm Technique:** PSO, ABC
- **Objective**: Minimize waiting time, congestion
- **Real-time**: Adapt to traffic conditions

#### 3. Airline Scheduling
**Problem:** Crew scheduling, flight scheduling

**Swarm Technique:** GA, ACO
- **Constraints**: Regulations, crew availability
- **Benefit**: Cost reduction, better utilization

### 6.4 Healthcare

#### 1. Medical Diagnosis
**Problem:** Feature selection for disease prediction

**Swarm Technique:** PSO, ABC
- **Data**: Patient symptoms, test results
- **Objective**: Select most relevant features
- **Example**: Cancer diagnosis using PSO

#### 2. Drug Design
**Problem:** Molecular docking - find drug-protein binding

**Swarm Technique:** PSO, FA
- **Objective**: Maximize binding affinity
- **Benefit**: Faster drug discovery

#### 3. Medical Image Analysis
**Problem:** Image segmentation, tumor detection

**Swarm Technique:** ABC, PSO
- **Application**: MRI, CT scan analysis
- **Benefit**: Improved accuracy

### 6.5 Finance and Economics

#### 1. Portfolio Optimization
**Problem:** Select investment portfolio

**Swarm Technique:** PSO, GA
- **Objective**: Maximize return, minimize risk
- **Constraints**: Budget, diversification
- **Example**: Stock portfolio selection

#### 2. Credit Scoring
**Problem:** Predict loan default risk

**Swarm Technique:** PSO for feature selection
- **Data**: Customer financial history
- **Benefit**: Better risk assessment

### 6.6 Machine Learning

#### 1. Neural Network Training
**Problem:** Optimize network weights

**Swarm Technique:** PSO, ABC
- **Benefit**: Avoid local minima
- **Application**: Deep learning optimization

#### 2. Feature Selection
**Problem:** Select relevant features from dataset

**Swarm Technique:** PSO, GA
- **Objective**: Maximize accuracy, minimize features
- **Example**: Text classification, image recognition

#### 3. Clustering
**Problem:** Group similar data points

**Swarm Technique:** ABC, PSO
- **Application**: Customer segmentation, document clustering
- **Benefit**: Better cluster quality

### 6.7 Robotics

#### 1. Path Planning
**Problem:** Find collision-free path for robot

**Swarm Technique:** PSO, ACO
- **Environment**: Static or dynamic obstacles
- **Objective**: Shortest, safest path
- **Example**: Autonomous vehicle navigation

#### 2. Swarm Robotics
**Problem:** Coordinate multiple robots

**Swarm Technique:** PSO, ACO
- **Tasks**: Formation control, area coverage
- **Application**: Search and rescue, exploration

### 6.8 Energy Systems

#### 1. Smart Grid Optimization
**Problem:** Manage distributed energy resources

**Swarm Technique:** PSO, ABC
- **Objectives**: Cost, reliability, emissions
- **Components**: Solar, wind, storage

#### 2. Wind Farm Layout
**Problem:** Optimal placement of wind turbines

**Swarm Technique:** PSO, GA
- **Objective**: Maximize power output
- **Constraints**: Wake effects, land availability

### 6.9 Agriculture

#### 1. Crop Planning
**Problem:** Decide what crops to plant and where

**Swarm Technique:** PSO, GA
- **Factors**: Soil, water, market demand
- **Objective**: Maximize profit

#### 2. Precision Agriculture
**Problem:** Optimize irrigation, fertilization

**Swarm Technique:** PSO, ABC
- **Benefit**: Resource efficiency, higher yield

### 6.10 Summary of Applications

| Domain | Problem | Swarm Technique | Benefit |
|--------|---------|----------------|---------|
| **Engineering** | Structural design | PSO, GA | Cost reduction |
| **Telecom** | Network routing | ACO | Adaptive routing |
| **Transportation** | Vehicle routing | ACO | Reduced distance |
| **Healthcare** | Medical diagnosis | PSO, ABC | Better accuracy |
| **Finance** | Portfolio optimization | PSO, GA | Risk management |
| **ML** | Neural network training | PSO, ABC | Better convergence |
| **Robotics** | Path planning | PSO, ACO | Collision-free paths |
| **Energy** | Smart grid | PSO, ABC | Cost, reliability |

---

## **Summary Table: Unit 4 Key Concepts**

| Topic | Key Points |
|-------|------------|
| **PSO** | Bird flocking, velocity update, pbest/gbest, continuous optimization |
| **ACO** | Ant foraging, pheromone trails, TSP/routing, discrete problems |
| **ABC** | Bee colony, employed/onlooker/scout bees, function optimization |
| **Firefly** | Firefly flashing, attractiveness, multimodal optimization |
| **Hybridization** | Combine algorithms, overcome limitations, better performance |
| **Comparisons** | PSO (fast), ACO (discrete), ABC (balanced), FA (multimodal) |
| **Applications** | Engineering, telecom, healthcare, finance, ML, robotics |

---

## **Expected Questions for Exam**

### 15 Marks Questions
1. Ant Colony Optimization (algorithm, types, applications)
2. Applications of Swarm Techniques (multiple domains with examples)
3. PSO and ACO with comparison

### 7-8 Marks Questions
1. Particle Swarm Optimization
2. Artificial Bees Algorithm
3. Firefly Algorithm
4. Hybridization and Comparisons of Swarm Techniques

### 2.5-3 Marks Questions
1. Characteristics of Artificial Bees
2. Any swarm technique (brief)

---

*These notes were compiled by [Deepak Modi](https://deepakmodi.tech)*      
*Last updated: December 2024*

