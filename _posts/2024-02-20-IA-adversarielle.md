---
layout: post
title: IA adversarial
---
Lors d'un projet scolaire, j'ai eu l'opportunité de développer une intelligence artificielle (IA) pour un jeu. Plusieurs algorithmes classiques ont été mis en œuvre, dont une réinterprétation du célèbre AlphaZero.

Le jeu sur lequel cette IA a été conçue est [Quoridor](http://quoridor.di.uoa.gr/), un jeu de plateau tour par tour où l'objectif est de bloquer son adversaire en plaçant des murs.

Dans un premier temps, différentes heuristiques et stratégies de jeu ont été élaborées pour créer un algorithme de type minimax, similaire à celui utilisé par Stockfish, le premier programme à avoir vaincu un humain aux échecs. Le principal inconvénient de ce type d'algorithme réside dans sa dépendance à la qualité des heuristiques, ce qui implique une grande compétence de la part du développeur dans le domaine du jeu.

Dans un second temps, une adaptation de l'algorithme [AlphaZero](https://github.com/plkmo/AlphaZero_Connect4), implémentée pour le jeu Puissance 4, a été développée. Cet algorithme repose sur la méthode de recherche MCTS (Monte Carlo Tree Search), qui explore de manière aléatoire les différents états du jeu tout en mémorisant les résultats à l'aide d'un réseau de neurones profonds grâce au Deep Reinforcement Learning.

Il convient de noter que l'algorithme MCTS est un outil de recherche très puissant, utilisé également dans des domaines de la mécanique pour la conception générative. Un exemple open source est le module Python [Rostok](https://github.com/aimclub/rostok), qui vise à générer le meilleur mécanisme pour une situation donnée.

<p align="center">
  <img src="../../../images/image_IA.png" alt="Alt text" width="800"  />
</p>