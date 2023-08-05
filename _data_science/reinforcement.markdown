---
layout: page
title: Reinforcement Learning
permalink: /data_science/reinforcement
---
The reinforcement learning hypothesis, as put forward by [Michael Littman](https://en.wikipedia.org/wiki/Michael_L._Littman), states that *"Intelligent behavior arises from the actions of an individual seeking to maximize its received reward signals in a complex and changing world."* A fun-to-watch example of RL in robotics is shown below (see [Geijtenbeek, et al 2013](https://www.youtube.com/watch?v=pgaEE27nsQw)), where synthetic (digital) bipedal creatures learn over many generations to walk. One thing notable about this example is that the synthetic creatures used are actually running advanced physics simulations of muscle-based locomotion - the knowledge gained from these simulations can then be transferred to real robots walking in the real world.

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

In this context, an environment can be anything. For a water-resources example, consider the control of a reservoir...
## Why Reinforcement Learning?
The reinforcement learning (RL) paradigm is unique in its focus on learning *optimal actions* to be taken by an agent operating a system *over time*. 

## References
I've found the following references very helpful in gaining an understanding of reinforcement learning concepts.

### Primary
Indispensable references: 

-  [Sutton and Barto](http://incompleteideas.net/book/the-book-2nd.html) maintain the authoritative text on the topic, and generously make a PDF version of their book freely available.
-  University of Alberta's [reinforcement learning specialization](https://www.coursera.org/specializations/reinforcement-learning) requires a Coursera subscription, but is well worth the cost for a professional data scientist, and is a great hands-on complement to the Sutton and Barto text. 

### Secondary
Compelling examples and research applications:

-  Google DeepMind's [autonomous data center cooling system](https://www.deepmind.com/blog/safety-first-ai-for-autonomous-data-centre-cooling-and-industrial-control) is a great example of applied RL for industrial control systems
-  [Seo, et al, 2021](https://ieeexplore.ieee.org/abstract/document/9474446) provide a compelling use case of applied deep reinforcement learning (DRL) to optimize pump scheduling at a wastewater treatment plant in South Korea.