---
layout: post
title: Optimisation multi-disciplinaire et design
---
Supposons que l'on possède un cahier des charges pour la conception d'un drone (aérien). Je sais que je souhaite une certaine autonomie, une vitesse de pointe donnée et une certaine robustesse.

Le problème, c'est que la conception d'un drone fait appel à différentes disciplines, qui vont chacune fabriquer leur propre composant :
- La propulsion qui s'occupe du moteur et des hélices
- Le génie électrique qui s'occupe de la batterie
- Le génie aéro qui s'occupe de l'aérodynamisme
- Le génie automatique qui s'occupe du contrôle et de la stabilité du drone
- Le génie mécanique qui s'occupe de la robustesse et de la légèreté
- Le génie réseau qui s'occupe de la communication
- Le génie système qui s'occupe du système embarqué
- Etc.

Ça fait beaucoup de choses à penser en même temps… Même pour un pré-dimensionnement, c’est assez complexe, on ne sait pas quelle discipline va influencer l'autre, etc.

Il y a plusieurs manières de traiter un tel problème multidisciplinaire. La première, qui est la plus simple mais qui peut prendre un certain temps et peut coûter un peu d’argent en échecs successifs, c’est la méthode itérative. Elle consiste à partir d’une discipline et à propager le design vers les autres disciplines en itérant, et à chaque itération, le design s’améliorera.

La seconde manière est dite « monolithique ». Elle consiste véritablement à penser à tout en même temps en prenant le temps de comprendre comment chacune des disciplines est interconnectée. Par exemple, la force propulsive des hélices va appliquer une force et déformer la structure, ainsi la propulsion influence la structure mécanique. Un autre exemple concerne la puissance délivrée par la batterie sous forme de tension et d'intensité, qui va influencer le couple et la vitesse de rotation des moteurs, ce qui à son tour influence les hélices, formant ainsi une chaîne d'influence, du génie électrique vers la propulsion.

En déterminant des règles mathématiques pour modéliser ces différentes influences, il est possible d'obtenir un système d'équations entre les variables interdisciplinaires. Les variables de ce système sont souvent contraintes pour respecter le cahier des charges. De plus, le système possède généralement plus d'inconnues que d'équations. Mais alors, comment déterminer une valeur pour les inconnues recherchées ? Il suffit de déterminer une fonction objectif à optimiser, par exemple l'endurance du drone ou sa vitesse maximale.
Toutes les variables de design qui étaient auparavant libres seront maintenant fixées pour le prédimensionnement du drone.

Cette science de l'optimisation interdisciplinaire porte le nom anglais de « multidisciplinary optimization ». Elle prend toute son importance dans des projets macroscopiques qui font appel à de nombreuses connaissances et à divers corps de métier.

En fait, le principe de cette discipline est d'exprimer le problème d'une manière suffisamment claire et modulaire pour pouvoir relier l'ensemble des corps de métier à un seul projet avec un objectif bien établi. Différents outils ont vu le jour pour l'expression et le traitement de ces types de problèmes, notamment différents types de diagrammes :

- Le plus important : le diagramme XDSM permet de relier l'ensemble des composantes d'un projet d'ingénierie de manière claire, et permet ainsi d'observer les différentes interdépendances. (Exemple ci-dessous tiré de : "Efficient sizing and optimization of multirotor drones based on scaling laws and similarity models", S Delbecq)
<p align="center">
  <img src="../../../images/diagramme_xdlsm.png" alt="Alt text" width="800"  />
</p>
- Le diagramme N2 : qui est la version précise du diagramme XDSM, permet de représenter à la variable près le code. Lors de mon prédimensionnement d'un drone, j'ai généré un tel diagramme qui se trouve au lien [Diagramme N2](/html/assembly_dyn.html). Vous noterez déjà la complexité d'un tel diagramme pour un simple modèle de drone (hélices, moteurs, ESC, batterie).

Ces diagrammes sont des outils théoriques, mais quels sont les outils pratiques disponibles ? La NASA a développé un code open source pour le développement de ce type de modèle de manière efficace en Python. Le module se nomme [OpenMDAO](https://openmdao.org) et possède une communauté de scientifiques très active. Pour les curieux, le module a une chaîne [YouTube](https://www.youtube.com/@OpenMDAO) qui présente le principe de l'optimisation interdisciplinaire et de l'optimisation en général de manière très pédagogique et bien illustrée.

J'ai moi-même utilisé ce module pour construire ma modélisation simple du drone pour le prédimensionnement.

De plus, un grand nombre de codes se sont développés autour de ce module. En particulier, on trouve [Fast-OAD](https://github.com/fast-aircraft-design/FAST-OAD), qui est un code spécialisé dans le design de systèmes aéronautiques et de l'aviation, conçu par un groupe de chercheurs de Supaero.