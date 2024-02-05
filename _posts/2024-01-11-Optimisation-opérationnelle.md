---
layout: post
title: Optimisation opérationnelle
---



Lors de ma scolarité, j'ai eu la chance d'apprendre à poser et résoudre avec la meilleure stratégie des problèmes d'optimisation variés, notamment :
- L'optimisation linéaire (PL),
- L'optimisation linéaire en nombre entier (PLNE),
- L'optimisation sous contraintes,
- Les optimisations non linéaires,
- D'autres formes d'optimisations.

Ces types de problèmes peuvent la plupart du temps être associés à des problèmes classiques pour lesquels des algorithmes optimisés ont été développés, tels que :
- Des problèmes sur les graphes, tels que le calcul du plus court chemin, le flux maximal, le transport, l'affectation, ou la création d'horaires,
- L'ordonnancement,
- Les contraintes globales, par exemple, la résolution de problèmes de "Tous différents" comme le Sudoku.

[Minizinc](https://www.minizinc.org) est un outil précieux pour la modélisation et la résolution de ce type de problèmes de manière très abstraite. De nombreux algorithmes de résolution de ces problèmes sont implémentés en Python et sont prêts à être utilisés.

Pourquoi est-il important pour un ingénieur mécanique de savoir identifier et résoudre de tels problèmes ? Eh bien, ces problèmes peuvent surgir à n'importe quelle étape de la résolution d'un problème technique. Pour illustrer cela, prenons quelques exemples. Le premier exemple est lié à la méthode de suivi des modes propres.

Un grand nombre de problèmes physiques peuvent être modélisés de manière linéaire sous la forme d'un problème de valeurs propres :
$$
L(u) = \lambda u
$$
C'est le cas, bien sûr, des problèmes de vibrations, de flambement ou de conduction thermique. Ces problèmes ont un nombre discret de solutions $(u_n, \lambda_n)$.

Supposons que le système dépende de paramètres, et que nous souhaitons mener une étude paramétrique en faisant varier ce paramètre (par exemple, en rigidifiant une partie de notre pièce mécanique). Dans ce cas, les solutions du problème dépendent du paramètre $\gamma$ : $(u_n(\gamma), \lambda_n(\gamma))$. Comment pouvons-nous nous assurer que la solution $(u_i(\gamma_1), \lambda_i(\gamma_1))$ est équivalente à la solution $(u_i(\gamma_2), \lambda_i(\gamma_2))$ lorsque $\gamma_1 \neq \gamma_2$ ? Cela pose un problème d'optimisation d'assignation, où la tâche consiste à associer les $(u_i(\gamma_1), \lambda_i(\gamma_1))$ aux $(u_i(\gamma_2), \lambda_i(\gamma_2))$ de la manière la plus appropriée, en utilisant par exemple une métrique de couplage, comme la somme des intercorrélations entre chacun des modes.

Ce type de problème se retrouve également en analyse d'images, lorsque l'on souhaite associer une famille d'objets détectés sur une image à une famille d'objets pré-enregistrés.