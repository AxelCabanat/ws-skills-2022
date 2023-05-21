# Integration continue

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- les enjeux de l'integration continue ✔️

L'intégration continue (CI) vise à automatiser et à faciliter le processus d'intégration des modifications de code dans un projet. Les enjeux de l'intégration continue sont nombreux et ils jouent un rôle essentiel dans l'amélioration de la qualité du logiciel et l'efficacité du développement. Voici quelques-uns de ses principaux enjeux :

    Détection précoce des erreurs : L'intégration continue permet de détecter les erreurs et les conflits dès que le code est intégré au référentiel central. Cela permet de réduire les problèmes qui surviennent lors de la fusion tardive de branches de code et facilite la correction des erreurs dès leur apparition.

    Livraison plus rapide : En automatisant le processus d'intégration et de construction, l'intégration continue permet de réduire le temps nécessaire pour livrer de nouvelles fonctionnalités ou des correctifs. Les développeurs peuvent soumettre leurs modifications de code et obtenir rapidement des résultats sur la qualité du logiciel, ce qui accélère le cycle de développement global.

    Réduction des conflits de fusion : Lorsque plusieurs développeurs travaillent simultanément sur un projet, il peut y avoir des conflits lors de la fusion de leurs modifications. L'intégration continue facilite la détection précoce de ces conflits, permettant aux développeurs de les résoudre rapidement. Cela évite les retards et les frustrations liés aux conflits de fusion tardifs.

    Automatisation des tests : L'intégration continue encourage l'automatisation des tests unitaires et fonctionnels. Les tests sont exécutés à chaque intégration, ce qui permet de s'assurer que les modifications de code n'introduisent pas de régressions ou d'erreurs. L'automatisation des tests garantit une meilleure qualité du logiciel et permet de détecter les problèmes plus tôt.

    Fiabilité et stabilité accrues : L'intégration continue favorise la création d'un processus de développement stable et fiable. En détectant rapidement les erreurs, en automatisant les tests et en encourageant une collaboration étroite entre les membres de l'équipe, l'intégration continue contribue à la construction de logiciels de meilleure qualité, avec moins de bugs et de problèmes de compatibilité.


- la mise en place d'une github action ✔️

GitHub Actions est une fonctionnalité intégrée à la plateforme GitHub qui permet d'automatiser des tâches dans le cadre de votre flux de travail de développement logiciel. Voici les étapes générales pour configurer une GitHub Action :

    Création d'un fichier de workflow : Tout d'abord, vous devez créer un fichier de workflow qui définit les actions à effectuer. Ce fichier est généralement placé dans le répertoire ".github/workflows" de du référentiel GitHub.

    Choix de l'événement déclencheur : Il est nécessaire de spécifier l'événement qui déclenchera l'action. Il peut s'agir d'un push sur une branche spécifique, d'une création d'une Pull Request, d'une nouvelle version taguée, etc. Cela dépend des besoins de du projet.

    Définition des jobs et des étapes : Dans le fichier de workflow, on peut définir un ou plusieurs jobs, qui sont des unités d'exécution indépendantes. Chaque job peut contenir plusieurs étapes, qui sont des actions individuelles à exécuter.

    Configuration des actions : Pour chaque étape, il faut spécifier les actions à exécuter. Les actions peuvent être des actions prédéfinies fournies par GitHub ou des actions personnalisées. Les actions prédéfinies couvrent diverses tâches courantes telles que la construction, les tests, le déploiement, etc.

    Gestion des dépendances et des variables : Si le workflow dépend de certaines dépendances ou nécessite des variables d'environnement spécifiques, il est impératif de les spécifier dans le workflow. Il est également possible définir des secrets GitHub pour protéger les informations sensibles, comme les clés d'API ou les jetons d'accès.

## 💻 J'utilise

### Un exemple personnel commenté ❌ / ✔️

```yaml 
name: Tests

# Choix de l'événement déclencheur 
on:
  pull_request:
    branches:
      - develop

jobs:

# Définition des jobs
  tests:

    runs-on: ubuntu-latest

# Définition des étapes
    steps:
    # Configuration des actions
      - name: Check out code
        uses: actions/checkout@v3

      - name: Make root envfile
        uses: SpicyPizza/create-envfile@v1.3
        # Gestion des dépendances et des variables
        with:
          envkey_POSTGRES_PASSWORD: "CECI_EST_UN_MOT_DE_PASSE"
          envkey_POSTGRES_USER: "CECI_EST_UN_UTILISATEUR"
          envkey_POSTGRES_DB: "CECI_EST_UNE_BASE_DE_DONNEES"
          envkey_POSTGRES_DB_TEST: "CECI_EST_UNE_BASE_DE_DONNEES_TEST"
          envkey_DB_PORT: 5432
          envkey_CORS_ALLOWED_ORIGINS: "http://localhost:3000,http://localhost:4000"
          envkey_JWT_PRIVATE_KEY: "CECI_EST_UNE_CLE_PRIVEE"
          envkey_SERVER_HOST: "localhost"
          envkey_SERVER_PORT: 4000
          directory: ./
          file_name: .env
          fail_on_empty: false


      - name: Build and run docker tests
        run: npm run test:docker

```
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
