# CMB Foreground Cleaning
## Introduction
This project was funded by the Columbia University cosmology department and uses data science and statistics to clean foreground components from relevant Cosmic Microwave Background Radiation maps. This project is motivated by the fact that the foreground contaminants in the CMB maps are not completely "Gaussian" i.e. they do not reflect a reflect a symmetrical normal distribution. This asymmetry stems from the fact that the contaminants across the sky are not evenly distributed, in large part due to the dust in the Milky Way plane. The dust in this region is significantly greater than dust in other regions of the sky. By minimizing the necessary statistical components, we can minimize the effects of this asymmetry and achieve a normal distribution for analysis.
## Methodology
My research project can be broken down into 3 steps:
1. Derive the equations for finding the minimum variance of CMB maps and finding a procedure for minimizing the skewness of the same CMB maps.
2. Implementing these procedures in Python to optimize for both the variance and the skewness of CMB maps.
3. Plotting the results of the optimized sets of weights.

In the first step, I used the method of LaGrange multipliers to solve for the set of weights that would mimimize the variance under the constraint that the set of weights would sum up to 1. This procedure takes into account a mathematical representation of CMB maps in which we seek to find the ideal set of weights that prioritzes observations at particular frequencies that are less noisy and down-weight those that are more noisy. The derivation for the variance shown [here]() is complete while the derivation for the skewness shown [here]() is outlined only as a procedure because it's not feasible to solve this derivation by hand, but ultimately leads to its reproduction in code and optimization using necessary packages. The procedure for the variance can be found [here]() and the procedure for the skewness [here]().

In the second step, in order to find the solution arrays for the weights, I implemented various statistical and pixell methods to read in and analyze the maps. Using Jupyter Notebooks, I used the pixell package to display and manipulate map data. In order to minimize the variance and skewness, I defined two variables $r$ and $b$, which acted as the co-variance and co-skewness matrices, respectively. Again respectively, these variables were 2-dimensional and 3-dimensional NumPy arrays. I also defined the constraint mentioned above using a lambda function. Using optimization packages in SciPy, I obtained the solution arrays, which both satisfied the constraint and provided a weight for each CMB map frequency. Because of the large size of the map files and computations, I used a remote connection to Linux to process these large datasets by calling jobs on an HPC cluster. Again due to the large file size, I have two versions of the main code for this project: one for the [code without output]() formatted as an ipynb notebook and another for the [code with output]() formatted as a pdf file.
## Results
After obtaining the two sets of weights for the variance and skewnwss of the CMB maps, I plotted the corresponding CMB maps, and then I compared the weights between the two sets of weights.

Both methods implement the variance and skewness procedures that I outlined in the derivations, and use the minimize function to obtain the respective solution array. I found that the differences in variance and skewness are more prominent towards the middle range of frequencies. Next, I took the difference between the variance and the skewness scaled down to the order of magnitude of the variance and found that the difference is greater towards the middle of the range of frequencies, while the smallest and largest frequencies have a smaller difference between the variance and skewness. 

Up to this point, the results have been focused on an analysis of the variance and skewness that have been optimized separately from each other. The last step of this project was to create a linear combination of the variance and skewness, with a final constraint ensuring that the variance and skewness are properly weighted with respect to the other. Proper optimization of these components together provided the set of weights that most effectively cleans the foreground contaminants under the limitations of the data and methodology used. I used different combinations of weights to find the smallest possible variance and skewness of the solution arrays as possible. This is done by comparing the variance and skewness to the absolute smallest variance and skewness found in the separate implementations above. In the end, I found feasible sets of weights to clean CMB maps using the statistical methods already described above. 
## Relevant Skills Used
- Python
- NumPy
- SciPy
- Linux
- HPC clusters and computing
- optimization
- **broader domains: cosmology, data science, high-performance computing, statistics, research
