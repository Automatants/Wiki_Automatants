---
author: 'Louis De Oliveira'
date: '2021-12-16 (last update)'
description: ''
---
# Valeur d'action - Action Value

En [[Apprentissage par renforcement]], la valeur d'action $q_* (a)$ correspond à l'espérance de la récompense reçue en effectuant l'action a l'instant $t$.

$$ q_* (a) := \mathbb{E}[R_t | A_t =a]$$

En pratique, la valeur de $q_* (a)$ n'est pas connue et il faut donc l'estimer. On note $Q_t (a)$ l'estimation de $q_* (a)$ à l'instant $t$.

L'action qui maximise $Q_t (a)$ est appellée *greedy action*.

$$ A_t = \underset{a}{\mathrm{argmax}}\,  Q_t (a) $$

## Sélection de l'action suivante - méthodes par valeur d'action

Une méthode naturelle d'estimation de $Q_t (a)$ est de prendre la moyenne des récompenses reçues en choisissant l'action a. Cela revient a avoir la relation : 

$$Q_{n+1} = Q_n + \frac{1}{n} [R_n - Q_n]$$

qui est de la forme :

$$ NewEstimate \leftarrow OldEstimate + StepSize[Target - OldEstimate]$$

Une définition plus générale pour actualiser $Q_t (a)$ consiste a utiliser la relation précédente pour un pas constant $\alpha \in ]0,1]$. Ce qui revient a favoriser les actions récentes en "oubliant" exponentiellement les actions passées.

$$Q_{n+1} = Q_n + \alpha [R_n - Q_n]$$

Il reste cependant a choisir quelle action choisir à chaque étape :
- $\epsilon$ - greedy : On choisit une valeur $\epsilon \in [0,1]$ et on choisit alors l'action greedy avec une probabilité $\epsilon$ et une action au hasard avec une probabilité $1-\epsilon$.
- Optimistic Initial Values : On initialise $Q_1 (a)$  avec une valeur relativement élevée, et de choisir les actions a chaque itération de manière greedy. Cela permet d'explorer au départ, puis de se stabiliser sur une action.
- Upper-Confidence-Bound : Sachant qu'il y a toujours une incertitude sur la précision de nos estimation des valeurs d'action, nous avons quand même intérêt à explorer notre espace d'action. Contrairement a $\epsilon$ - greedy  qui choisit de manière uniforme, on favorise les actions dont la valeur estimée est la plus élevée compte-tenu de l'incertitude sur sa mesure. $$ A_t = \underset{a}{\mathrm{argmax}}\,  \left[ Q_t (a) + c\sqrt{\frac{\ln t}{N_t (a)}} \right]$$





