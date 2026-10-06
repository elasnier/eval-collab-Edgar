# 1. Choix du mécanisme d'authentification

## Statut
Accepté

## Contexte
Nous développons une API qui sera consommée par une application web (même domaine) et une application mobile. Notre équipe compte trois développeurs. Une exigence de sécurité stricte nous impose de pouvoir forcer la déconnexion immédiate d'un compte compromis. Nous devons choisir entre des sessions avec cookie, des JWT (stateless) ou des jetons d'API.

## Décision
Nous choisissons d'utiliser des **jetons d'API stockés en base de données**. 

Les JWT classiques (sans état) ne permettent pas de révoquer un accès immédiatement sans ajouter une couche complexe de liste noire. Les sessions avec cookies sont souvent fastidieuses à gérer sur des applications mobiles natives. Les jetons d'API stockés en base permettent une révocation instantanée (il suffit de supprimer le jeton de la base) et sont simples à implémenter pour notre équipe de trois développeurs.

## Conséquences
* **Positif :** La déconnexion forcée est garantie et immédiate (respect de l'exigence de sécurité).
* **Positif :** Intégration simple pour l'application mobile.
* **Négatif :** Obligation de faire une requête en base de données à chaque appel API pour vérifier la validité du jeton.