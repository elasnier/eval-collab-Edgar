# ADR-001 : Choix technologique de la maquette initiale

Date : 2026-10-06
Statut : Accepté
Décideurs : Équipe de développement

## Contexte
Besoin de valider rapidement le design (couleurs pastel, thème anti-stress) et les interactions basiques (micro-animations) du site vitrine "Squishy Dumplings". Nous cherchons la solution la plus rapide à mettre en place sans sur-ingénierie, l'équipe connaissant bien le web natif.

## Options envisagées
1. HTML/CSS natif (Vanilla)
2. Framework React.js
3. Framework CSS (Tailwind)

## Décision
Utiliser **HTML5 et CSS3 natifs**, regroupés dans un unique fichier `index.html`.

## Conséquences
+ Déploiement immédiat et aucune étape de configuration / compilation requise.
+ Code très léger et lisible par tous.
- Manque de modularité : la duplication de code sera inévitable si on ajoute de nouvelles pages.
- Si le fichier grandit, le CSS intégré deviendra difficile à maintenir (nécessitera une refonte ou extraction).
