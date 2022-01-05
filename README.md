# CMB-Foreground-Cleaning
## Motivation
This project was prart
## Introduction
This project was funded by the Columbia University cosmology department and uses data science and statistics to clean foreground components from relevant Cosmic Microwave Background Radiation maps. This project is motivated by the fact that the foreground contaminants in the CMB maps are not completely "Gaussian" i.e. they do not reflect a reflect a symmetrical normal distribution. This asymmetry stems from the fact that the contaminants across the sky are not evenly distributed, in large part due to the dust in the Milky Way plane. The dust in this region is significantly greater than dust in other regions of the sky. By minimizing the necessary statistical components, we can minimize the effects of this asymmetry and achieve a normal distribution for analysis.
## Methodology
My research project can be broken down into 3 steps:
1. Derive the equations for finding the minimum variance of CMB maps and finding a procedure for minimizing the skewness of the same CMB maps.
2. Implementing these procedures in Python to optimize for both the variance and the skewness of CMB maps.
3. Plotting the results of the optimized sets of weights.

In the first step, I used the method of LaGrange multipliers to solve for the set of weights that would mimimize the variance under the constraint that the set of weights would sum up to 1. This procedure takes into account a mathematical representation of CMB maps in which we seek to find the ideal set of weights that prioritzes observations at particular frequencies that are less noisy and down-weight those that are more noisy. The derivation for the variance shown here() is complete while the derivation for the skewness shown here() is outlined only as a procedure because it's not feasible to solve this derivation by hand, but ultimately leads to its reproduction in code and optimization using necessary packages. In the second step, in order to find the solution arrays for the weights, I implemented various statistical and pixell methods to read in and analyze the maps. Using Jupyter Notebooks, I used the pixell package to display and manipulate map data. In order to minimize the variance and skewness, I defined two variables $r$ and $b$, which acted as the co-variance and co-skewness matrices, respectively. Again respectively, these variables were 2-dimensional and 3-dimensional NumPy arrays. I also defined the constraint mentioned above using a lambda function. Using optimization packages in SciPy, I obtained the solution arrays, which both satisfied the constraint and provided a weight for each CMB map frequency. Because of the large size of the map files and computations 
## Results
## Relevant Skills Used
- Python
- NumPy
- SciPy
- Linux
- HPC clusters and computing
- optimization
- **broader domains: cosmology, data science, high-performance computing, statistics, research
