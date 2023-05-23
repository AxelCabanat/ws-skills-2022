# Microservices

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- les différences avec l'architecture monolithique ✔️

Dans une architecture monolithique, l'application est développée comme une seule unité indivisible. Toutes les fonctionnalités et les modules de l'application sont regroupés en un seul et même code source. Elle tend alors à être de grande taille et complexe, car toutes les fonctionnalités sont regroupées en un seul code source. Cela peut rendre le développement, le déploiement et la maintenance plus difficiles.
Ses différents modules de partagent la même base de code et s'exécutent dans le même processus. La communication entre les modules se fait généralement via des appels de fonction interne. L'évolutivité est limitée, car tous les modules doivent être mis à l'échelle ensemble.
L'application monolithique est déployée en tant qu'entité unique. Cela signifie que toute modification ou mise à jour nécessite le déploiement de l'ensemble de l'application, ce qui peut entraîner des interruptions de service.
De par son architecture, toutes les parties de l'application sont généralement développées en utilisant la même technologie et les mêmes outils. Cela peut limiter la flexibilité lorsqu'il s'agit d'adopter de nouvelles technologies.

Dans une architecture microservices, l'application est composée de petits services autonomes et indépendants. Chaque service est responsable d'une fonctionnalité spécifique et communique avec les autres services via des API, généralement à l'aide de protocoles de communication légers tels que HTTP/REST. Chaque service pouvant être mis à jour de manière indépendante, cette structure permet une meilleure évolutivité et flexibilité. 
Les microservices sont petits et indépendants les uns des autres, ce qui les rend plus faciles à développer, tester, déployer et maintenir. Chacun d'eux peut être développé, mis à l'échelle et déployé séparément selon les besoins.
Cela permet des mises à jour continues et des déploiements plus rapides, sans affecter l'ensemble de l'application. De plus, si un microservice échoue, les autres services peuvent continuer à fonctionner, ce qui améliore la disponibilité globale du système.
Les microservices offrent une plus grande flexibilité technologique. Chaque service peut être développé avec la technologie la plus adaptée à sa fonctionnalité spécifique. Cela permet d'adopter de nouvelles technologies plus facilement et de tirer parti des avantages spécifiques de chaque technologie.

- la communication asynchrone entre services ✔️

La communication asynchrone entre les services est une approche courante pour permettre une interaction efficace et flexible entre les différents composants du système. Elle est généralement réalisée à l'aide d'un système de messagerie ou de files d'attente, par exemple via Message Queuing Telemetry Transport, un protocole léger de messagerie asynchrone utilisant un modèle de publication/abonnement (publish/subscribe). Chaque service peut publier des messages dans une file d'attente pour notifier d'autres services d'un événement ou d'une action qui s'est produite. Les services intéressés peuvent ensuite consommer ces messages et réagir en conséquence.

- le deploiement d'un cluster ❌ / ✔️


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
