# 📘 Discrete Optimization Problem with Quadratic Objective Function

## 📌 Overview

This project presents the design, implementation, and experimental evaluation of algorithms for solving a **discrete optimization problem with a quadratic objective function**.

The work was completed as part of the course *Operations Research* at **Igor Sikorsky Kyiv Polytechnic Institute**.

The goal is to determine optimal values of decision variables under constraints such that a quadratic objective function reaches its **maximum or minimum**.

---

## 🧮 Problem Formulation

We consider a system with:

- **n integer variables** (n is even)  
- Each variable is bounded:  
  $a_j ≤ x_j ≤ b_j$
- Global constraint:  
  $sum (j=1..n) x_j ≤ B $
  
---

## 🎯 Objective Function

$$ x_1·x_2 + x_3·x_4 + ... + x(n-1)·x(n) → extremum $$

The task is to:

- **maximize** or **minimize** the objective function  
- while satisfying all constraints  

📄 See full formulation in the report.

---

## ⚙️ Implemented Algorithms

This project includes several optimization approaches:

---

### 🔹 Greedy Algorithm

- Iteratively assigns variable values based on constraints  
- Very fast and simple heuristic  
- Provides a **baseline solution**  

📉 Limitation: may get stuck in suboptimal solutions  

---

### 🐝 Bee Algorithm (with Local Search)

![Bee Algorithm Scheme](images/bee_scheme.gif)

- Inspired by **swarm intelligence**
- Simulates:
  - scout bees → exploration  
  - forager bees → exploitation  
- Includes:
  - random solution generation  
  - local improvement  
  - feasibility correction (“reanimation”)  

📌 **Time complexity:** $O(n · k)$, where *k* is the number of iterations  

---

### 🧬 Genetic Algorithm

![Genetic Algorithm Scheme](images/genetic_scheme.png)

- Evolutionary optimization method  
- Based on:
  - selection (tournament)  
  - crossover (recombination)  
  - mutation  
  - local optimization  
  - population update  

Key features:

- Works with populations of solutions  
- Handles constraints via repair mechanism  
- Uses fitness function based on objective value  
- Strong global search capability  

---

## 🧪 Experiments & Analysis

The algorithms were evaluated through multiple experiments:

### 🔍 Investigated factors:
- number of variables (problem size)  
- number of iterations  
- constraint parameter **B**  
- selection strategies (Genetic Algorithm)  
- impact of local optimization  

---

### 📊 Example Results

![Experiment Results](images/experiment_1.png)

---

### 📈 Key Observations

- Solution quality improves with more iterations  
- Genetic algorithm consistently finds **better optima**  
- Bee algorithm provides **stable and balanced performance**  
- Greedy algorithm is fastest but least accurate  
- Constraint **B strongly affects feasibility and solution space**  

---

## 🧱 Project Structure

```
ConsoleApp1/
│
├── BeeAlgorithm.cs        # Bee algorithm implementation
├── GeneticAlgorithm.cs    # Genetic algorithm implementation
├── GreedyAlgorithm.cs     # Greedy algorithm
├── InputData.cs           # Input data generator
├── DataRecorder.cs        # Experiment logging
├── Report.cs              # Results processing
├── Program.cs             # Main entry point
├── ConsoleApp1.csproj     # Project configuration
```

---

## 🛠️ Technologies Used

* **C# (.NET 5.0)**
* Console application
* Custom algorithm implementations (no external ML libraries)

---

## 🎯 Key Features

* Multiple optimization algorithms in one project
* Support for both **minimization and maximization problems**
* Custom **input generator** for test cases
* Experimental comparison framework
* Clear algorithm implementations for educational purposes

---

## 📊 Conclusions

Based on the theoretical analysis and experimental evaluation of the developed algorithms, the following conclusions were obtained:

* The considered problem belongs to the class of **combinatorial optimization problems with constraints**, where finding an exact optimal solution is computationally expensive.

* The **Greedy Algorithm** provides fast results with low computational cost, but its solutions are often suboptimal due to its local decision-making nature.

* The **Bee Algorithm with Local Search** demonstrates:

  * good exploration of the search space
  * improved solution quality compared to greedy methods
  * stable performance across different problem sizes
  * effective balance between diversification and intensification

* The **Genetic Algorithm** showed the best overall performance:

  * consistently produces high-quality solutions
  * effectively explores the global search space
  * benefits significantly from:

    * selection strategy
    * mutation parameters
    * local optimization

* Experimental analysis confirmed that:

  * increasing the **number of iterations** improves solution quality but increases computation time
  * the constraint parameter **B** significantly affects the feasible solution space
  * **local optimization** noticeably improves final results for both Bee and Genetic algorithms
  * different **selection mechanisms** in the genetic algorithm impact convergence speed and accuracy

* In terms of complexity:

  * heuristic algorithms provide a practical trade-off between **accuracy and performance**
  * Bee Algorithm complexity is approximately $O(n \cdot k)$, where *k* is the number of iterations

* Overall:

  * **heuristic and evolutionary algorithms are effective approaches** for solving this class of problems
  * combining **global search (e.g., genetic algorithms)** with **local optimization techniques** yields the best results

