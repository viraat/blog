---
layout: post
title: Full stack deep learning
tags: [deep learning, full stack]
date: 2020-05-15
---

Summary of notes taken while viewing the full stack deep learning bootcamp.  

## Lecture 2: ML Projects

- Lifecycle of a ML project
![]({{site.baseurl}}/assets/imgs/posts/full-stack/lifecycle-1.png)
  - Planning and project setup
    - what problem; 
    - How; 
  - Data collection and labeling
    - Setup sensors
    - Collect data
    - Annotate data
  - Training and debugging
    - implement baseline
    - research and SOTA
  - Deploy and test
    - Write tests: 
      - different from evaluation of model
      - train model on small subset 
      - test on subset of data
      - no regressions in your code base
      - can make sensible predictions/achieve sensible loss on small subset of your dataset
    - Roll out to production
  - This is not a linear flow, we can always go backward from one of these stages to any of the previous ones
    - Metric is not right
    - Task is too hard
    - Model is probably not well chosen
  - Also things at org level: team and hiring + infra and tooling
  - The one thing you really need to know apart from all of this:
    - Understand SOTA in your domain
      - what's possible
      - what to try next
![]({{site.baseurl}}/assets/imgs/posts/full-stack/lifecycle-detail.png)
- Planning and project setup
  - Prioritizing projects and choosing goals
    - Find high-impact ML problems
      - Automate complext parts of your pipeline
      - Places where cheap prediction is valuable
    - Cost of ML project is driven by data availability and accuracy requirements
  - Mental Models for high impact ML projects
    - Feasability vs Impact framework for ML projects
    - Prediction Machines: Economics of AI 
      - **Look for projects where cheap prediction will have a huge business impact**
    - Software 2.0: Andrej Karpathy
      - 2.0 work with datasets which get compiled via optimization
      - Works better, more general, computational advantages
      - **Look for complicated rule-based software and see if 2.0 can come up with better software**
  - Assessing feasibility
    - The pyramid:
![]({{site.baseurl}}/assets/imgs/posts/full-stack/feasibility-ml.png)
    - How do you know how much data do you need?
      - Rule of thumb: *At least* **10,000** examples for DL
      - looking at SOTA implementations and seeing how much data they used for obtaining the results that they did
    - You can setup structure around your model that prevents it from making confident wrong prediction
    - Accuracy requirement scaling
![]({{site.baseurl}}/assets/imgs/posts/full-stack/accuracy-scale.png)
      - ML project costs tend to scale super-linearly in the accuracy requirement
      - You can make product design choices to reduce your accuracy cost
        - FB tag for faces, suggested. 
        - Designing collaborative AI blog post
    - Another heuristic for assessing feasibility:
      - Anything normal people can do in < 1 sec ML can do at scale and well
      - Not really a very good metric
    - Ask why your company cares about your problem: impact and feasibility
      - **Look for complicated rule-based software and see if 2.0 can come up with better software**
      - **Look for projects where cheap prediction will have a huge business impact**
  - Choosing metrics
    - Real world is messy, you care about lots of metrics
    - ML systems work best when optimizing for one metric
    - This means you need to combine multiple metrics
    - Metrics can and will change over time
    - How to combine metrics?
      - average/weighted average
      - threshold n-1 metrics and choose nth to drive
      - more complex/domain specific metrics: mean-average precision (mAP)
  - Choosing baselines

40:43