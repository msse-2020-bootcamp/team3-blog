---
layout: post
title: "Monte Carlo integration and simulations"
author: Muhan Zhang
---

My second post will be around Monte Carlo (MC) method, which covers what I learned today. It is absolutely inspiring to learn to disintegrate a continual integration into summation of discrete values. In Monte Carlo method, that's the point! And its approach to discrete values is to generate random numbers, as is the core of MC method.

In MC simulation, the calculation of pairwise potential energy is switched to simple summation. This summation is composed of some simple repeated calculation, following a single pattern that can be easily incorporated into Python coding. It has to be emphasized that the pairwise energy should rule out all self-calculation and repetitive terms.

Even though it turns out the final energy calculated is far away from the standard one provided by NIST, the core problem is solved to fix the errors.

1. Cutoff distance. The addition of cutoff distance is apparently to reduce computational costs. After setting this distance, simple comparisons can be operated to avoid complicated calculation. However, for a system with millions of particles, such as bulk system, the accumulated truncation can induce large amount of energy loss. Some small energy can become huge as long as the number of particles is large enough. After we plotted the graph of Lennard Jones potential energy curve, it became clear that larger than 3$\sigma$, distance has little influence on the total energy, but a tail correction function is required to solve the energy-loss catastrophe.

2. Periodic boundary conditions. Most simulations probe the structural and thermodynamical properties of a system of a few hundred to a few thousand particles. Clearly, this number is still far removed from the thermodynamical limit, such as a liquid bulk system. Therefore, in order to simulate bulk phases it is essential to choose boundary conditions that mimic the presence of an infinite bulk surrounding our N-particle system. It is so interesting to explain this involved concept with the game Pac-man by Dr Nash! We found the maximum distance any particle can be from another in each dimension should be $\frac{l_B}{2}$ (where $l_B$ is the box length). The actual distance of the example (0,0,0) and (0,0,8) with box length of 10 should be 2 as the vector is required to be converted to (0,0,-2)!

I really found periodic boundary conditions intriguing and interesting. For a central potential box, there should be 26 identical boxes surrounding, as the central one is ruled out. Actually, the total energy can be expressed like this:
$$U_{tot} = \frac{1}{2}\sum_{i,j,n}'u(|r_{ij}+nL|)$$
where L is box length (a number); $n$ and $\r_{ij}$ are 3D vectors, as $n$ is used to mark the surrounding 26 boxes with 0,1,-1 three integers. The calculation of vectors is of great importance! Prime is used to rule out self-calculation, and $\frac{1}{2}$ is used to remove repetitive terms. These are shown in the code "range(i+1,num_atoms)".