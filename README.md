# Project_4_Exact_Diagonalization

## Introduction

The following code computes the time evolution of a system of N spins to see how this evolution affects entanglement. More precisely, it take an initially unentangled state, \bra{Psi}, and evolves it over time, computing the Von Neumann entropy at each timestep. The Von Neumann entropy of a pure multipartite system $\bra{\Psi_AB}$ is defined by,

\begin{align*} S = \sum_n \rho_n \log_2(\rho_n) \label{eq1} &&(1) \end{align*}

where $\{\rho_n\}$ are the eigenvalues of $\hat{\rho}_{AB} = \bra{\Psi_{AB}}\ket{\Psi_{AB}}$. The Von Neumann entropy of a reduced density matrix,

$$ \rho_A = \text{Tr}({\bra{\Psi_{AB}}\ket{\Psi_{AB}}}) = \sum_j \ket{j_B}({\bra{\Psi_{AB}}\ket{\Psi_{AB}}})\bra{j_B} = \sum_j (\hat{\rho}_A)_{mn} $$

is a measure of the entanglement of the system. If a system is separable, it is not entangled and therefore it's Von Neumann entropy is zero.

Starting in a separable state, the entanglement of the system should increase with time until the system is fully entangled. In the following code, the reduced density matrix is includes half of the spins, so the maximum entanglement should be $\frac{N}{2}$

The system evolves according to:

$$ \bra{\Psi(t)} = e^{-iHt}\bra{\Psi(0)}$$

where $H$ is the the Hamiltonian:

\begin{align*} H=-(\cos{\theta}(\sigma_x\otimes\sigma_x)+\frac{\sin{\theta}}{2}(\sigma_z\otimes I+I\otimes\sigma_z)) + \frac{1}{2}(\sigma_x\otimes\sigma_y+\sigma_y\otimes\sigma_x) && (2) \end{align*}

where the $\sigma_i$s are the Pauli matrices and $I$ is the identity. The first term in the Hamiltonian is the Ising Model.

Computing the time evolution in the way, however, is computationally expensive, so the evolution can be approximated by equation (4), which uses sparse multiplication instead of an  exponential.

Starting in a separable state, the entanglement of the system should increase with time until the system is fully entangled, the code below shows.

## Results

The following are plots of the evolution of the entanglement for N=6 spins:

The following is a plot demonstrating that the code works for N=20 spins:

When N=20, it takes about 0.8 seconds to perform the sparse multiplication in the timestep and 0.4 seconds to compute the entanglement entropy. So the above plot only shows the first 100 timesteps instead of the time it takes to achieve maximum entanglement, that would take a significant amount of time.

## Discussion and Conclusion:

The plots for N=6 show the entanglement increasing up to around 2.5, which is close to the expected value of 3. The increase in entanglement should be linear with time, but is  not due to the loss of normalization shown in the plots of Norm vs time. It is clear from looking at the plots that the linearity increases as the timestep decreases and the norm is better preserved. The code in "Evolution and entanglement of a system of N spins.ipynb" includes code to plot the entanglement vs time of N=20 spins until the system become maximally entangled, but it was not run due to time constraints.
