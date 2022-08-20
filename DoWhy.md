# DoWhy:

[path to library](https://github.com/py-why/dowhy#using-econml-and-causalml-estimation-methods-in-dowhy)

This tool allows to explore couterfactual prediction: when one behavior changes, what else changes as a result?

**These what if tasks are fundamentally harder that forecasting**

- Causal Analysis add human knowledge as constraints
- Machine learning expands our ability to map data relationship 

## Causal Analysis Pipeline:

- Causal Discovery: Find appropiate causal graph (DECI)
- Causal Identification: Derive causal effect expression (DoWhy/DECI)
- Causal Estimation: Quantify causal effects (EconML/DECI)
- Causal Validation: Validating the effect estimate (DoWhy)

Inter-operable: Focus on different tasks, but all are inter-operable with each other. Together, they provide an end-to-end pipeline for causal inference. 

### User-Example:
-An economist who knows the confounders and want to estimate ATE.(for this EconML is appropiate)

- Domain expert who knows the full causal relationship and want to estimate ATE. He don't know the counfounders between the variables. You can use DoWhy with EconML. EconML will provide with multiple causal estimation methods, as DoWhy will provide multiple identification and validation methods.

- General data scientist or decision maker who have data and want a method to provide both relationship insight and causal quantities (such as CATE) for decision making. He can use DECI as an end to end causal inference which canbe also used for discovery or estimation alone. He can use EconML to provide for multiple causal estimation methods. DoWhy for identification and validation methods. And using all of them together to provide a multiple end to end causal inference methods. 

## Dowhy

[path to library](https://github.com/py-why/dowhy#using-econml-and-causalml-estimation-methods-in-dowhy)

### Updates: Effect Inference
- Complete identification algorithm
- More powerfull validation tests:
  - Conditional independence tests to check validity of graph
  - Robustness scores based on partial R2
  - (Upcomming) Non-parametric robustness scores for double ML
- Extensibility:
  - Support for custom external estimators from any library
  - Support for graphs generated from DAGitty
- Case Studies: Targetting messages to people who are likely to benefit the most:
  - Split treatment analysis to rank heterogeneous causal effects

### Updates: New causal tasks:
- For causal estimation:
  - Causal Effect Inference
  - Causal Prediction (Out-of-distribution prediction)

## EconML: 

[path to library](https://github.com/microsoft/econml)

### Updates: New Usability
- Rscorer:
  - New universal scorer to inform choice across causal models in library
  - Different causal models (DML, meta learners) have qualitatively different performance on different samples.
- Beyond python:
  - Responsible AI dashboard in Azure has new effect visualization
  - ShowWhy wraps DoWhy and EconML in a guided interface to form causal analysis

## DECI (Deep End-to-end Causal Inference)

[path to library](https://github.com/microsoft/project-azua)
[path to library 2](https://github.com/microsoft/causica)

### Option 1: Stacking
1. Cauasal Discovery
2. Causal Identification
3. Causal Estimation

This approach have some issues, because the discoverys of graph discovery or the format of data might bring some problems. For this reason is not always the best approach to apply all of them by stacking.

## Option 2: Joint Modeling:

Using DECI with only observation data input, we can produce the causal graph, the functional relationships, the treatment effect and finally the recomend decisions. 

### Key Features of DECI
1. When it comes to cause discovery, we can perform multiple methods of graph learning (with multiple variables and observations)
2. How to deal with graph ambiguity, to solve this you can generate a probability distribution of all the posible graphs that can explain the data. This allows to take account the uncertainty of the graph generated.
3. Efficient functional learning, we can learn simultaneously all the relationships of variables when we are learning from graphs themselves. 
4. Efficient handling of missing & mixed-type data.