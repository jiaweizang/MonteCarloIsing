#  Monte Caro calculation for 1D and 2D Ising Model

This repository contains code for the Monte Carlo Calculation of an Ising model.

The code was used for the course Thermal and Statistical Physics, where I did TA and taught students how to do
the Monte Carlo Simulation for the Ising Model.


Code author: Jiawei Zang (jiaweizang)

## Ising Model
Consider the 2D L*L-spin Ising model, in which each site is associated with a variable $s_{i,j}=1,-1$. The energy is 


![equation](https://latex.codecogs.com/svg.image?E=-%5Cfrac%7BJ%7D%7B2%7D%5Csum_%7Bi=0,%20%5Cldots-1%20;%20j=0%20%5Cldots%20L-1%7D(s_%7Bi,%20j%7D(s_%7Bi&plus;1,%20j%7D&plus;s_%7Bi-1,%20j%7D)&plus;s_%7Bi,%20j%7D(s_%7Bi,%20j&plus;1%7D&plus;s_%7Bi,%20j-1%7D)))

It has periodic boundary conditions: $s_{i,j}=s_{L+i,j}$

Based on Monte Caro method, the main procedure is as follows:
1. Create a L * L lattice, and start with a given spin configuration $s_p$ and energy $E_p$

2. Select a site at random and propose to flip the spin on that site (i.e. change the sign of the variable on that site).

3. Compute the new energy $E_{new}$, and calculate the energy difference $\Delta E = E_{new} - E_p$ .

4. Accept or reject the proposal with the detailed balance probability:
a) if $\Delta E<=0$, accept the proposal. b) if $\Delta E>0$, accept the proposal with probability $P = e^{−\frac{\Delta E }{k_BT}}$, and reject proposal with probability 1-P.

5. Return either the original state or the new state according to whether the proposal is accepted.

6. Go back to step 2, repeat the procedure n_max times until it reaches equilibrium. 
* set $k_B = 0$
* we need to consider boundary conditions: we can use the trick: i% N. For example, 0%N=0, (N+2)%N=2




