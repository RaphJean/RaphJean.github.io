---
layout: post
title: Ansys discovery et design en temps réel
---

Sur le thème du design et de l'optimisation, nous avons examiné le nouveau logiciel de conception d'Ansys : Ansys Discovery. Il s'agit d'un logiciel conçu pour faciliter considérablement les allers-retours entre la conception et la simulation. Il vise à se positionner entre ces deux phases.


Il dispose de quelques outils de CAO qui lui permettent de modifier rapidement la géométrie. De plus, il intègre les principaux outils de simulation basés sur les solveurs Ansys :
- Structurels,
- Thermiques,
- Fluides.

La mise en place des simulations a été pensée pour être très rapide pour l'utilisateur. Une fois la simulation configurée, l'utilisateur dispose de plusieurs niveaux de raffinement : un raffinement très grossier qui est rapide à résoudre car il fonctionne sur GPU, et un solveur plus précis qui fonctionne sur le CPU.


L'outil permet effectivement d'abord d'améliorer grossièrement la géométrie, puis au fur et à mesure de la progression dans la simulation, on peut l'affiner plus précisément.


De plus, Ansys Discovery permet de réaliser de la conception générative en proposant un optimiseur topologique qui permet de visualiser plusieurs versions d'une même géométrie, tout en fournissant un indicateur d'objectif affiché sur un graphique en fonction des différentes itérations ou versions de la génération.


J'ai testé l'utilisation du logiciel en créant une géométrie CAO d'un concept de quadricoptère, en introduisant des dissipateurs de chaleur au niveau du moteur, des circuits électroniques et de la batterie.


Une fois la géométrie importée dans Discovery, j'ai pu facilement lancer une simulation structurelle, une simulation topologique et une simulation thermique. La simulation thermique a rapidement montré que le dissipateur de chaleur pour le circuit électronique était surdimensionné, car l'afflux de chaleur restait concentré près du circuit. Ainsi, en modifiant rapidement la géométrie pour retirer de la matière, il est possible d'observer l'évolution de la température. L'ensemble de ces simulations ne m'a pris que 20 minutes, alors qu'autrefois il aurait fallu des journées pour un tel processus.

<p align="center">
  <img src="../../../images/ansys-discovery-2.png" alt="Alt text" width="800"  />
</p>