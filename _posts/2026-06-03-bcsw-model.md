---
layout: post
title: "Notes on the BCSW Model of Supply Chain Fluctuations"
author: "Vivek S. Handebagh"
date: 2026-06-03
math: true
---

Personal notes on the paper: **"Aggregate Fluctuations from Independent Sectoral Shocks: Self-Organized Criticality in a Model of Production & Inventory Dynamics"** (Bak, Chen, Scheinkman, Woodford; 1992)

## Overview

1. **Setup**
2. **The Model**
    - define variables
    - define nature of dynamics
    - example of avalanche
    - given distribution on shock space
    - ${T_s}$ is an abelian group, so we can just study $Y_j(t)$
3. **Results**
    - $P(R_j = r) = 2^{-(2r+1)} C_r$
    - large-$r$ case (Stirling's approx)
    - avalanche size has no finite mean
4. **Discussion on criticality**
    - mechanisms for self-organized criticality
    - critical exponents
    - scaling relation

---

## 1. Setup

Consider an economy made up of a large number of productive units, each of which supplies only a small number of customers, and in turn buys from only a small number of suppliers.

We will suppose that productive units are located on a cylindrical lattice of $L \times L$. Each unit buys supplies from the two units immediately below it, except the units in the bottom row. The bottom row represents the primary economic inputs (produced w/o any produced inputs). Each unit sells to the two firms immediately above it, except units in the top row.

## 2. The Model

Some assumptions:
- average production costs are minimized by producing batches of 2 units of the good each time that production occurs.
- the cost of holding one unit of inventory is negligible, but not so for anything more. Hence, each unit will only hold 0 or 1 unit of the good.
- production is instantaneous once inputs are purchased.

Then the dynamics of a unit's inventory is: $$x_{ij}(t+1) = x'\big(x_{ij}(t),, s_{ij}(t)\big)$$
We can define the vector of exogenous shocks: $$\vec s(t) = \big(s_{1,1}(t), \ldots, s_{1,L}(t)\big) \in S$$

Then, given some probability distribution on shock space $S$ and iid draws of $\vec s$, the dynamics define a Markov chain on $X$. For each $j$: $$s_{1,j}(t) = \begin{cases} 0 & \text{w/ prob } 1-p \\ 1 & \text{w/ prob } p \end{cases}$$

Limiting case: If each final good's demand fluctuates with some finite variance and is independent of the other final goods, then as $L \to \infty$, the aggregate production by final goods $\to$ constant (central limit theorem).

The motivating question: Is the economy always calm when there is no aggregate shock?
In the real world GDP can fall several percent without any synchronized cause. Even if demand is steady, how do disturbances in the supply chain propagate?

For each possible $s \in S$, there is a transition operator $T_s : X \to X$, and if $S_1 + S_2 = S$, then $$T_S = T_{S_1} \cdot T_{S_2} = T_{S_2} \cdot T_{S_1}.$$ ${T_s}$ is an abelian group → this means the effects of a shock vector $S$ that affects $N$ sites is equivalent to a succession of $N$ shocks. $$Y(t) = \sum_{j=1}^{N} Y_j(t)$$ where each $Y_j(t)$ is the size of an avalanche (the amount of aggregate production it triggers).

The uniform distribution on $X$ is invariant under $T_s$, and so forms an ergodic distribution. Hence, we can talk about unconditional distributions for $Y_j$.

- Each avalanche has a left frontier and a right frontier: $u(i)$ and $v(i)$.
- Under the uniform distribution, each site the avalanche hasn't touched yet is still a fair coin flip.
- The frontiers get extended only through successive coin flips.
- So the width, $w(i) = v(i) - u(i) + 1$, is just a simple random walk w/ no drift.
- Define $R$ as the depth, the row at which the avalanche dies ($W = 0$).

## 3. Result

From random walk theory: $$P(R_j = r) = 2^{-(2r+1)} C_r$$ where $$C_r = \frac{1}{r+1}\binom{2r}{r} = \frac{(2r)!}{r!,(r+1)!} \quad \text{(Catalan number) }$$ 

How often do large avalanches happen in the large-$r$ limit?
Apply Stirling's approximation to approximate $P(R)$:
$$r! \approx \sqrt{2\pi r}\left(\frac{r}{e}\right)^r$$ $$\to \quad C_r \approx \frac{4^r}{\sqrt\pi}, r^{-3/2}$$ $$\to \quad P(R_j = r) \approx \frac{1}{2\sqrt\pi}, r^{-3/2}$$ $$P(R_j \ge r) \sim \frac{1}{2\sqrt\pi}\sum_{r' \ge r} r'^{-3/2} \sim \frac{1}{\sqrt\pi}, r^{-1/2}$$

→ The probability that an avalanche lives to a depth $r$ decays as a power law.

- A fraction $\sim \tfrac{1}{\sqrt r}$ of supply-chain shocks sends a cascade $r$ layers back.

**What can we say about $Y_j$?**

- After $i$ steps, a driftless random walk is spread over a region $\sim \sqrt i$. $$Y_j = \sum_{i}^{R_j} w(i) = \int_0^{R_j} \sqrt i; di = \frac{2}{3} R_j^{3/2}$$
    
- What is $\Pr(Y_j > y)$? This is the same as asking $\Pr(R_j > r)$ where $r = \left(\tfrac{3}{2} y\right)^{2/3}$. We know that $$\Pr(Y_j > y) \sim \Pr(R_j > y^{2/3}) \sim \left(y^{2/3}\right)^{-1/2} = y^{-1/3}$$
    
- To get the tail-end density, we just differentiate: $$P(Y_j) \sim y^{-4/3}$$

But this has no finite mean: $\int^\infty y \cdot y^{-4/3}, dy$ diverges. No finite variance either.

## 4. Discussion on criticality & exponents

- Normally we are used to a system in which we tune a parameter to reach criticality.
- Here that parameter is inventory density, which sets the effective transmission probability.
- If stock is abundant, $p < p_c$: incoming orders get absorbed. But as orders keep coming, stock is depleted and $p \to p_c$.
- If stock is scarce, $p > p_c$: orders get propagated all the way to the boundary and dissipate out, until production refills shelves such that $p \to p_c$.
- This is self-organized criticality.

**Critical exponents:**

|Exponent|Definition|Value|Meaning|
|---|---|---|---|
|$\tau$|$P(y) \sim y^{-\tau}$|$4/3$|size distribution|
|$\alpha$|$P(R) \sim R^{-\alpha}$|$3/2$|duration / depth|
|$D$|$y \sim R^{D}$|$3/2$|size–depth scaling|
|$\delta = \alpha - 1$|$P(R > r) \sim r^{-\delta}$|$1/2$|survival / persistence|
|$Z$|$R \sim W^{Z}$ ($W \sim R^{1/2}$)|$2$|diffusion of random walk|
There is a scaling relation here. Since size and duration are tied by $Y \sim R^D$, their distributions can't be independent: $$P_Y(y), dy = P_R(R), dR$$ $$\to \quad \alpha - 1 = D(\tau - 1)$$ 