---
layout: post
title: "Learning and Searching for Cellular Automata Structures via Information Feature Space"
author: Vivek Handebagh
date: 2023-05-06
categories: [research, machine-learning, cellular-automata]
math: true
---

## Abstract

To study a complex system, one needs to understand the state space, the processes that operate on that state space, and any patterns and structures that emerge as the process evolves. We want to investigate the underlying connections between these aspects, and see if we can work backwards to identify the properties of a system. Cellular automata (CA) provide a simple framework to explore complex systems, but trying to uncover connections between emergent structures, initial state configurations, and rule-sets in higher-dimensional and multi-state CAs quickly becomes challenging.

Deep learning has been revolutionary in recognizing and learning patterns, and the project aims to apply it to the dynamics of CAs. We explore the simplest models capable of learning the dynamics of CAs. Results indicate that predicting evolved states in small CAs remains challenging. Feature maps based on information measures provide insights into structural complexity and reveal distinct spatial localities within the CAs. Future directions include investigating if these feature maps reveal the number of underlying structures in CAs and if deep learning models can predict CA configurations if only given information features.

---

## Cellular Automata

Cellular automata (CA) are mathematical models that simulate the behavior of complex systems that operate through simple local interactions. Pioneered in the 1940s by John von Neumann, CAs provide a simple framework for studying complex systems and networks.

The basic setup of a CA is a lattice of cells, where each cell can occupy one of a finite number of $k$ states. At each time step, the state of each cell is updated based on its current state and its neighborhood of size $r$. Most studied CAs are 1-dimensional and binary. The state space is then the set of all possible binary strings of length $L$.

One-dimensional CAs can be visually analyzed using space-time diagrams. However, in higher dimensions or with larger neighborhood sizes and multiple cell states, these visual methods quickly become infeasible. Thus, we turn to deep learning to uncover the underlying connections in these more complex settings.

---

## Structures of Cellular Automata

![Spacetime diagram of elementary CA 225](/assets/images/225_spacetime.png)

What does it mean for a CA to contain structures? The image above is a space-time diagram of the elementary CA 225. We see two distinct *textures* propagating through space and time, both driven by the same update rule. Our focus is not just on visually interesting patterns but on understanding their *functional role* in computation and information propagation.

There are several distinct classes of structures:

1. **Static Structures**  
   Arrangements of cells that remain unchanged over time, such as single cells or blocks.

2. **Oscillators**  
   Periodic structures that repeat after a fixed number of time steps.

3. **Spaceships**  
   Configurations that move across the lattice, like gliders in Conway's Game of Life.

4. **Methuselahs**  
   Initially simple configurations that evolve into long-lived, complex patterns before stabilizing.

5. **Chaotic Structures**  
   Highly sensitive to initial conditions, often found in rules like 110.

6. **Fractal-like Structures**  
   Self-similar and compactly encoded, as in the Sierpinski triangle.

---

## The Bridge Between CAs and Deep Learning

Cellular automata are discrete, making traditional dynamical system analysis difficult. However, neural networks—especially Convolutional Neural Networks (CNNs)—are powerful tools for learning from structured data like CA evolutions.

CNNs use convolutional layers that apply filters across input data to extract features like edges, textures, and shapes. These operations resemble CA update rules on a 2D lattice.

A study by Gilpin [^1] showed that CNNs can be trained to learn arbitrary CA rules. However, this doesn't necessarily imply that they can generalize beyond the training data.

![The convolution operation](/assets/images/image.png)

As a baseline, we trained a simple sequential neural network (2 layers, 64 neurons each) to predict the next state of a 10-bit CA (Rule 225). Despite seeing all possible input strings during training, the model only reached ~20% accuracy, later optimized to ~50%. This surprising difficulty motivates our investigation into the *simplest models* capable of learning even simple CA dynamics.

---

## Information Feature Maps

To better understand structural complexity in CAs, we used **information-theoretic measures** like Shannon entropy:

$$
H(X) = -\sum_x p(x) \log_2 p(x)
$$

Entropy helps distinguish regions of order and disorder in CA evolution. Instead of global entropy, we compute local entropy over neighborhoods and assign the value to the center cell, creating a **feature map** of uncertainty.

![Entropy plot for CA 225](/assets/images/225_entropy_plot.png)

This entropy map shows distinct spatial zones in the CA, sharply delineated and possibly indicating distinct underlying structures. We speculate that these entropy “bands” may correspond to fundamental modes of organization within the CA.

We also explored **mutual information**:

$$
I(X;Y) = \sum_x \sum_y p(x,y) \log_2 \frac{p(x,y)}{p(x)p(y)}
$$

This measures dependencies between cell values at different time steps. Such feature maps, layered like image channels, can potentially improve deep learning models' ability to predict future states or infer hidden rules.

We even attempted to train a model using *only* the information feature maps (without binary state images) to predict CA evolution—accuracy dropped to ~15%, but the idea remains promising.

---

## Conclusion

This post introduces the rich world of cellular automata and the surprising difficulties of learning their dynamics, even in simple settings. From observing emergent structures to constructing entropy-based feature spaces, the interplay between deep learning and CAs invites many open questions.

What are the minimal models that can generalize CA dynamics? Can we invert the process and recover rules from observed structures? The journey into learning complex systems through CAs has just begun.

---

## References

[^1]: Gilpin, W. (2019). *Cellular automata as Convolutional Neural Networks*. Physical Review E, 100(3). [https://doi.org/10.1103/physreve.100.032402](https://doi.org/10.1103/physreve.100.032402)
