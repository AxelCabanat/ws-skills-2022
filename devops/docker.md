# Docker

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- la création d'une image docker ✔️

La création d'une image Docker se fait via l'écriture d'un Dockerfile. C'est un fichier texte qui définit les instructions nécessaires pour créer une image Docker. Il spécifie la base de l'image, les dépendances, les fichiers sources et les commandes à exécuter lors de la création de l'image. Le Dockerfile est généralement placé à la racine du projet. 

Voici une explication générale du processus :

    Définition de la base de l'image : il faut d'abord spécifier l'image de base à utiliser. Par exemple, l'image de système d'exploitation ou une image spécifique à un langage de programmation. Pour la suite des explications, nous prendrons l'exemple d'un environnement Ubuntu.
    Les commandes énoncés correspondront donc à celles spécifiques à cet environnement.

    Ajout des dépendances : Si l'application nécessite des dépendances spécifiques, il est nécessaire de les installer dans l'image Docker. Cela peut être fait à l'aide de commandes telles que RUN apt-get install pour les packages Ubuntu.

    Ajout des fichiers sources : On doit copier les fichiers sources de votre application dans l'image Docker. Pour se faire, utiliser la commande COPY. Par exemple, si on a un fichier index.js, on peut l'inclure dans l'image en utilisant COPY index.js /app.

    Définition des variables d'environnement : Si l'application nécessite des variables d'environnement spécifiques, il faut les définir dans le Dockerfile à l'aide de la commande ENV. Par exemple, ENV PORT=8080 définira une variable d'environnement PORT avec la valeur 8080.

    Exposition des ports : Si l'application écoute sur un port spécifique, il faut l'exposer dans l'image Docker afin de pouvoir y accéder depuis l'extérieur. On peut utiliser la commande EXPOSE pour spécifier les ports à exposer. Par exemple, EXPOSE 8080 exposera le port 8080.

    Définition de la commande d'exécution : Enfin, il est nécessaire de spécifier quelle commande exécuter lorsque le conteneur basé sur cette image est démarré via la commande CMD. Par exemple, CMD ["node", "index.js"] exécutera la commande node index.js lorsque le conteneur démarre.

Une fois le Dockerfile écrit, on peut construire l'image Docker en exécutant la commande docker build dans le répertoire contenant le Dockerfile. Cela va lire le Dockerfile, suivre les instructions et construire l'image Docker. 

- l'éxécution d'un container ✔️

Une fois la construction de l'image terminée, on peut exécuter un container issu de cette image à l'aide de la commande docker run. Chaque container créé à partir de l'image est une instance distincte et isolée de l'application, fonctionnant de manière autonome. Les containers sont conçus pour être éphémères et reproductibles. On peut surveiller leurs comportements via un terminal ou docker desktop et les arrêter via la commande docker stop.


- l'orchestration de containers avec docker-compose ✔️

Docker Compose permet de définir, configurer et exécuter plusieurs conteneurs interconnectés en utilisant un fichier YAML appelé docker-compose.yml.

Voici comment fonctionne l'orchestration de containers :

    Configuration des services : Dans le fichier docker-compose.yml, il faut définir les différents services (conteneurs) qui composent l'application. Chaque service est identifié par un nom et comprend les détails spécifiques tels que l'image à utiliser, les ports à exposer, les volumes à monter, etc.

    Gestion des volumes de données : Docker Compose permet de définir des volumes pour les conteneurs, et ainsi de persister les données même lorsque les conteneurs sont détruits et recréés. Cela facilite la gestion des données dans un environnement de conteneurisation.

Une fois que vous avez configuré votre fichier docker-compose.yml, vous pouvez exécuter les services en utilisant la commande docker-compose up. Docker Compose crée et démarre les conteneurs spécifiés, en les reliant selon les dépendances définies.
Lorsque vous exécutez cette commande, Docker Compose construit automatiquement les images nécessaires.


## 💻 J'utilise

### Un exemple personnel commenté ✔️

```yaml
name: WaitIt-development
# Configuration des services
services:
  db:
    image: postgres:15-alpine
    container_name: WaitIt-db
    environment:
      POSTGRES_PASSWORD: ${POSTGRES_PASSWORD}
      POSTGRES_USER: ${POSTGRES_USER}
      POSTGRES_DB: ${POSTGRES_DB}
    ports:
      - 5432:5432
    healthcheck:
      test:
        [
          'CMD-SHELL',
          'pg_isready -U ${POSTGRES_USER} -d postgres'
        ]
      interval: 10s
      timeout: 5s
      retries: 5
    volumes:
      - db:/var/lib/postgresql/data

  server:
    container_name: WaitIt-server
    depends_on:
      db:
        condition: service_healthy
    build: ./server
    ports:
      - 4000:4000
      - 5001:5001
    volumes:
      - ./server/src:/app/src
    environment:
      POSTGRES_PASSWORD: ${POSTGRES_PASSWORD}
      POSTGRES_USER: ${POSTGRES_USER}
      POSTGRES_DB: ${POSTGRES_DB}
      POSTGRES_DB_TEST: ${POSTGRES_DB_TEST}
      DB_PORT: ${DB_PORT}
      CORS_ALLOWED_ORIGINS: ${CORS_ALLOWED_ORIGINS}
      JWT_PRIVATE_KEY: ${JWT_PRIVATE_KEY}
      SERVER_HOST: ${SERVER_HOST}
      SERVER_PORT: ${SERVER_PORT}
      DB_HOST: 'db'
      NODE_ENV: 'development'
      CHOKIDAR_USEPOLLING: 'true'

  client:
    container_name: WaitIt-client
    build: ./client_web
    ports:
      - 3000:3000
    volumes:
      - ./client_web/src:/app/src
    environment:
      VITE_GRAPHQL_API_URL: 'http://localhost:4000'
      VITE_WEBSOCKET_URL: ${VITE_WEBSOCKET_URL}
      CHOKIDAR_USEPOLLING: 'true'
# Gestion des volumes de données (ici espace non déterminé)
volumes:
    db:
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
