---
layout: page
title: Machine Learning Engineering and Operations (MLOps)
permalink: /concepts/mlops
---
Whether physics-based, domain-knowledge-driven process models or wholly empirical data-driven models are used (or a combination of the two) for environmental system evaluation, these models become stale as new data becomes available. ML Engineering (or MLOps) combines machine learning model development with DevOps principles for continuous improvement/integration and continuous delivery/deployment (CI/CD). This is a relatively new field of practice and study, having just emerged in the past decade at tech flagships like Google, Facebook and Amazon. 

In this section I'll collect the best resources I find in my efforts to understand the objectives and requirements of MLOps, and begin to outline my own take on the subject as it intersects with the more traditional model development and management lifecycle of water-quality and environmental infrastructure modeling.

Topics to be considered:
-  [Technical debt]()
-  [MLOps maturity model(s)]()
-  [Standards development]()
-  [Data drift]()
-  [Concept drift]()
-  [Model tracking systems]()
-  [Containerization]()
-  [Distributed computing]()

## Technical debt
In a few words:

> *"Developing and deploying ML systems is relatively fast and cheap, but maintaining them over time is difficult and expensive."*

This leading quote from Google Research's 2015 paper [*Hidden Technical Debt in Machine Learning Systems*](https://papers.nips.cc/paper/2015/file/86df7dcfd896fcaf2674f757a2463eba-Paper.pdf) (Scully, et al., 2015) conveys the central concept well. Technical debt (Cunningham, 1992) more specifically is a not-so-subtle metaphor relating the maintenance costs of software projects to fiscal debt of other capital investments (forgive me, bankers, I know not what I do). To quote Google again: 

> "Technical debt may be paid down by refactoring code, improving unit tests, deleting dead code, reducing dependencies, tightening APIs, and improving documentation - the goal is *not* to add new functionality, but to enable future improvements, reduce errors, and improve maintainability... we argue that **ML systems have a special capacity for incurring technical debt, because they have all of the maintenance problems of traditional code plus an additional set of ML-specific issues.**" 

-  Complex models erode boundaries
    -  entanglement
    -  correction cascades
    -  undeclared consumers
-  Data dependencies cost more than code dependencies
    -  unstable data dependencies
    -  underutilized data dependencies (legacy features, bundled features, $\epsilon$-features, correlated features)
    -  static analysis of data dependencies
-  Feedback loops
    -  direct
    -  hidden
-  ML-system anti-patterns
    -  glue code
    -  pipeline jungles
    -  dead experimental codepaths
    -  abstraction debt
    -  common smells (plain-old-data, multiple-language, prototype)
-  Configuration debt
-  Changes in the external world
    -  fixed thresholds in dynamic systems
    -  monitoring and testing (prediction bias, action limits, upstream producers)
-  Other areas of ML-related debt
    -  data testing debt
    -  reproducibility debt
    -  process management debt
    -  cultural debt
-  Conclusions (from the paper)

**Is it worth it?**

The issue as stated is compelling: after all, are we building ML systems for the sake of ML systems? Well, certainly some are, but it isn't the dominant reason for building them (or shouldn't be). Certainly not in the domain of civil infrastructure. The question glaring from beneath this statement, then, is: *why are we continuing to build ML systems if they are more difficult and expensive to maintain than other reasonable solutions?*


# References and Resources
Are compiled for this section here.

## Helpful resources
My first resource for getting a handle on MLOps was Andrew Ng's online certificate program for MLOps. I highly recommend it, and many of the particular technical references discussed throughout this section were brought to my attention in that course. 
## References
