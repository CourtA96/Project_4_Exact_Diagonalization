# Project_4_Exact_Diagonalization

## Introduction

The code in "Evolution and entanglement of a system of N spins.ipynb" computes the time evolution of a system of N spins to see how this evolution affects entanglement. More precisely, it take an initially unentangled state, Psi, and evolves it over time, computing the Von Neumann entropy at each timestep. The Von Neumann entropy of a reduced density matrix, is a measure of the entanglement of the system. If a system is separable, it is not entangled and therefore it's Von Neumann entropy is zero.

Starting in a separable state, the entanglement of the system should increase with time until the system is fully entangled. In the following code, the reduced density matrix is includes half of the spins, so the maximum entanglement should be 0.5N.

The system evolves according to the Hamiltonian. The first term in the Hamiltonian is the Ising Model. The evolution is computed using sparse multiplication.

Starting in a separable state, the entanglement of the system should increase with time until the system is fully entangled, the code in "Evolution and entanglement of a system of N spins.ipynb" shows.

## Results

The following are plots of the evolution of the entanglement for N=6 spins:

![](https://raw.githubusercontent.com/CourtA96/Project_4_Exact_Diagonalization/master/Time%20vs%20Entanglement%20N%206%20dt%200.001.png)
![](https://raw.githubusercontent.com/CourtA96/Project_4_Exact_Diagonalization/master/Time%20vs%20Entanglement%20N%206%20dt%200.0001.png)

And the following are plots of the norm as the N=6 system evolves:

![](https://raw.githubusercontent.com/CourtA96/Project_4_Exact_Diagonalization/master/Time%20vs%20Norm%20N%206%20dt%200.001.png)
![](https://raw.githubusercontent.com/CourtA96/Project_4_Exact_Diagonalization/master/Time%20vs%20Norm%20N%206%20dt%200.0001.png)

The following is a plot demonstrating that the code works for N=20 spins:

![](https://raw.githubusercontent.com/CourtA96/Project_4_Exact_Diagonalization/master/Time%20vs%20Entanglement%20N%2020%20dt%200.001.png)

When N=20, it takes about 0.8 seconds to perform the sparse multiplication in the timestep and 0.4 seconds to compute the entanglement entropy. So the above plot only shows the first 100 timesteps instead of the time it takes to achieve maximum entanglement, that would take a significant amount of time.

## Discussion and Conclusion:

The plots for N=6 show the entanglement increasing up to around 2.5, which is close to the expected value of 3. However, the decrease in timestep appears to be affecting the time the system takes to achieve maximum entropy, which should not be occurring. The increase in entanglement should also be linear with time, but is  not due to the loss of normalization shown in the plots of Norm vs time. It is clear from looking at the plots that the linearity increases as the timestep decreases and the norm is better preserved. The code in "Evolution and entanglement of a system of N spins.ipynb" includes code to plot the entanglement vs time of N=20 spins until the system become maximally entangled, but it was not run due to time constraints.

## Works Cited:

The course notes: https://github.com/eschnett/2018-computational-physics-course/tree/master/exact-diagonalization-module
