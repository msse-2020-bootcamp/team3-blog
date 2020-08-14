---
layout: post
title: "Monte Carlo simulation for atomic system"
author: Xudong Zhuang
---

Today, we learn about develop our own Monte Carlo simulation code.

Firstly, the flow of calculation should be established before we can start the development. The flow of calculation is presented below:

1. Generate an initial system state 'm'.
2. Choose an atom with uniform probability from state 'm'.
3. Propose a new state 'n' by translating the particle with a uniform random displacement in each direction.
4. Calculate the energy change for the particle.
5. Accept or reject the new state.

Based on the above working flow, two functions have been developed for later coding, including: 

1. accept_or_reject.
2. calculate_pair_energy.

Herein, accept_or_reject is a function determine whether a Monte Carlo move should be accepted based on the difference of energy before and after the move as well as the temperature. From my perspective, the input variable--beta, which is 1 over temperature can be changed into temperature and beta should be calculated within this function. In this way, people who use our code don't need to calculate the value(s) of beta so that it can be more convenient to them.

The second function is calculate_pair_energy, which allows us to calculate the interaction energy of the particles with its environment (all other particles in the system). Though the calculation of energy can be accomplished by an already existed funtion--calculate_total_energy, this function can greatly reduce our computation consumption as only one particle is changed during one Monte Carlo move.

After the above preparation, Monte Carlo simulation is carried out with some initialization processes at the beginning and the 5-steps flow of calculation presented above. The resulting calculated energy is close to the standard value provided by NIST, which indicates the success of our coding!