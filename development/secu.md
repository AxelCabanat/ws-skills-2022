# Sécurité dans le développement Web

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- Le rôle de l'OWASP ✔️

L'OWASP (Open Web Application Security Project) est une communauté mondiale à but non lucratif qui se concentre sur l'amélioration de la sécurité des applications Web. Son rôle principal est de sensibiliser, de former et de fournir des ressources pour aider les professionnels et les organisations à créer des applications Web plus sécurisées. L'OWASP accomplit cela en proposant des programmes de sensibilisation à la sécurité, en développant des ressources open source, en fournissant des formations et en encourageant l'adoption de meilleures pratiques de sécurité. L'organisation facilite également la collaboration et le partage de connaissances entre les experts en sécurité et les développeurs du monde entier.

- Les injections SQL ✔️

Les injections SQL sont une technique dangereuse où des données non validées sont insérées dans des requêtes SQL, permettant aux attaquants d'exécuter du code SQL non autorisé. Cela peut conduire à l'accès non autorisé, la modification ou la suppression de données sensibles. Pour se protéger contre les injections SQL, il est essentiel de valider et filtrer les données d'entrée, d'utiliser des requêtes préparées, de mettre en place une gestion des privilèges appropriée, de maintenir les logiciels à jour et de former les développeurs sur les meilleures pratiques de sécurité.

- XSS ✔️

Une faille XSS (Cross-Site Scripting) est une vulnérabilité où du code script malveillant est injecté dans des pages Web, permettant aux attaquants d'exécuter des actions nuisibles sur les navigateurs des utilisateurs. Cela peut entraîner le vol de données, la falsification de contenu ou le détournement de sessions utilisateur. Pour prévenir les failles XSS, il est important de valider et d'échapper les données, d'utiliser des protections au niveau du navigateur, de filtrer et valider côté serveur, et de sensibiliser les développeurs aux meilleures pratiques de sécurité.

- CRSF ✔️

CSRF (Cross-Site Request Forgery) est une attaque où des actions non autorisées sont effectuées sur des utilisateurs authentifiés via des requêtes forgées. Pour se protéger contre les attaques CSRF, il faut utiliser des jetons anti-CSRF, vérifier les référents, respecter la politique de même origine et éduquer les utilisateurs sur les bonnes pratiques de sécurité.

## 💻 J'utilise

### Un exemple personnel commenté ✔️

Précautions prises dans la mise à jour d'un ticket

TicketResolver

```javascript
// Autorisation en fonction de roles utilisateur
  @Authorized<RoleEnum>([RoleEnum.ADMINISTRATEUR, RoleEnum.OPERATEUR])
  @Mutation(() => Ticket)
  async updateTicket(
    // vérification du type des arguments
    @Arg('id', () => Int) id: number,
    @Arg('data') data: TicketInput,
    @PubSub() pubsub: PubSubEngine,
  ): Promise<Ticket> {
    const updatedTicket = await TicketController.updateTicket(data, id);
    await pubsub.publish('UpdatedTicket', updatedTicket);
    return updatedTicket;
  }
```
TicketController
```javascript
  updateTicket: async (data: TicketInput, id: number) => {
    // récupération des seules données nous intéressant
    const {
      status, isFirstTime, user, service,
    } = data;

    // vérification de l'id
    const ticketToUpdate = await TicketModel.getOneTicketById(id);

    if (ticketToUpdate === null) {
      throw new Error('Ticket not found');
    }

// Attribution du statut selon un ENUM
    ticketStatusUpdater(ticketToUpdate, status);

// Récupération de entités liées par référence
    ticketToUpdate.isFirstTime = isFirstTime;
    if (user) {
      ticketToUpdate.user = (await UserModel.getOneArgUser(user.id)) || null;
    }
    ticketToUpdate.service = (await ServiceModel.getOneArgService(service.id)) || null;

    await TicketModel.updateTicket(ticketToUpdate);

    return ticketToUpdate;
  },
```

TicketModel

```javascript
// Utilisation d'un ORM et se processus sécurisés pour s'adresser à la base de donnée
  updateTicket: async (ticketToUpdate: Ticket) => await
  dataSource.getRepository(Ticket).save(ticketToUpdate),
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
