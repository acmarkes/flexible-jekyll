---
layout: post
title: Causal Inference - Understanding the Foundations and Assumptions
date: 2024-02-17 00:00:00 -0300
description: A small intro on causal inference for observational data
img: causal_intro.png
tags: [Statistics, Causality]
---

## **Title:**
Causal Inference: Understanding the Foundations and Assumptions

### **Introduction:**
In the realm of data analysis, distinguishing between causality and correlation is paramount. While correlation identifies relationships between variables, causality delves deeper into understanding the mechanisms behind these relationships. Causal inference, or causal modeling, seeks to bridge this gap by providing formal definitions of causal effects and delineating the assumptions necessary to infer causation from observational data. In this article, we'll explore the fundamental principles of causal inference, focusing on the key assumptions and methodologies involved in estimating causal effects from observational data.

### **Notations:**
Before delving into the intricacies of causal inference, it's crucial to establish some key notations:
- Treatment (**T**): Represents the intervention or action taken, such as receiving a flu vaccine.
- Outcome (**Y**): Denotes the result or response of interest, such as contracting the flu.
- Potential Outcome (**Y**<sup>t</sup>): Refers to the outcome that would be observed under a specific treatment condition (e.g., receiving the flu vaccine or not).
- Counterfactuals: Represent the hypothetical outcomes that would have occurred under different treatment scenarios.


### **The Potential Outcomes Framework: Conceptualizing Causality**

One powerful framework that addresses the fundamental problem of causal inference is the potential outcomes framework, also known as the counterfactual framework or Rubin Causal Model (RCM). Developed by Donald Rubin in the 1970s, this framework provides a systematic way to define and estimate causal effects in observational studies and experiments.

At its core, the potential outcomes framework revolves around the notion of counterfactuals, which are hypothetical outcomes that would have occurred under different treatment conditions. In any given situation where a treatment or intervention is applied to individuals, each person has a potential outcome associated with each possible treatment level. For example, if we are studying the effectiveness of a new medication, the potential outcome for an individual who receives the medication would be their health outcome if they took the medication, while the potential outcome for the same individual under no medication would be their health outcome if they did not take the medication.

The framework formalizes this concept by defining potential outcomes as random variables denoted as Y<sup>1</sup> and Y<sup>0</sup>, where:

- Y<sup>1</sup> represents the potential outcome under the treatment condition (e.g., taking the medication).
- Y<sup>0</sup> represents the potential outcome under the control condition (e.g., not taking the medication).

### **The Fundamental Problem of Causal Inference:**
The core challenge in causal inference lies in the inability to observe multiple outcomes for the same individual. However, by making certain assumptions, we can estimate average causal effects on a population level. The average causal effect is defined as the difference in outcomes between treated and untreated individuals.

### **How the Framework Solves the Problem:**

The potential outcomes framework offers a structured approach to navigating the challenges posed by the fundamental problem of causal inference. By explicitly defining potential outcomes and acknowledging the existence of counterfactual scenarios, researchers can conceptually disentangle causation from association.

Through this framework, researchers can:

- **Define Causal Effects:** The framework provides formal definitions of causal effects, allowing researchers to precisely quantify the impact of treatments or interventions on outcomes.
- **Make Causal Inferences:** By comparing observed outcomes with counterfactual outcomes, researchers can estimate causal effects even in the absence of randomized controlled trials.
- **Formulate Assumptions:** The framework relies on assumptions such as SUTVA and Ignorability to enable causal inference. These assumptions guide researchers in making valid inferences about causal relationships from observational data.

In essence, the potential outcomes framework offers a structured way to reason about causality and estimate causal effects, providing a solid foundation for causal inference in diverse research settings. By embracing the concept of counterfactuals and leveraging observed data, researchers can gain valuable insights into causal relationships and inform decision-making processes in fields ranging from healthcare to public policy.

### **Assumptions in Causal Inference:**
To estimate causal effects from observational data, several assumptions must be satisfied:

1. **SUTVA (Stable Unit Treatment Value Assumption):** SUTVA posits that the treatment assigned to one unit does not influence the potential outcomes of other units. This assumption ensures that each unit's outcome is solely determined by its own treatment assignment.
  
2. **Positivity (aka Overlap or Common Support):** Positivity asserts that every unit in the population has a non-zero probability of receiving each treatment level. Considering a single covariate X=x, formally we have that P(T=t | X=x) > 0 for all values of X. Imagine your population is comprised of 500 people aged 30 to 80 and you want to understand the impact of a treatment only available to people aged 50 or more.  Everyone under that age threshold has no chance to receive the treatment and it won't be possible to extrapolate their behaviour if they had received the treatment. This condition is essential for estimating causal effects across all subgroups of the population.
  
3. **Ignorability (Exchangeability):** Ignorability assumes that, conditional on observed covariates, the treatment assignment is independent of potential outcomes. This assumption allows researchers to control for confounding variables and isolate the causal effect of the treatment.
  
4. **Consistency:** Consistency dictates that as the sample size increases, estimates of treatment effects converge to the true treatment effect. This ensures the reliability and accuracy of estimated causal effects with larger sample sizes.

### **Conclusion:**
Causal inference is a powerful tool for uncovering causal relationships from observational data. By understanding the foundational assumptions and methodologies in causal inference, researchers can derive meaningful insights into the causal mechanisms underlying observed phenomena. However, it's crucial to acknowledge the limitations and potential biases inherent in causal inference and employ robust sensitivity analyses to assess the robustness of conclusions. As data-driven decision-making continues to gain prominence, a solid understanding of causal inference principles is indispensable for extracting actionable insights and informing evidence-based policies and interventions.
