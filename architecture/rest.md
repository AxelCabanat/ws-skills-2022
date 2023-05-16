# REST API

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- les verbes HTTP ✔️

"Les verbes HTTP définissent le type d'action que l'on souhaite réaliser avec les données.
Les principaux verbes utilisés quotidiennement par un serveur sont les suivants :

- GET : lire la donnée
- POST : créer la donnée
- PUT/PATCH : modifier la donnée (totalement/partiellement)
- DELETE : supprimer la donnée"

- les statuts HTTP ✔️

"Les statuts HTTP sont des codes référant à des états de faits vis-à-vis d'une requête.
Ils sont organisés de la façon suivante :

- De 100 à 199 : Les réponses informatives
- De 200 à 299 : Les réponses de succès
- De 300 à 399 : Les messages de redirection
- De 400 à 499 : Les erreurs du client
- De 500 à 599 : les erreurs du serveur

Il est à noter que si certaines sont rencontrées quotidiennement (201 : created, 404 : not found) d'autres s'avèrent moins fréquentes (418 : I'm a teapot)"

- les endpoints ✔️

"Un Endpoint est ce qu’on appelle une extrémité d’un canal de communication.
Dans le cadre d'une API, cette dernière interagit avec un autre système (comme par exemple une base de données), les points de contact de cette communication sont considérés comme des Endpoints. Ils représentent l’endroit où les API envoient les demandes et où réside la ressource et sont caractérisés par un chemin d'accès propre."

- CORS ✔️

"On dit que deux URL ont des origines différentes si elles ne partagent pas le même hôte / port.
Par défaut, une application n'est pas autorisée à utiliser les ressources d'une autre origine, sauf si on le lui précise. Ainsi, un front et un back tournant sur des domaines différents ne pourront pas communiquer.

Par l'utilisation de CORS (ou Cross-Origin Resource Sharing) par notre server, ce dernier peut alors recevoir des données en provenance du côté client."


- la nomenclature recommandée pour les routes ✔️

  "A titre d'illustration, nous prendrons ici l'exemple d'un site fictif "https://monsite.com" (Toute référence à un site réel sera dans le cas présent tout à fait fortuite).
  Par convention, il est de bon ton que nos routes d'api commencent par "https://api.monsite.com/"
  Pour constituer une route en accord avec les normes REST, certaines règles sont à observer:

  - Utiliser des noms aussi intuitifs et simples que possible
  - Utiliser des lettres minuscules
  - Eviter les caractères spéciaux, qui peuvent avoir d'autres significations que celles attendues
  - Utiliser des Forward Slash pour séparer les éléments de notre route
  - Le séparateur de mot doit être le "-" et non "\_" ou une utilisation du camelCase, qui rentrerait en conflit avec le second point évoqué.
  - Utiliser le camelCase pour les paramètres
  - Ne pas utiliser d'extention de fichier.

  Ainsi, si nous voulons accéder à nos utilisateurs, nous enprunteront la route "https://api.monsite.com/users" et pour accéder au prénom de notre 42e utilisateur, nous crérons la route "https://api.monsite.com/users/:userId/first-name" de façon à y accéder par l'URL suivante : "https://api.monsite.com/users/42/first-name"

## 💻 J'utilise

### Un exemple personnel commenté ❌ / ✔️

### Utilisation dans un projet ❌ / ✔️

[lien github](...)

Description :

### Utilisation en production si applicable❌ / ✔️

[lien du projet](...)

Description :

### Utilisation en environement professionnel ❌ / ✔️

Description :

## 🌐 J'utilise des ressources

### Titre

- lien
- description

## 🚧 Je franchis les obstacles

### Point de blocage ❌ / ✔️

Description:

Plan d'action : (à valider par le formateur)

- action 1 ❌ / ✔️
- action 2 ❌ / ✔️
- ...

Résolution :

## 📽️ J'en fais la démonstration

- J'ai ecrit un [tutoriel](...) ❌ / ✔️
- J'ai fait une [présentation](...) ❌ / ✔️
