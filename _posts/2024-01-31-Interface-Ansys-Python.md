---
layout: post
title: Interface Ansys et python
icon: ../images/ansys-python.svg
---
Python est le langage de programmation le plus utilisé pour faire l'interface entre des codes et des logiciels. La plupart des logiciels ont leurs propres API : c'est le cas d'Ansys avec pyAnsys. 
Le module qui m'intéresse ici particulièrement est [pyMapdl](https://mapdl.docs.pyansys.com/version/stable/), qui permet d'appeler un modèle Ansys APDL directement depuis Python. En effet, une fois que le modèle a été sauvegardé au format .db, il est possible de le modifier : par exemple, de changer le prétraitement en modifiant certains paramètres, puis de lancer la simulation et enfin de récupérer les résultats.

<p align="center">
  <img src="../../../images/Ansys-python-scheme.png" alt="Alt text" width="600"  />
</p>

 Ansys est très pratique pour créer son modèle et offre des méthodes appropriées pour le résoudre. Une fois que les équations sont implémentées, il reste également très utile pour visualiser les résultats dans leur ensemble et vérifier que la physique fonctionne correctement. Cependant, Ansys offre peu de flexibilité lorsqu'il s'agit de réaliser des simulations avec une liste de paramètres. De plus, Ansys ne permet pas directement d'effectuer des analyses précises sur les résultats des simulations, en particulier l'exécution d'algorithmes pour l'analyse des données.

C'est là qu'intervient l'utilisation de Python : il est possible à la fois de lancer des simulations sur des ensembles de paramètres entiers et d'exécuter des algorithmes spécifiques pour l'analyse des résultats.

Dans mon exemple, je souhaite effectuer une analyse des résultats en identifiant des modes de disques spécifiques dont la forme est préconnue. De plus, pour analyser l'interaction acoustique-structure de mon modèle vibroacoustique, je fais varier la vitesse du son dans l'eau. Tout cela peut être exécuté dans une simple boucle.

De plus, je peux utiliser toutes les bibliothèques disponibles en Python pour effectuer l'analyse des résultats de mon système éléments finis modélisé et résolu par Ansys. Pour ce faire, je procède en trois étapes :
1. Je commence par extraire les données du modèle qui me permettront de réaliser les analyses ultérieures : le maillage et les types d'éléments, en les classant selon les domaines précédemment définis à partir des sélections nommées dans Ansys.

2. Ensuite, j'extrais les résultats par domaines.

3. Enfin, j'utilise les modules d'éléments finis disponibles en Python :
    - Je recommande [FEnics](https://fenicsproject.org) ou sa nouvelle version en cours de développement, [FEnicsx](https://github.com/FEniCS/dolfinx). Ce module est très complet, mais son installation sur des ordinateurs sans Linux peut être un peu complexe, et sa prise en main peut être un défi.
    - Si vous préférez une option plus simple pour le FEM en Python, je recommande [Scikit FEM](https://github.com/kinnala/scikit-fem), qui est excellent et particulièrement simple à installer et à comprendre, même s'il n'est pas aussi complet que FEnics.

La mise en place de cette routine m'a permis de lancer des simulations Ansys sur toute une gamme de valeurs de vitesse du son, tout en simplifiant le système à un modèle comportant seulement quelques degrés de liberté, bien plus gérable que celui constitué de millions de degrés de liberté.

Voici quelques exemples de résultats que j'ai pu obtenir :

<p align="center">
  <img src="../../../images/Ansys-python-analysis.png" alt="Alt text" width="800"  />
</p>
