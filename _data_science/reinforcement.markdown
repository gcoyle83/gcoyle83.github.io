---
layout: page
title: Reinforcement Learning
permalink: /data_science/reinforcement
---
The reinforcement learning hypothesis, as put forward by [Michael Littman](https://en.wikipedia.org/wiki/Michael_L._Littman), states that *"Intelligent behavior arises from the actions of an individual seeking to maximize its received reward signals in a complex and changing world."* 

A fun-to-watch example of RL in robotics is shown below (see [Geijtenbeek, et al., 2013](https://www.goatstream.com/research/papers/SA2013/)), where synthetic (digital) bipedal creatures learn over many generations to walk. One thing notable about this example is that the synthetic creatures used are actually running advanced physics simulations of muscle-based locomotion - the knowledge gained from these simulations can then be transferred to real robots walking in the real world.

<center>
<video width="560" height="315" autoplay controls loop muted>
  <source src="/assets/images/bipedal.mp4" type="video/mp4" alt="Robots trained to walk with RL">
</video>
</center>

Robotics may be a fun example of RL, but the reinforcement learning task has been stated more generally (although not exclusively) as a Markov Decision Process (MDP). 

<center>
	<figure>
		<img src="/assets/images/rl_mdp_01.png"
			 width="500"
			 alt="Markov Decision Process">
		<figcaption>The Markov Decision Process (MDP) abstraction.</figcaption>
	</figure>
</center>

In a MDP, an *agent* selects among a possible set of *actions* conditional on an observed *state* from the agent's *environment*. The agent's goal is to select the action that maximizes its total *return over time*, where the return is defined as a function of incremental *rewards* received after taking actions in the environment. 

In this context, an environment can be anything: a flat terrain with a constant gravitational field as in the bipedal locomotion example above, a Go board as in the case of DeepMind's [AlphaGo](https://en.wikipedia.org/wiki/AlphaGo), or a data center as in the case of DeepMind's real-world [RL-powered industrial cooling system](https://www.deepmind.com/blog/safety-first-ai-for-autonomous-data-centre-cooling-and-industrial-control). 

A number of interesting water-resources examples have appeared in recent literature, and I'll do my best to summarize their contributions here:

### Reinforcement learning for real-time control of stormwater management systems
Reinforcement learning for RTC in stormwater management has been an active area of research lately, most notably at Prof. Jonathan Goodall's [Hydroinformatics Research Group](https://uvahydroinformatics.org/) in the Link Lab at the University of Virginia. Also worth noting is the occasional collaboration between Goodall's team and Xylem. 

-  [Saliba, et al., 2020](https://www.mdpi.com/2073-4441/12/11/3222) framed the problem of real-time control (RTC) of stormwater infrastructure (retrofitted) as a RL problem. Compared against passive systems (no controls), the RL implementations reduced flooding volume by 70.5% on average. This work used a simplistic simulated environment based in SWMM5. Introduces difficulties of dealing with uncertain data inputs (imperfect state observations). 

-  [Wang, et al., 2020](https://www.researchgate.net/profile/Cheng-Wang-109/publication/343426754_Smart_Stormwater_Control_Systems_A_Reinforcement_Learning_Approach/links/645d0691f43b8a29ba44dfad/Smart-Stormwater-Control-Systems-A-Reinforcement-Learning-Approach.pdf) - a simple conceptual stormwater system is simulated with SWMM5, using the [`pyswmm`](https://github.com/OpenWaterAnalytics/pyswmm) package for interactive control of the model by the RL agent. A reward function designed around an expert baseline control policy is introduced to limit exploration during dry periods. The actor-critic method Deep Deterministic Policy Gradient (DDPG) is used. While several simplifying assumptions are made, this paper helped to depict the potential of applying RL to active stormwater control systems with the single objective of flood mitigation.

-  [Bowes, et al., 2020](https://iwaponline.com/jh/article/23/3/529/77759/Flood-mitigation-in-coastal-urban-catchments-using) continued this line of inquiry on hypothetical urban catchments, but extended the baseline comparison to include industry-standard rule-based control (RBC), as well as model predictive control with genetic algorithm optimization (MPC-GA). RL was shown to quickly outperform RBC, while performing comparably with MPC-GA but at significantly less computational expense. 

-  [Bowes, et al., 2022](https://par.nsf.gov/servlets/purl/10340922) - This work used SWMM5 simulations of real catchments in Norfolk, VA, with tidal influence and multiobjective optimization to mitigate flooding and maximize sediment capture.

## Why Reinforcement Learning?
It's reasonable to ask why RL should be used at all. Why not just program a stormwater system with predefined rules about how to operate? The reinforcement learning (RL) paradigm is unique in its focus on learning *optimal actions* to be taken by an agent operating a system *over time*. DeepMind's data-center cooling application offers a compelling example: "...the AI [learned] to take advantage of winter conditions and produce colder-than-normal water, which reduces the energy required for cooling within the data center. Rules don't get better over time, but AI does."

*More to come.*

## References
I've found the following references very helpful in gaining an understanding of reinforcement learning concepts.

### Primary
Indispensable references: 

-  [Sutton and Barto](http://incompleteideas.net/book/the-book-2nd.html) maintain the authoritative text on the topic, and generously make a PDF version of their book freely available.
-  University of Alberta's [reinforcement learning specialization](https://www.coursera.org/specializations/reinforcement-learning) requires a Coursera subscription, but is well worth the cost for a professional data scientist, and is a great hands-on complement to the Sutton and Barto text. 

### Secondary/Application Specific
Compelling examples and research applications - many of these are discussed in context above, but are also listed here for completeness:

-  [UVA Hydroinformatics](https://uvahydroinformatics.org/) lab and [GitHub repository](https://github.com/uva-hydroinformatics)
-  Google DeepMind's [autonomous data center cooling system](https://www.deepmind.com/blog/safety-first-ai-for-autonomous-data-centre-cooling-and-industrial-control) is a great example of applied RL for industrial control systems
-  [Seo, et al, 2021](https://ieeexplore.ieee.org/abstract/document/9474446) provide a compelling use case of applied deep reinforcement learning (DRL) to optimize pump scheduling at a wastewater treatment plant in South Korea.