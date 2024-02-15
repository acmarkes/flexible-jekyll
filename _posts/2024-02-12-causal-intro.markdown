---
layout: post
title: Causal Inference - Understanding the Foundations
date: 2024-02-11 00:00:00 -0300
description: A small intro on causal inference for observational data
img: causal_intro.png
tags: [Statistics, Causality]
---


## **Introduction:**
Anyone working with data has heard the maxim "correlation is not causation" but not everyone finds out what causation actually is and how to measure it. While correlation identifies relationships between variables, causality delves deeper into understanding the mechanisms behind these relationships, including the effects of certain variables. Causal inference provides formal definitions of causal effects and the assumptions necessary to infer causation from observational data, as well as rules about what variables to control for and sensitivity analysis to measure the impact of a violated assumption. 

In this brief article, we'll explore the fundamental principles of causal inference and introduce a framework and its key assumptions to understand and estimate causal effects from observational data.

## **Conceptualizing Causality**

Causal effects are best understood as the consequences of manipulations or interventions on certain variables. However, it's crucial to ensure that the variables chosen for analysis are manipulable—that is, they can be subject to interventions or treatments.

Consider the example: "What is the effect of BMI on heart disease?" In this scenario, BMI serves as the variable of interest, but it's influenced by various factors such as diet, medication, exercise, genetic predisposition, among others. These factors can confound the relationship between BMI and heart disease, making it challenging to isolate the true causal effect. Weight, for instance, is not a manipulable variable since it cannot be directly intervened upon. To address this, we can identify a manipulable variable that serves as a proxy for BMI, such as whether an individual started a ketogenic diet or not.

By selecting manipulable variables and carefully defining causal relationships, we can better understand the causal effects of the treatment and avoid confounding factors. But when defining causal relationships we encounter a fundamental issue in causal inference: the inability to observe multiple outcomes for the same individual. In our example, the same person can't start and not start the diet.

## **The Potential Outcomes Framework**

One powerful framework that addresses the fundamental problem of causal inference is the potential outcomes framework. Developed by Donald Rubin in the 1970s, this framework provides a systematic way to define and estimate causal effects in observational studies and experiments.

At its core, the potential outcomes framework revolves around the notion of counterfactuals. In any given situation before a treatment or intervention is applied to individuals, each person has a potential outcome associated with each possible treatment level. 

Say we are studying the effects of a flu vaccine. The potential outcome for an individual who receives the vaccine could be if they got the flu within 6 months, while the potential outcome for the same individual without the vaccine would be if they got the flu within 6 months. After the treatment we'd have the actual outcome for the person and our counterfactual would be the other potential outcome. 

By explicitly defining potential outcomes, acknowledging the existence of counterfactual scenarios and relying on some assumptions that will allow us to make valid inferences about causal relationships from observational, the potential outcomes framework can be used to disentangle causation from association and to estimate average causal effects in our population.

### **Notations:**

Before delving any deeper, let's formalize some ideas:

#### Treatment (**T**): 
Represents the intervention or action taken, such as receiving a flu vaccine.
  
#### Outcome (**Y**): 
Denotes the result or response of interest, such as contracting the flu within 6 months of taking the vaccine.
  
#### Potential Outcome (**Y**<sup>t</sup> or **Y**|T=t): 
Refers to the outcome that would be observed under a specific treatment condition. We have two possible outcomes: **Y**<sup>0</sup> if they didn't receive the vaccine, **Y**<sup>1</sup> if they did).
  
#### Counterfactual: 
Represent the hypothetical outcomes that would have occurred under different treatment scenarios. If T=1 then **Y**<sup>1</sup> is our outcome and **Y**<sup>0</sup> is our counterfactual).
  
#### Covariate (**X**): 
Refers to variables that aren't affected by the treatment, like the age of the person receiving the vaccine or if they took it previously.
  
#### Confounder: 
A covariate that affects both outcome and treatment. Older people are at a higher risk if they get the flu, which might influence them to look for the treatment more than their younger counterparts


## **Assumptions in Causal Inference:**
To estimate causal effects from observational data, several assumptions must be satisfied:

#### **SUTVA (Stable Unit Treatment Value Assumption):**

The treatment assigned to one unit (individual, subject, etc) does not influence the potential outcomes of other units. 
This assumption can be difficult to confirm when you have interacting individuals. For example, if someone in a house decides to start dieting, other members of the household might feel inclined to do the same. SUTVA ensures that each unit's outcome is solely determined by its own treatment assignment.

#### **Ignorability (Exchangeability):**

The treatment assignment should be independent of potential outcomes when conditioning on observed covariates. That means that every covariate X that affects both the treatment T and the outcome Y are observed and can be controlled for. This type of covariate is known as a confounder, so remember: no unmeasured confounders. 

#### **Positivity (aka Overlap or Common Support):**

Positivity asserts that every unit in the population has a non-zero probability of receiving each treatment level. Considering a single covariate X=x, formally we have that P(T=t | X=x) > 0 for all values of X. Imagine your population is comprised of 500 people aged 30 to 80 and you want to understand the impact of a treatment only available to people aged 50 or more.  Everyone under that age threshold has no chance to receive the treatment and it won't be possible to extrapolate their behaviour as if they had received the treatment. This condition is essential for estimating causal effects across all subgroups of the population.

#### **Consistency:**
Last but not least: there should be no hidden versions of treatment. If the treatment is to receive welfare payments, the individual either receives it or doesn't. If the treatment is getting a prize, there should be no consolation prizes for those that didn't get one. Define your treatments well and make sure you know all their possibilities. 

## **Conclusion:**

Understanding causality is paramount for making informed decisions based on data. While correlation can identify relationships between variables, causality enables a deeper comprehension of the mechanisms behind these relationships and the effects of specific interventions or treatments. In this article, we explored some foundational concepts of causal inference, as well as the potential outcomes framework. 

Leveraging the ideas of the framework allows us to compare observed outcomes with hypothetical outcomes under different treatment scenarios. We also defined some notations for these ideas and explained the key assumptions essential for estimating causal effects from observational data. 

In the next part of this series, we will delve into the mathematical nitty-gritty of these concepts. Stay tuned.

###### Sources:

Pearl, J., Glymour, M., Jewell, N. (2019) Causal Inference in Statistics: A Primer. John Wiley & Sons

Molak, A. (2023). Causal Inference and Discovery in Python. Packt Publishing.

Holland, P. (1986). Statistics and Causal Inference. Journal of the American Statistical Association, Vol. 81, No. 396 (Dec., 1986), pp. 945-960. American Statistical Association.
