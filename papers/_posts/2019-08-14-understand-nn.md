---
layout: post
title:  "what does it mean to understand a neural network?"
date:   2019-08-14
tag: paper, neuroscience, optimization
---

NNs provide direction for neuroscience research.

- Core idea: Neuroscience should focus of learning and development to understand how the brain works.
- Motivation: NNs are easily understood in *how they learn*. It is very hard to understand the exact processing they are doing by looking at the weight matrices.
- For the moment, NNs are best understood in terms of their mechanisms for development and learning. 
- Even though NNs are fully observed (total description of all functions, all inputs, all learned weights), it is hard to produce a "meaningful" understanding.
- Claim: The brain's generative process is similar to that of NNs. It obtains information from a world which it stores as a distributed pattern of weight changes. 
- Question: Can an artificial system that is as good as humans at a broad range of tasks be compactly expressed?
  - Notion of compressibility: 
    - system like tic-tac-toe with large number of possible games can be solved by a compactly expressed set of three rules. 
    - system like go with very large number of possible states *cannot* be "solved" by a compactly expressed system. 
  - Systems that solve a broad range of interesting problems at human level *should be less compressible* than specialized system like AlphaGo. (Humans can play Go and do other things)
  - Answer: Expect broadly applicable systems to be hard (or impossible) to compress into a small size.
![]({{site.baseurl}}/assets/imgs/papers/understanding-nn/understand-nn-compressibility.png)
- How ML scientists are trying to understand NNs:
  - Analysis: look for optimization phenomena (vanishing gradients, exploding global dynamics). These do not provide a meaningful understanding of the computations done by the system, only allow diagnosis.
  - Intuitive understanding: stimuli that can fool the system, visualize elements, perturbation analysis. These are not advanced enough to give a meaningful understanding.
- Compression of NNs:
  - The *bulk* of information we need to specify a working model comes from the *world*, which is complicated and (arguably) incompressible.
  - This assumes that the domain of the world we care about is pretty complex (tic-tac-toe vs image recognition)
- Knowing just the architecture and weights of a functioning NN system is not very useful (except for the task it already solves). Instead, knowing learning rules, architectures and loss functions that *train* the system is *far* more useful.
- Brain:
  - While learned information (from the world) might be incompressible, biological information (how nature sets up the brain to learn, anatomy, etc.) might be
  - A breakdown into parameters (nurture, learned information) and principles (nature, *how to learn*) is precisely how most modern NN papers are broken down:
    - tasks and related data (nurture)
    - architectures, loss functions, learning rules, optimization approaches (nature)
  - The nurture part (data sources) cannot be communicated in a straightforward sense (you can show images, but hard to understand totality)
  - The nature part (training info) of NN papers can be expressed in small human understandable equations, i.e. they are *compressible*
  - Argument that a similar finding for brains is possible, however, trying to understand the nurture part might be very hard (given how hard it is for NNs).
  - Conclusion: focus on understanding the nature part, i.e. how the brain is setup for learning and how it learns. The popular approaches used to study brains can readily be focused on studying the nature component as opposed to nurture component.
![]({{site.baseurl}}/assets/imgs/papers/understanding-nn/understand-nn-nature-nurture-principles-data.png)
- **Instead of asking how the brain works, arguably, ask *how it learns to work***
