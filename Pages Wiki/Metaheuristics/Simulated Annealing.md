---
author: 'Raffael BDL'
date: '2021-12-17'
description: 'Simulated Annealing'
---
# Simulated Annealing
Simulated Annealing is a [[What Are Metaheuristics|metaheuristic]] method for global optimization.
It is particulary useful if finding a near-maximum global point is more important than finding an exact maximum local point.

#### Inspiration
Simulated Annealing is inspired by how metal is heated and cooled to alter its properties.

## How to use Simulated Annealing (SA)
![[Hill_Climbing_with_Simulated_Annealing.gif]]

SA requires four functions :
* An energy function, that will be minimized. The analogy with physics is that one wants to minimize the energy of the internal state of their system.
* A neighborhood function, that picks a random state that is close to the previous one (close by distance for instance).
* A temperature function, that will represents the heating and cooling of the SA.
* A probability function, like Boltzmann probability for instance.

Python code for annealing :
```Python
s = s0
for k in range(k_max):
	T = temperature(k)
	s_new = neighborhood(s)
	if P(E(s), E(s_new), T) >= random(0,1):
		s = s_new
```

##### Boltzmann probability
The idea is that the hotter it is the easier it is to reach high level energy. Conversely, when the temperature is too low, the system cannot reach states with greater energy. It is a good way to implement exploration for SA.

$$P(E_{cur},E_{chal},T)=exp(\frac{E_{cur}-E_{chal}}{T})$$

where $E_{cur}$ is the current state energy, $E_{chal}$ is the challenger state energy, and $T$ is the temperature.

Here, if $E_{cur} >= E_{chal}$, $P>1$ and therefore if the code the condition will always be verified. Nonetheless, even if $E_{cur} < E_{chal}$ there is still a chance that the state will change.

### Famous applications of Simulated Annealing
The most famous application of SA is certainly the *Travelling Salesman Problem*. Given a set of cities and the distances between each pair of cities, what is the shortest distance to visit all the cities. This problem is NP-Hard and its solution must be global, which makes SA really potent in this case.

Many problems are analog to this one, once the functions like *energy* and *neighborhood* are well-defined.