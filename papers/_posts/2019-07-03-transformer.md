---
layout: post
title:  "Transformer: attention is all you need"
date:   2019-07-03
tag: [language models, transformers, pre-training]
---

Let's get transforming!

- New sequence transduction model solely based on attention mechanisms
- **Goal**: Superior translation quality + less training time; make parallelizable
- **Idea**: Attention mechanism used to draw global dependencies between input and output. Replace recurrent layers with multi-headed self attention.
- Self-attention relates different position of a single sequence in order to compute a representation of the sequence. 
- Number of operations required to relate two arbitrary input and output positions is a constant unlike recurrent or convolutional architectures
- An attention function is a mapping from a query and key-value pair to an output. Query, key, value and output are all vectors. 
  - Output is computed as weighted sum of values where a particular value's weight is given by compatibility function of the query with the corresponding key.
  - $Attention(q, k, v) = w^\top v$ and $w_i = compat(q, k_i)$
  - Rewritten as $Attention(q, k, v) =  compat(q, k)^\top v$
  - This paper uses a `softmax` as a compat function, and they scale it by a factor
- Architecture involves positional encoding, attention sublayers, feed-forward sublayers. residual connections and layer norms. 
- **Claim**: their model is better and more efficient. 
- **Side Claim**: Self-attention could also yield more interpretable results
- **Questions**
  - What's a sequence transduction model?
  - How did they get the scaling factor?
  - What's a BLEU?
  - What's a sinusoid?
  - What's byte-pair encoding?
  - Interesting `learning-rate scheduler`
  - What's multi-headed self attention?