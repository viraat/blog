## Delayed impact of fair machine learning
tags: [fairness, reading-group]
- Most fair ML has focussed on static setting without looking into how decisions affect the underlying population with time
- Show that common fairness criteria do not promote improvement for the population over time, and in certain cases and under certain conditions can result in harm
- Result: important to consider temporal modeling in evaluation of fairness criteria
- use the example of a bank giving loans to people from two groups based on their credit scores
  - one-step feedback where the credit scores of individuals increases if they pay back the loan and decreases if not
  - overall group improvement is when the mean credit score of the group increases 
    - stagnation is when there is no improvement
    - harm is when there is decrease of score
    - relative harm is when the increase in score is not as much compared to the unconstrained (no fairness criteria) scenario
  - they measure group improvement for three different scenarios:
    - unconstrained bank: maximize profit
    - demographic parity: lend to both groups at equal rate
    - equality of opportunity: equalize the true positive rates between the two groups (equal lending rate in both groups to people who repay their loans)
- contributions:
  - show that both fairness criteria can lead to all possible outcomes
  - outcome curve which can visually show outcomes
  - real-life data experiments in line with theory
  - alternatives to hard fairness criteria: optimize for group score instead of fairness
![outcome-curve](week30-delayed-fairness-1.png)