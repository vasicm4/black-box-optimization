# black-box-optimization

## Overview
This project applies a **genetic algorithm** to a BlackBox optimization problem, specifically targeting the optimization of neural network parameters when the error function is unknown in analytic form. Instead of relying on gradient-based methods, the algorithm treats the model as a black box, evaluating candidate solutions only through computed error values.

## Problem Statement
The task is to minimize the absolute error of a neural network by adjusting its weight parameters. Since the error function cannot be expressed analytically, classical optimization techniques are unsuitable. Genetic algorithms provide a suitable alternative due to their ability to explore complex, high-dimensional search spaces and avoid local minima.

## Methodology

### Genetic Algorithm Workflow
1. Define input parameters, fitness function, and algorithm configuration  
2. Initialize population (chromosomes as real-valued vectors)  
3. Evaluate chromosomes using the model error function  
4. Select parents (roulette wheel selection)  
5. Generate offspring through crossover  
6. Apply mutation operators  
7. Preserve best solutions using elitism  
8. Repeat until convergence or iteration limit  

### Mutation Operators
- **Rotation:** Rotate a subset of genes  
- **Swap:** Swap two positions in a chromosome (best performing in tests)  
- **Inversion:** Reverse a segment of genes  

### Key Parameters
- Population size: 200  
- Max iterations: 200  
- Crossover rate: 0.6  
- Mutation rate: 0.4  
- Elitism rate: 0.1  
- Error threshold: 0.0005  

## Results
Nine independent runs demonstrated stochastic behavior, with best-found errors varying between runs. The lowest error achieved was **0.1677**, confirming the effectiveness of the algorithm. Convergence graphs showed consistent improvement of best and average solutions over generations.

## Conclusion
The genetic algorithm proved to be an effective approach for BlackBox optimization of neural network parameters. While the stochastic nature means global minima are not guaranteed every time, repeated runs improve the likelihood of high-quality solutions. The combination of roulette selection, swap mutation, and elitism yielded the fair balance between exploration and exploitation.
