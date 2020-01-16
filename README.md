# Hopfield-project

Hopfield model and data reconstuction
Description
The Hopfield network, also introduced in the course Models of Theoretical Physics, is a simple model of neuron dynamics that can be mapped to a spin system with inhomogeneous couplings. Hence, Hopfield networks are described as spin glasses, with spins Si and spin-spin interactions $J_{ij} S_i S_j$ . The full Hamiltonian of the system is $H[S]=-\sum_{i&lt;j} J_{ij}S_i S_j$. The network in practice is used to store patterns in its spin-spin coupling constants $J_{ij}=J_{ji}$ . A pattern ${x_i|i=1,...,N}$ is a given configuration of spins ${x_i=S_i}$, each equal to +1 or -1. It could represent for example a black (+1) and white (-1) pixel in a picture. The properties of the Hopfield network include the fact that:

a. it can store P different patterns $x^a=\{x^a_{i}\}$ $(1\le a \le P)$ as long as P is much smaller than the number N of spins.

b. it can recover a pattern $x^a$ from a corrupted ya by energy minimization of the spins of $y^a$.

Datasets
a. a set of random arrays and patterns;

b. the MNIST database of handwritten digits. In this case, the group should find a way to define the P=10 patterns relative to the 10 digits 0,1,2,..,9.

Assignments
The project aims at simulating a Hopfield network by:

a. Generate or read from file P patterns and imprint their vaules in the couplings Jij between spins, by fixing the couplings to constant values $J_{ij} = \sum_{a=1}^P x^a_i x^a_j / N$. Note that a mean field version is adopted if all pairs $1\le i \le j \le P$ are used (this is what was presented in the theoretical course). If a 2d image is considered for a pattern, one can also explore other versions, such as nonzero coupling only between spins within a distance R from each other.

b. Generate corrupted patterns $\{y^a\}$, for example, by copying each $y^a_i = x^a_i$ with probability $q&lt;1$, otherwise setting $y^a_i = -x^a_i$ with probability $(1 – q)$.

c. Recover the patterns from progressively more corrupted $y^a$, obtained by increasing $q$, till the point where it becomes difficult to get back to the original patterns xa. The recovery may be implemented by iterating the “sign” rule (each new spin at time t+1 equals $S_i(t+1) = \sum_j J_{ij}S_j(t)$ obtained from spins at time t) starting from $S(0)=y^a$ . It can also be attempted by a minimization of the Hamiltonian with a Monte Carlo based on random spin flips and the Metropolis rule.

d. Check how much pattern overlap is allowed while keeping each pattern distinguishable from the others.

e. Describe the clearly and coherently the findings of the previous points.
