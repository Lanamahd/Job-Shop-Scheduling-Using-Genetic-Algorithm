# Job-Shop Scheduling Using Genetic Algorithm

## Overview

This project implements a **Genetic Algorithm (GA)** to solve the **Job-Shop Scheduling Problem (JSSP)**, a combinatorial optimization problem that involves scheduling a set of jobs on a set of machines to minimize the makespan (total completion time). The solution incorporates advanced genetic operators such as crossover, mutation, and fitness evaluation, along with visualization tools like Gantt charts to evaluate schedules.

---

## Table of Contents

1. [Features](#features)
2. [Dataset](#dataset)
3. [Algorithm Workflow](#algorithm-workflow)
4. [Key Components](#key-components)
5. [Results and Visualization](#results-and-visualization)
6. [Getting Started](#getting-started)
    - [Prerequisites](#prerequisites)
    - [Running the Project](#running-the-project)
7. [File Descriptions](#file-descriptions)
8. [Conclusion](#conclusion)

---

## Features

- **Genetic Algorithm Implementation**:
  - Fitness evaluation to optimize schedules.
  - Crossover operators for generating offspring from parent schedules.
  - Mutation operators to introduce variability and explore the search space.
  
- **Makespan Calculation**:
  - Calculates the total completion time for a given schedule.
  - Ensures valid schedules by respecting machine constraints.

- **Visualization**:
  - Gantt chart generation to visualize job schedules on machines.

- **Scalability**:
  - Works with multiple jobs and machines provided in CSV format.

---

## Dataset

The input dataset is provided in the `jobs.csv` file, which contains job operations in the following format:
    ```
    Operations M1[5]->M2[3]->M3[2] M2[4]->M1[6] M3[2]->M1[3]->M2[4] M1[2]->M2[2]
    ```

Each line represents a job, with operations specifying the machine (`Mx`) and the time required (`[time]`).

---

## Algorithm Workflow

1. **Initialization**:
   - Parse job operations from the dataset.
   - Generate an initial population of schedules.

2. **Genetic Operators**:
   - **Selection**: Use proportional selection to choose parents based on fitness.
   - **Crossover**: Apply Partially Mapped Crossover (PMX) to generate offspring.
   - **Mutation**: Use inversion and insertion mutations to introduce variability.

3. **Fitness Evaluation**:
   - Calculate the makespan for each schedule.
   - Scale the inverse makespan as the fitness value.

4. **Visualization**:
   - Generate Gantt charts to visualize machine schedules.

5. **Termination**:
   - Repeat the genetic algorithm for a fixed number of generations or until convergence.

---

## Key Components

1. **Makespan Calculation**:
   - Determines the total time required to complete all jobs on all machines.

2. **Mutation Operators**:
   - **Inversion Mutation**: Reverses a segment of a job's operations.
   - **Insertion Mutation**: Moves an operation to a new position within the same job.

3. **Crossover Operator**:
   - **Partially Mapped Crossover (PMX)**: Ensures valid offspring schedules by preserving job constraints.

4. **Gantt Chart Visualization**:
   - Displays the schedule of jobs on machines along with their start and end times.

---

## Results and Visualization

- **Objective**:
  - Minimize the makespan while ensuring valid schedules.

- **Visualization**:
  - The Gantt chart shows the start and completion times of each job operation on specific machines.

Example Gantt chart:
    ```
    +-------------------+-------------------+-------------------+ | Machine M1 | Machine M2 | Machine M3 | +-------------------+-------------------+-------------------+ | Job 1 (5 units) | Job 2 (4 units) | Job 3 (2 units) | | ... | ... | ... | +-------------------+-------------------+-------------------+
    ```

---

## Getting Started

### Prerequisites

- Python 3.8 or later
- Required Python libraries:
  - `numpy`
  - `pandas`
  - `matplotlib`

Install the required libraries using:
    ```bash
    pip install numpy pandas matplotlib

### Running the Project
1. Clone the repository:
    ```bash
    git clone https://github.com/Lanamahd/Job-Shop-Scheduling-Using-Genetic-Algorithm.git
    cd Job-Shop-Scheduling-Using-Genetic-Algorithm

2. Ensure the input dataset (jobs.csv) is correctly formatted.

3. Run the main script:
    ```bash
     python jodShop.py

4. Follow the console output to view the makespan and Gantt chart for each schedule.

---

## File Descriptions

### **`jodShop.py`**
- Main Python script implementing the genetic algorithm, makespan calculation, and visualization.

### **`jobs.csv`**
- Input dataset containing job operations and machine requirements.

### **`Report.pdf`**
- Detailed report explaining the algorithm, results, and analysis.

---

## Conclusion

The **Job-Shop Scheduling Using Genetic Algorithm** project demonstrates the power of genetic algorithms in solving complex scheduling problems. By combining fitness evaluation, genetic operators, and visualization, the project provides an effective solution for minimizing makespan and optimizing schedules. 
