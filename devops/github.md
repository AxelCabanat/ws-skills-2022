# GitHub

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- l'initialisation d'un projet ✔️

"A la création d'un projet, la commande "git init" permet l'utilisation des commandes git au sein de ce dernier et ainsi utiliser les fonctions de versionning de git et l'hébergement via un compte github ou gitlab."

- travailler avec des branches ✔️

"Une branche est une copie du code source principale qui permet de travailler sur ce dernier sans en changer le contenu pour les autre collaborateurs. Généralement, une branche est créée pour effectuer une tâche (développer une foctionnalité, résoudre un bug, remanier des morceaux de codes...). Au cours de son avancée, des sauvegardes d'étapes clés peuvent être mise en place sur cette branche seule, indépendamment du code source dans sa version d'origine. Ces sauvegardes sont appelés des commits."

- faire une PR ✔️

"Une fois l'objectif de la branche atteint, on entreprend l'intégration de notre développement sur la branche principale. On appelle cette intégration un "merge". Afin de prendre en compte les éventuels changements sur la branche visée, il est de bon ton d'intégrer le contenu de cette dernière dans notre branche annexe, de façon à gérer les éventuels conflits entre notre code et le ciblé. Une fois ces conflits gérés, le merge peut alors être proposé aux autres collaborateurs. C'est ce qu'on appelle une "Pull Request". Cette requête peut-être approuvée ou non. Des modifications d'extraits précis du code peuvent même être demandées."

- utiliser git rebase pour faire des commits propres ✔️

"La fonction "git rebase" permet de récupérer l'historique de commit d'une branche. Ainsi, afin d'intégrer nos commit dans la chronologie de la branche sur laquelle se base notre code, cette commande est utilisée pour s'intégrer dans une autre continuité de celle de notre branche."

- utiliser les gitHub actions ✔️

GitHub Actions est un service d'automatisation intégré à la plateforme GitHub. Il permet aux développeurs de définir et d'exécuter des flux de travail automatisés pour leurs projets. Les GitHub Actions sont déclenchées par des événements spécifiques, tels que les pushs de code, les créations de Pull Requests, les créations de tags, etc. Elles permettent d'automatiser des tâches courantes comme la construction, les tests, le déploiement, les notifications, etc.

Pour plus de détails sur leurs utilisations, se référer à la partie dédiée à la CI.

## 💻 J'utilise

### Un exemple personnel commenté ✔️

```bash

Cab@DESKTOP-IRQO7E4 MINGW64 ~/Documents/Wild/2209-wns-adleman-bordolamif (develop)
# mise à jour de la branche mère
$ git pull origin develop
remote: Enumerating objects: 93, done.
remote: Counting objects: 100% (93/93), done.
remote: Compressing objects: 100% (48/48), done.
remote: Total 77 (delta 53), reused 40 (delta 28), pack-reused 0
Unpacking objects: 100% (77/77), 22.02 KiB | 410.00 KiB/s, done.
From https://github.com/WildCodeSchool/2209-wns-adleman-bordolamif
 * branch            develop    -> FETCH_HEAD
   7addeef..2bd9907  develop    -> origin/develop
Updating 7addeef..2bd9907
Fast-forward
# détail des changements

Cab@DESKTOP-IRQO7E4 MINGW64 ~/Documents/Wild/2209-wns-adleman-bordolamif (develop)
# création de la nouvelle branche et déplacement vers cette dernière
$ git checkout -b 262-synthese-vocale
Switched to a new branch '262-synthese-vocale'

Cab@DESKTOP-IRQO7E4 MINGW64 ~/Documents/Wild/2209-wns-adleman-bordolamif (262-synthese-vocale)
# indexation des changements développés
$ git add .

Cab@DESKTOP-IRQO7E4 MINGW64 ~/Documents/Wild/2209-wns-adleman-bordolamif (262-synthese-vocale)
# commit du code indexé
$ git commit -m "fix counterResolver"
[262-synthese-vocale c143897] fix counterResolver
 1 file changed, 1 insertion(+), 2 deletions(-)

Cab@DESKTOP-IRQO7E4 MINGW64 ~/Documents/Wild/2209-wns-adleman-bordolamif (262-synthese-vocale)
$ git add .

Cab@DESKTOP-IRQO7E4 MINGW64 ~/Documents/Wild/2209-wns-adleman-bordolamif (262-synthese-vocale)
$ git commit -m "fix expo access token use & add vocal synthesis to tv screen"
[262-synthese-vocale 1a4fb3f] fix expo access token use & add vocal synthesis to tv screen
 5 files changed, 35 insertions(+), 4 deletions(-)
 create mode 100644 client_web/src/utils/speak.ts

Cab@DESKTOP-IRQO7E4 MINGW64 ~/Documents/Wild/2209-wns-adleman-bordolamif (262-synthese-vocale)
# récupération des mises à jour de la branche mère (aucun changement ici)
$ git pull origin develop
From https://github.com/WildCodeSchool/2209-wns-adleman-bordolamif
 * branch            develop    -> FETCH_HEAD
Already up to date.

Cab@DESKTOP-IRQO7E4 MINGW64 ~/Documents/Wild/2209-wns-adleman-bordolamif (262-synthese-vocale)
# envoi des commits sur une branche distante dédiée
$ git push origin 262-synthese-vocale
Enumerating objects: 36, done.
Counting objects: 100% (36/36), done.
Delta compression using up to 8 threads
Compressing objects: 100% (21/21), done.
Writing objects: 100% (21/21), 2.37 KiB | 2.37 MiB/s, done.
Total 21 (delta 17), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (17/17), completed with 15 local objects.
remote:
remote: Create a pull request for '262-synthese-vocale' on GitHub by visiting:
remote:      https://github.com/WildCodeSchool/2209-wns-adleman-bordolamif/pull/new/262-synthese-vocale
remote:
remote: GitHub found 4 vulnerabilities on WildCodeSchool/2209-wns-adleman-bordolamif's default branch (2 high, 2 moderate). To find out more, visit:
remote:      https://github.com/WildCodeSchool/2209-wns-adleman-bordolamif/security/dependabot
remote:
To https://github.com/WildCodeSchool/2209-wns-adleman-bordolamif.git
 * [new branch]      262-synthese-vocale -> 262-synthese-vocale
```
Une pull request est ensuite créée sur GitHub pour demander le merge de la branche sur develop sous condition de l'approbation des collaborateurs.

### Utilisation dans un projet ✔️

[lien github](https://github.com/WildCodeSchool/2209-wns-adleman-bordolamif)

Description : Projet de soutenance du titre professionnel concepteur développeur d'application

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
