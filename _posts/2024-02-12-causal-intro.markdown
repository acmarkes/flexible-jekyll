---
layout: post
title: Causal Inference - Understanding the Foundations and Assumptions
date: 2024-02-12 00:00:00 -0300
description: A small intro on causal inference for observational data
img: heartd.jpg
tags: [Statistics, Causality]
---

### **Introduction**
In the realm of data analysis, distinguishing between causality and correlation is paramount. While correlation identifies relationships between variables, causality delves deeper into understanding the mechanisms behind these relationships. Causal inference, or causal modeling, seeks to bridge this gap by providing formal definitions of causal effects and delineating the assumptions necessary to infer causation from observational data. In this article, we'll explore the fundamental principles of causal inference, focusing on the key assumptions and methodologies involved in estimating causal effects from observational data.

### **Notations**
Before delving into the intricacies of causal inference, it's crucial to establish some key notations:
- Treatment (**A**): Represents the intervention or action taken, such as receiving a flu vaccine.
- Outcome (**Y**): Denotes the result or response of interest, such as contracting the flu.
- Potential Outcome (**Y**<sup>a</sup>): Refers to the outcome that would be observed under a specific treatment condition (e.g., receiving the flu vaccine or not).
- Counterfactuals: Represent the hypothetical outcomes that would have occurred under different treatment scenarios.

### **The Fundamental Problem of Causal Inference**
The core challenge in causal inference lies in the inability to observe multiple outcomes for the same individual. However, by making certain assumptions, we can estimate average causal effects on a population level. The average causal effect is defined as the difference in outcomes between treated and untreated individuals.

### **Assumptions in Causal Inference**
To estimate causal effects from observational data, several assumptions must be satisfied:

1. **SUTVA (Stable Unit Treatment Value Assumption):** SUTVA posits that the treatment assigned to one unit does not influence the potential outcomes of other units. This assumption ensures that each unit's outcome is solely determined by its own treatment assignment.
  
2. **Positivity (Overlap):** Positivity asserts that every unit in the population has a non-zero probability of receiving each treatment level. This condition is essential for estimating causal effects across all subgroups of the population.
  
3. **Ignorability (Exchangeability):** Ignorability assumes that, conditional on observed covariates, the treatment assignment is independent of potential outcomes. This assumption allows researchers to control for confounding variables and isolate the causal effect of the treatment.
  
4. **Consistency:** Consistency dictates that as the sample size increases, estimates of treatment effects converge to the true treatment effect. This ensures the reliability and accuracy of estimated causal effects with larger sample sizes.

### **Conclusion**
Causal inference is a powerful tool for uncovering causal relationships from observational data. By understanding the foundational assumptions and methodologies in causal inference, researchers can derive meaningful insights into the causal mechanisms underlying observed phenomena. However, it's crucial to acknowledge the limitations and potential biases inherent in causal inference and employ robust sensitivity analyses to assess the robustness of conclusions. As data-driven decision-making continues to gain prominence, a solid understanding of causal inference principles is indispensable for extracting actionable insights and informing evidence-based policies and interventions.
