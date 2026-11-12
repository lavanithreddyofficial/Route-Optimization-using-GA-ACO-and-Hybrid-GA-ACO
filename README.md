# Route Optimization using GA, ACO, and Hybrid GA-ACO

**Author:** Lavanith Reddy Adavally

## 📌 Overview
This project explores and compares three metaheuristic optimization approaches to solve the **Euclidean Traveling Salesman Problem (TSP)** across a dataset of 30 locations[cite: 29, 31]:
1. **Genetic Algorithm (GA):** Uses permutation encoding, tournament selection, Ordered Crossover (OX), swap mutation, and elitism[cite: 33].
2. **Ant Colony Optimization (ACO):** Uses probabilistic path selection driven by pheromone trails ($\alpha=1.0$) and heuristic visibility ($\beta=2.0$), with iterative pheromone evaporation ($\rho=0.5$)[cite: 34, 35].
3. **Hybrid GA-ACO:** Combines GA's broad global exploration with periodic ACO local refinement (injecting pheromone-guided solutions into the population every 10 generations)[cite: 32, 35].

---

## 📊 Performance Evaluation & Results

The algorithms were evaluated on a 30-city Euclidean coordinate dataset (`route_dataset.csv`) using final tour distance, convergence behavior, and wall-clock execution time[cite: 31, 32, 38, 47]:

| Algorithm | Final Best Distance | Execution Time (s) | Key Characteristics |
| :--- | :---: | :---: | :--- |
| **Genetic Algorithm (GA)** | `543.01` - `585.51` | `~6.68s` - `13.15s` | Fastest execution; broader exploration, slower convergence[cite: 38, 39, 47]. |
| **Ant Colony Optimization (ACO)** | **`462.31`** | `~40.99s` - `98.50s` | Highest solution accuracy (shortest route); computationally expensive[cite: 38, 47]. |
| **Hybrid GA-ACO** | `490.04` - `508.01` | `~6.58s` - `16.10s` | Strong trade-off between route accuracy and execution speed[cite: 38, 47]. |

*(Note: Exact metrics vary slightly across runs due to stochastic initialization; values reflect documented report benchmarks and notebook execution outputs[cite: 38, 47].)*

---

## 🛠️ Complexity Analysis

* **Genetic Algorithm:** Time $O(G \times P \times N)$ | Space $O(P \times N + N^2)$[cite: 44]
* **Ant Colony Optimization:** Time $O(I \times A \times N^2)$ | Space $O(A \times N + N^2)$[cite: 44, 45]
* **Hybrid GA-ACO:** Time $O(G \times P \times N + (G/K) \times A \times N^2)$ | Space $O(P \times N + N^2)$[cite: 44, 45]

*(Where $N$ = cities, $P$ = population size, $G$ = generations, $A$ = ants, $I$ = iterations, $K$ = hybrid interval[cite: 44].)*

---
