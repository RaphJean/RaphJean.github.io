---
layout: post
title: Participation au hackaton "le robot worldwide"
---


Récemment, mon équipe et moi avons participé au **LeRobot Worldwide Hackathon**, un événement où l’on peut vraiment laisser libre cours à sa créativité et tester des idées audacieuses. Nous nous sommes fixés pour objectif d'explorer comment rendre les robots capables de ressentir et d’exprimer des émotions pour créer un **spectacle de marionnettes interactif**.

Pour ce projet, nous nous sommes appuyés sur le jeu de données **LEPuppet Emotions**, disponible sur Hugging Face, et nous avons conçu un **pipeline complet pour capturer, analyser et générer des émotions** à partir des mouvements et du texte.  


La première étape a été de collecter des **trajectoires de mouvement correspondant à différents états émotionnels**. Grâce à des techniques de réduction de dimensionnalité, nous avons pu visualiser les émotions sous forme de clusters bien distincts. Résultat : chaque émotion avait sa propre “signature” de mouvement.  

Pour générer de nouveaux mouvements émotionnels, nous avons développé un **réseau LSTM léger**, avec seulement ~50 000 paramètres. Malgré sa taille réduite, il produit des **patterns de mouvement cohérents et facilement reconnaissables**. C’est toujours fascinant de voir qu’un petit modèle peut créer quelque chose qui semble “vivant”.

Mais les émotions ne viennent pas que du mouvement : le texte a aussi son rôle. Nous avons intégré un module capable d’analyser **le texte transcrit d’un locuteur en temps réel** pour en déduire l’émotion sous-jacente. Le robot peut alors adapter ses mouvements pour refléter ce que l’on ressent : comme un vrai partenaire de scène.  

Enfin, pour que le spectacle soit crédible, nous avons mis en place un **module de synchronisation labiale** qui aligne les visèmes avec l’audio. Le résultat ? Un robot qui parle et bouge les lèvres naturellement, donnant vie aux émotions de façon réaliste.  


Le travail de notre équipe a donné lieu à un **spectacle interactif fascinant**, que vous pouvez découvrir ici :  
[Voir la vidéo](https://huggingface.co/datasets/LeRobot-worldwide-hackathon/submissions/blob/main/324-goofyparis-bot.mp4.mp4)  

Vous pouvez également explorer tout le code sur notre GitHub :  
[https://github.com/RaphJean/Hugging-face-hackaton-le-robot-worldwide.git](https://github.com/RaphJean/Hugging-face-hackaton-le-robot-worldwide.git)  


Participer à ce hackathon avec mon équipe nous a permis de combiner plusieurs compétences : **analyse de données, machine learning léger, traitement du langage, animation 3D et synchronisation audio-vidéo**. Et surtout, cela nous a rappelé que **la technologie peut être fun et émotionnelle à la fois** !
