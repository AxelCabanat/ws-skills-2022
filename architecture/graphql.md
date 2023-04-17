# GraphQL

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- la différence entre REST et GraphQL ✔️

REST est le standard d'API le plus répendu. Pour un point d'entrée il fait correspondre un résultat à la structure prédéfinie.
GraphQL permet d'intéroger la base de données à partir d'un endpoint et de définir la structure de la réponse attendue directement dans la requête.


- les besoins auxquels répond GraphQL ✔️

GraphQL est un bon choix architectural si l’application fait appel à de nombreuses requêtes.
Là où REST nécessiterai l'aménagement d'un endpoint par requête, GraphQL permet de tous les regrouper en un seul, la structure de la réponse étant portée par la requête elle-même.

- la définition d'un schéma

Le schéma permet de définir la structure de la donnée attendue dans l'utilisation d'une API GraphQL. Il se définit en amont de la requête de la façon suivante:

```javascript
type Character {
  name: String!
  appearsIn: [Episode!]!
}
```


- Query ✔️

Dans le cas d'une API GraphQL, on appelle Query les requêtes qui ont un objectif de lecture seule des données (équivaut à un GET en API REST)


- Mutation ✔️

Une mutation regroupe les actions ayant pour but d'influer sur la base de données. Cette appellation regroupe les verbes HTTP POST, PUT, et DELETE.

- Subscription ✔️

Une subscription GraphQL permet la lecteur de la base de données mais à la différence des Queries, son résultat suit les variations de la base de données. Elle permet de maintenir une connection activer avec le serveur afin de recueillir ses mises à jour par le biais des WebSockets.


## 💻 J'utilise

### Un exemple personnel commenté ❌ / ✔️

### Utilisation dans un projet ✔️

[lien github](https://github.com/WildCodeSchool/2209-wns-adleman-bordolamif)

Description :

UserQuery côté frontend (définition du schéma)

```javascript
export const GET_ALL_USERS = gql`
query GetAllUsers {
  getAllUsers {
    id
    firstname
    lastname
    email
    role
    isFirstLogin
    isSuspended
    services {
      acronym
      color
      id
      name
      isOpen
    }
    counter {
      id
      name
    }
    tickets {
      id
      name
      createdAt
      calledAt
      closedAt
      isFirstTime
      isReturned
      status
    }
    currentService {
      acronym
      color
      id
      name
      isOpen
    }
  }
}
`;
```

UserResolver côté backend (définition de requêtes utilisables)
```javascript
@Resolver(User)
export class UserResolver {

  @Query(() => [User])
  async getAllUsers(): Promise<User[]> {
    const users = await UserController.getAllUsers();
    return users.map((user) => getSafeAttributes(user));
  }

  ...}
```


### Utilisation en production si applicable❌ / ✔️

[lien du projet](...)

Description :

### Utilisation en environement professionnel ❌ / ✔️

Description :

## 🌐 J'utilise des ressources

### Titre

- lien : https://graphql.org/
- description : documentation officielle GraphQL

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
