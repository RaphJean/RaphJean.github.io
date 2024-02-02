---
layout: post
title: Simulation de planète
icon: ../images/planet.png
---


  
  

On s'intéresse dans ce problème à la simulation du climat sur une planète donnée. La simulation tente d'illustrer le comportement dynamique du climat en décrivant l'évolution des variables les plus notables : le mouvement de l'air, la température, l'humidité et la condensation de l'eau.

  

La planète est définie au préalable comme étant composé de surfaces de terrestre et aquatiques. Dans un premier temps, ces surfaces sont considérées comme fixes dans un premier temps, puis elles vont évoluer au rythme du climat dans un second temps.

  

La surface planète est un sytème fermé qui est sujet à diverses excitations externes : le rayonnement solaire, sa rotation.

  

Enfin, il est possible de visualiser le climat à partir des conséquences de celui-ci : une forte humidité.

  

Afin de développer un tel modèle, il y a plusieurs étapes essentielles à passer :
1. Créer la géométrie,
2. Mailler la géométrie,
3. Modéliser mathématiquement le problème,
4. Implémenter la méthode de résolution numérique du problème,
5. Résoudre le problème,
6. Visualiser les solutions.

  
# 1. Création et maillage de la géométrie
On souhaite modéliser l'atmosphère. Si l'on considère la terre comme une boule, l'atmosphère est la couche supérieure de la boule. De manière simplifiée, c'est une coque, dont le rayon $r_T$ correspond à la surface terrestre et $r_A$ correspond au rayon de extérieur de l'atmosphère. 

Cette géométrie est finalement assez simple à modéliser. Une simple utilisation du programme gmsh permet de faire l'affaire :
1. On crée deux boules $B_A$ et $B_T$ de diamètres respectifs $r_A$ et $r_T$,
2. On vient soustraire la boule la plus grande avec la boule la plus petite pour créer la coque,
3. On utilise dans un premier temps l'outil de maillage automatique de gmsh en fixant un paramètre pour la taille de chaque élément,
4. On garde en mémoire la surface terrestre ainsi que la surface atmosphérique qui vont permettre d'appliquer des conditions aux frontières.

