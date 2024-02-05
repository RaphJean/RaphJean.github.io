---
layout: post
title: Design d'une propulsion vectorielle
---


Dans le cadre du projet [SkyArch](https://skyarch-aero.com), j'ai eu l'opportunité de contribuer à la conception d'un drone dirigeable. Ce qui distingue le drone dirigeable, c'est sa capacité à rester en l'air grâce à un gaz porteur plus léger que l'air, tel que l'hélium ou l'hydrogène. Un tel engin présente une dynamique similaire à celle d'un bateau.

Afin de minimiser la masse utilisée pour la propulsion, nous avons opté pour l'utilisation d'un système à propulsion vectorielle : le dirigeable est manœuvré en ajustant la direction des hélices. Ce système s'oppose au système à propulsion différentielle, qui est principalement utilisé pour les drones classiques à plusieurs hélices (comme les quadridrones). Dans ce dernier cas, l'appareil est dirigé en modulant la force propulsive de chaque hélice. Par exemple, pour virer à droite, il suffit d'augmenter la force sur l'hélice de gauche par rapport à celle de droite.

Finalement, la propulsion vectorielle est également utilisée pour certains bateaux : pour manœuvrer les zodiacs, on change la direction des hélices. De plus, un dirigeable est un très gros objet qui a beaucoup d'inertie en raison de sa prise au vent. Ainsi, la manœuvre par propulsion vectorielle, qui implique un changement de direction assez lent, est bien adaptée à ce type d'engin. En revanche, les drones multicoptères, du fait qu'ils sont légers et ont une faible prise au vent, ont besoin d'un système qui leur permet de changer de direction rapidement. La propulsion différentielle est parfaite pour cela, le changement de direction peut se faire quasiment instantanément.

Pour concevoir un tel système, plusieurs options sont disponibles. Nous avons choisi d'opter pour l'approche la plus évidente. Un premier servo-moteur permet d'ajuster le premier angle $\theta_1$ du système, qui comprend également le second servo-moteur et l'hélice. Le second servo-moteur permet de régler l'angle $\theta_2$ de l'hélice.

En réalité, la rotation de chacun de ces angles n'est pas directement fournie par le servo-moteur, mais elle est transmise via un mécanisme de piston.


Le problème a été conçu en utilisant SolidWorks, en utilisant une méthode très puissante appelée "top-down". Cette approche implique de modéliser paramétriquement chacune des pièces du mécanisme en fonction des autres pièces avec lesquelles elles interagissent.

Enfin, le mécanisme a été testé en l'imprimant à l'aide des imprimantes 3D du fablab de Polytechnique Montréal.