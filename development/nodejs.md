# Titre de la compétence

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- Comment développer en utilisant un système de _livereloading_ (`nodemon` par exemple) ✔️

"nodemon permet de relancer le server à chaque actualisation du code afin de prendre en compte les modifications apportées. Si le serveur rencontre une erreur dû au code ajouté, il se relancera une fois l'erreur inciminée résolue."

- La connexion de mon application à une base de données avec et sans ORM/ODM (avec `mysql` puis `prisma` par exemple) ✔️

Appel à une bdd mysql sans ORM
```javascript
const database = mysql.createPool({
  host: process.env.DB_HOST, 
  port: process.env.DB_PORT, 
  user: process.env.DB_USER,
  password: process.env.DB_PASSWORD,
  database: process.env.DB_NAME,

});

const getMovies = (req, res) => {
  database
    .query("select * from movies")
    .then(([movies]) => {
      res.json(movies);
    })
    .catch((err) => {
      console.error(err);
      res.status(500).send("Error retrieving data from database");
    });
};
```

Appel à une bdd mysql via l'ORM Prisma
```javascript
//schema.prisma
generator client {
  provider = "prisma-client-js"
}

datasource db {
  provider = "mysql"
  url      = env("DATABASE_URL")
}

//model
const { PrismaClient } = require("@prisma/client");
const database = new PrismaClient();

const findAll = async () => {
    try {
        const movies = await database.$queryRaw`SELECT * FROM movies`;
        return movies;
    } catch (err){
        console.error(err);
        res.status(500).send("Error retrieving data from database");
    }
};
```

- Le développement d'une API REST et GraphQL (avec les packages `express` et `graphql` par exemple) ✔️

Définition du endpoint en API REST
```javascript
app.get("/api/counters", CounterController.getAllCounters);
```

Définition de la query en API GraphQL
```javascript
    @Query(() => [Counter])
  async getAllCounters(): Promise<Counter[]> {
    return await CounterController.getAllCounters();
  }
```

- _Bonus : la manipulation des fichiers système avec `fs` et l'utilisation des streams en NodeJS_ ❌ / ✔️

## 💻 J'utilise

### Un exemple personnel commenté ❌ / ✔️

```javascript
// this function takes a path to a .md file of the host system and write the HTML version of this file
// the .html file is given back
const convertMDFileToHTML = (pathToMDfile) => /* ... path to HTML file */
```

### Utilisation dans un projet ✔️

API REST :
[lien github](https://github.com/AxelCabanat/spot-on)

Description : Projet de soutenance du titre professionnel développeur web et web mobile

API GraphQL:
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
