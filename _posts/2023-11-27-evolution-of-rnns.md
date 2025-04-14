---
layout: post
title: "The Evolution Towards Biologically Plausible Artificial Recurrent Neural Networks"
author: Vivek Handebagh
date: 2023-11-27
categories: [neuroscience, AI, deep-learning]
math: true
---

## Introduction

Since discovering the brain's computational nature, scientists have used its principles to create artificial neural networks. Both Computer Science and Neuroscience have since grown in parallel—Computer Science adopting neuro-inspired frameworks, and Neuroscience leveraging computational models to better understand the brain. Recently, as deep neural networks have become more complex, some models now exhibit strikingly human behavior. This has created new opportunities for bridging the gap between mathematics and biology.

Recurrent neural networks (RNNs) are central to this endeavor. Inspired by the recurrent circuits of the brain, RNNs model temporal and dynamic processes, storing information across time and offering insights into the neural basis of cognition.

However, modern RNNs depend on mechanisms like backpropagation through time and are often trained for isolated cognitive tasks[^1]. Efforts are underway to make RNNs more biologically plausible. These include long-term memory retention via skip connections[^2], local synaptic learning rules[^3], and unsupervised pruning algorithms for network efficiency[^4].

This literature review explores the validity of RNNs as models of cognition, their scientific contributions, their limitations, and ongoing work to biologically ground their design.

---

## The Case for RNNs as the Model Organism

To justify RNNs as models of brain computation, we first need a theoretical lens through which to view brain activity. **Dynamical Systems Theory (DST)** provides that lens.

In DST, the brain's state space is a high-dimensional space where each axis corresponds to the firing rate of a neuron. The system's evolution is described by differential equations that define the vector field over this space[^5]. This establishes a mathematical parallel between artificial and biological neural dynamics.

RNNs, trained with techniques like stochastic gradient descent or backpropagation through time, can reconstruct any observed dynamical system (DS). One promising method, **Low-rank Inference from Neural Trajectories (LINT)**, shows how low-rank RNNs (lrRNNs) can be fit to neural data, yielding interpretable and biologically meaningful dynamics[^6].

---

## Limitations of RNNs as Biological Models

While RNNs have yielded substantial theoretical insights, they fall short of capturing key biological constraints. For example, LSTMs trained to solve six distinct tasks produced solutions that bore no resemblance to task representations in the brain[^7]. This highlights that multiple computational solutions can exist—but not all are biologically plausible.

RNNs trained on isolated lab tasks may bypass constraints faced by biological systems, such as flexibility[^1]. Backpropagation itself is biologically implausible, requiring $\mathcal{O}(N^3)$ memory while the brain operates with only $\mathcal{O}(N^2)$ synaptic variables. Moreover, experimental data shows that only a small subset of neurons participate in memory formation[^3].

---

## RNN-Propelled Developments

Despite these shortcomings, RNNs have yielded powerful discoveries about brain-like computation:

- **Task Specialization**: When trained on twenty cognitive tasks, RNNs self-organized into regions functionally specialized for different computations[^8], echoing structures like the prefrontal cortex and hippocampus[^9].

- **Dynamical Motifs**: DST analysis showed that different tasks used different motifs—like attractors or rotations—modularly reused depending on context[^10].

- **Transitive Inference (TI)**: RNNs trained on TI tasks not only generalized to unseen combinations but mirrored the behavioral responses of living subjects[^11]. This opens the door to simulating abstract human faculties like logical reasoning.

- **Representational Strategy**: RNNs adaptively switch between rich and minimal internal representations based on noise level, mimicking human cognitive filtering[^12].

- **Tiny RNNs**: Remarkably, one- or two-unit RNNs can outperform classical cognitive models in reward-learning tasks, emphasizing that cognition may be governed by surprisingly low-dimensional dynamics[^13].

---

## Towards Biological Plausibility

Modern architectures like LSTMs and GRUs rely on gating mechanisms absent from biological brains. Yet without them, modeling memory or decision-making remains difficult. Skip connections, aligned with intrinsic dynamics, offer one biologically inspired alternative[^2].

A core challenge remains: **a biologically plausible alternative to backpropagation**. Some efforts train only the output layer and a context layer, which then modulates recurrent activity[^3]. Others implement **forward-only gradient estimation** based on striatal circuits[^14]. While promising, these still suffer from variance in unbatched data.

Comparative studies show that biologically inspired algorithms often require fewer data and converge faster than backpropagation[^15]—a testament to the computational elegance of the brain.

Lastly, **pruning mechanisms**—mirroring synaptic elimination during development—have been proposed using noise to make structural information locally accessible, allowing networks to remove redundant connections without disrupting dynamics[^4].

---

## Conclusion

RNNs are evolving toward greater biological plausibility, with profound implications. Can we one day describe brain dynamics with the precision of Maxwell’s equations? Can deep learning frameworks eventually integrate both cellular and network-level dynamics?

As models grow more aligned with biology, they may drive the development of efficient AI systems—ones that rival human cognition while operating on orders of magnitude less energy.

Ultimately, this path leads us not only toward better machines but toward deeper truths about what intelligence is—and what role artificial intelligence will play in our shared future.

---

## References

[^1]: Yang, G. R., Joglekar, M. R., Song, H. F., Newsome, W. T., & Wang, X. J. (2021). Task representations in neural networks trained to perform many cognitive tasks. *Nature Neuroscience*, 24(3), 305–316.
[^2]: Soo, J., et al. (2023). Training recurrent networks with dynamics-aligned skip connections.
[^3]: Masse, N. Y., et al. (2022). Flexible recurrent networks through top-down context modulation.
[^4]: Moore, T., et al. (2021). Using noise for synaptic pruning in unsupervised networks.
[^5]: Durstewitz, D. (2022). Dynamical systems approaches in cognitive neuroscience.
[^6]: Valente, M., et al. (2022). Extracting low-rank recurrent dynamics from neural trajectories.
[^7]: Da Costa, R., et al. (2019). Elucidating the solutions found by LSTMs in cognitive tasks.
[^8]: Article on multitask-trained RNN specialization.
[^9]: Miconi, T. (2017). Biologically plausible learning in recurrent neural networks.
[^10]: Driscoll, L. N., et al. (2022). Dynamical motifs for cognitive flexibility.
[^11]: Kay, J. W., et al. (2022). Generalization of transitive inference in RNNs.
[^12]: Stroud, J. P., et al. (2023). Representation strategies in high vs. low noise tasks.
[^13]: Ji-An, S., et al. (2023). Tiny RNNs outperform classical models in RL tasks.
[^14]: Lemmel, J., et al. (2023). Real-time forward learning in RNNs.
[^15]: Gupta, A., et al. (2023). Bio-inspired learning converges faster than backpropagation.
