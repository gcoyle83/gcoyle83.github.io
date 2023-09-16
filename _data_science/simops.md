---
layout: page
title: Simulation Modeling Operations (SimOps)
permalink: /concepts/simops
---
Whether physics-based, domain-knowledge-driven process models or wholly empirical data-driven models are used (or a combination of the two) for environmental system evaluation, these models become stale as new data becomes available. ML Engineering (or MLOps) combines machine learning model development with DevOps principles for continuous improvement/integration and continuous delivery/deployment (CI/CD). 

As discussed in [Pan, et al., 2019](), the related concept of *SimOps* applies the same concepts to the management of simulation models. Here the term *simulation models* refers to the use of numerical algorithms for simulation of some system of interest. Traditionally, these simulators are systems of partial or ordinary differential equations that describe the governing equations of the system. The development of these models has traditionally been very domain-specific, though general principles are widely applicable and the field of "numerical methods" for efficiently implementing algebraic approximations to the solution of the system (through integration and iterative convergence routines).

However, it seems that the practice of managing the lifecycle of these models has not been systematically developed in a similar fashion. Most of the research in the area focuses on improved numerical algorithms for faster approximation or reduced uncertainty. The process of systematically managing model versions, calibration efforts, data assimilation, prediction, scenario and uncertainty analysis, and so on, appears to be *ad hoc* and does not benefit from a discipline parallel to MLOps.

It is worth recalling (from the [MLOps concept overview]()) that MLOps was originally organized around the concept of applying the principles of DevOps to machine learning systems. [Sculley]() identified several ways in which ML systems differed from "traditoinal" software systems, namely: that such systems are dependent on (continually updating) data, ...

Consider how these concerns have direct counterparts in simulation modeling:
-  Any simulator is conditional on a fixed set of calibration parameters, which are selected through some iterative process to improve the fit of the model output to available observed data;
-  As new data are available, it is desirable (if not common) to regularly assimilate this data into the model to improve the calibration and uncertainty estimation;
-  At best, the re-calibration/data-assimilation procedures result in updated probability distributions for the calibration parameters. More often, they result in different discrete selections for parameter values;
-  Any re-calibrated model is therefore a different realization of the system of interest and should be considered a new version of the model - the same data from a previous period would not generate the same output as before;

Fortunately, it seems that most - if not all - of the requirements of managing the operation/application of simulation models match closely with that of ML models. Therefore, the field of simulation modeling can directly benefit from (and inform) the development of MLOps.

All that said, there is a related and overlapping practice area sometimes referred to as *ModelOps* that claims a broader scope than MLOps in the sense that its goal is to manage "all models" - from spreadsheet rules to advanced PDE simulators and DNNs - throughout an enterprise. This is certainly an admirable goal and deserving of further review...

Topics to be considered:
-  [Technical debt]()
-  [MLOps maturity model(s)]()
-  [Standards development]()
-  [Data drift]()
-  [Concept drift]()
-  [Model tracking systems]()
-  [Containerization]()
-  [Distributed computing]()
-  Connection with [SimOps](https://arxiv.org/pdf/2111.06223.pdf)
 
# References and Resources
Are compiled for this section here.

## Helpful resources
...

## References
Chapra, SC. Numerical Methods for Engineers. McGraw-Hill. 20xx.