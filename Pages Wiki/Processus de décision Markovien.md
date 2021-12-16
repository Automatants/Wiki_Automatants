---
author: 'Louis De Oliveira'
date: '2021-12-16 (last update)'
description: ''
---
# Processus de décision Markovien

Un processus de décision markovien (en anglais Markov decision process, MDP) est un modèle stochastique où un agent prend des décisions et où les résultats de ses actions sont aléatoires. Les MDPs sont utilisés pour étudier des problèmes d'optimisation à l'aide d'algorithmes de programmation dynamique ou d'[[Apprentissage par renforcement]].

Dans ce cadre nous pouvons représenter le processus d'apprentissage par l'intéraction d'un [[Agent]] avec un [[Environnement]].![[RLenv.PNG]]
L'agent et l'environnement intéragissent à chaque instant $t$ : l'agent reçoit une représentation de l'état de l'environnement $S_t \in \mathcal{S}$ et choisit donc une action $A_t \in \mathcal{A} (s)$, un instant plus tard il reçoit une récompense $R_{t+1} \in \mathcal{R} \subset \mathbb{R}$ et se retrouve dans un nouvel état $S_{t+1}$.

## PDM finis

Dans un PDM fini, les ensembles d'action, d'état et de récompense ($\mathcal{A}, \mathcal{S}, \mathcal{R}$) ont un nombre fini d'éléments. Dans ce cas, les variables aléatoires $R_t$ et $S_t$ ont une distribution de probabilité discrète qui ne dépend que de l'état précédent et de l'action choisie. On a donc pour $s, s' \in \mathcal{S}, r \in \mathcal{R}, a \in \mathcal{A}$ :
$$p(s',r | s, a) := \mathbb{P}(S_t = s', R_t = r | S_{t-1} = s, A_{t-1} = a)$$

La fonction $p$ définit la dynamique du PDM.

On définir de même:

- La probabilité de transition d'état : $$p(s' | s, a) := \mathbb{P}(S_t = s' | S_{t-1} = s, A_{t-1} = a) = \sum_{r \in \mathcal{R}} p(s',r | s, a)$$
- La récompense attendue pour un paire état/action : $$r(s, a) := \mathbb{E}\left[ R_t| S_{t-1} = s, A_{t-1} = a \right] = \sum_{r \in \mathcal{R}} r \sum_{s' \in \mathcal{S}} p(s',r | s, a)$$
- La récompense attendue pour un triplet état/action/état-suivant:$$r(s, a, s') := \mathbb{E}\left[ R_t| S_{t-1} = s, A_{t-1} = a, S_t = s' \right] = \sum_{r \in \mathcal{R}} r \frac{p(s',r | s, a)}{p(s' | s, a)}$$

L'objectif de l'apprentissage étant de maximiser le gaint total réçu par l'agent sur le long terme, on définit le gain attendu après l'instant t :$$G_t := R_{t+1} + R_{t+2} + R_{t+3} + \cdots + R_T$$

