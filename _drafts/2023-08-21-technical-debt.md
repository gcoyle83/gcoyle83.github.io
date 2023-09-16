---
layout: post
title:  "Reading notes - hidden technical debt in ML systems"
---

In this post I'll be reviewing the main concepts presented in Google Research's 2015 paper [*Hidden Technical Debt in Machine Learning Systems*](https://papers.nips.cc/paper/2015/file/86df7dcfd896fcaf2674f757a2463eba-Paper.pdf) (Scully, et al., 2015). 

## Technical debt
In a few words:

> *"Developing and deploying ML systems is relatively fast and cheap, but maintaining them over time is difficult and expensive."*

This leading quote conveys the central concept well. Technical debt (Cunningham, 1992) more specifically is a not-so-subtle metaphor relating the maintenance costs of software projects to fiscal debt of other capital investments. To quote Google again: 

> "Technical debt may be paid down by refactoring code, improving unit tests, deleting dead code, reducing dependencies, tightening APIs, and improving documentation - the goal is *not* to add new functionality, but to enable future improvements, reduce errors, and improve maintainability... we argue that **ML systems have a special capacity for incurring technical debt, because they have all of the maintenance problems of traditional code plus an additional set of ML-specific issues.**" 

-  Complex models erode boundaries
    -  entanglement
		-  CACE - Changing anything changes everything
		-  Example, serving ensembles, improving an individual component model may degrade system accuracy if residuals are more strongly correlated with other component models

    -  correction cascades
		-  y= Fa(x)
		-  y' = Fa(x) + e(x) = Fb(x)
		-  y'' = Fb(x) + e(x) = Fc(x)
		-  "Once in place, a correction cascade can create an improvement deadlock, as improving the accuracy of any individual component actually leads to system-level detriments...
		-  "Augment [Fa(x)] to learn the corrections directly within the same model by ading features to distinguish among cases, or [otherwise] accept the cost of creating a separate model for [y']."
    -  undeclared consumers 
		- without access controls, consumers of model output may be 'undeclared', silently using the output of a given model as an input to another system. 
		-  Synonymous with 'visibility debt' in traditional SoftEng. 
		-  Can contribute directly to feedback (self-referential) loops in some cases

-  [HERE!] Data dependencies cost more than code dependencies
    -  unstable data dependencies
    -  underutilized data dependencies (legacy features, bundled features, $\eps$-features, correlated features)
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

**When is it worth it?**

The issue as stated is compelling: after all, are we building ML systems for the sake of ML systems? Well, certainly some are, but it isn't the dominant reason for building them (or shouldn't be). Certainly not in the domain of civil infrastructure. The question glaring from beneath this statement, then, is: *why are we continuing to build ML systems if they are more difficult and expensive to maintain than other reasonable solutions?*