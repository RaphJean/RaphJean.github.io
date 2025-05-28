---
layout: post
title: Fabrication du bras robotique "Le robot"
---


Nous avons fabriqué le robot so100 et pris en main l'utilisation du repo ["Le robot"](https://github.com/huggingface/lerobot) en planifiant quelques trajectoires bas niveau. Nous nous sommes aussi intéressé au repo ["Phosphobot"](https://github.com/phospho-app/phosphobot) (une surcouche pour le contrôle du bras) de la startup émergente ["Phospho AI"](https://phospho.ai/).

L'idée ce bras robotique est d'être contrôlé par le même bras dit. Il y a un follower (le bras manipulé) qui suit exactement le positionnement du leader (le bras qui contrôle le follower). L'objectif étant de guide le follower dans de nombreuses actions pour fabriquer un data-sets et entrainer une IA qui contrôle le bras pour lui permettre de généraliser certaines trajectoires. 

Nous avons fabriqué dans un premier temps le robot follower (le bras manipulé). Comme nous n'avions pas de leader, nous avons réfléchis à remplacer le leader (le bras qui agit en guise de manette) par un autre système de contrôle basé sur de la vision par ordinateur. L'idée est de mapper une configuration articulaire humaine récupérer à l'aide de caméra vers le robot pour le contrôler. La librairie ["Media Pipe"](https://github.com/google-ai-edge/mediapipe) semble être un très bon candidat pour récupérer l'information bio-mécanique.

Comme nous sommes en train de fabriquer des caméras en parallèles (pi-Caméra) nous pensons que c'est l'occasion de les utiliser dans ce contexte.

Une petite image prise à la fin de la fabrication du bras, je pouvais enfin le piloter !


<p align="center">
  <img src="../../../images/raph_lerobot.png" alt="Alt text" width="450"  />
</p>