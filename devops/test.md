# Tester son application

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- les tests unitaires ✔️

 Consiste à tester individuellement les plus petites unités de code afin de vérifier leur fonctionnement correct. L'objectif principal des tests unitaires est de s'assurer que chaque unité de code fonctionne comme prévu, de manière isolée, indépendamment des autres parties du système. Cela permet de détecter rapidement les erreurs ou les comportements non désirés au niveau de chaque unité, facilitant ainsi la détection et la correction des problèmes.

- les mocks ✔️

 Ce sont des objets simulés utilisés dans les tests unitaires pour remplacer des composants réels sur lesquels une unité de code dépend. Lorsqu'une unité de code est testée, les mocks sont utilisés pour simuler le comportement des dépendances et fournir des réponses préprogrammées. Cela permet d'isoler l'unité de code testée et de vérifier son fonctionnement de manière indépendante.

- les tests d'integration ✔️

 Ils visent à vérifier le bon fonctionnement des différentes composantes d'un système lorsqu'elles sont combinées et interagissent les unes avec les autres. Contrairement aux tests unitaires qui se concentrent sur des unités de code individuelles, les tests d'intégration examinent les interactions et les flux de données entre plusieurs composantes du système. 

- les tests de bout en bout (end to end) ✔️

 Ils visent à évaluer le fonctionnement global d'un système du début à la fin, en simulant des scénarios d'utilisation réels. Contrairement aux tests d'intégration qui vérifient les interactions entre les composantes du système, les tests de bout en bout examinent l'ensemble du flux de travail ou du parcours utilisateur, en testant toutes les couches et les fonctionnalités du système.

 Les tests de bout en bout offrent une vue d'ensemble du fonctionnement du système et permettent de valider le flux complet des fonctionnalités, mais ils peuvent être plus lents et plus coûteux à exécuter que les autres types de tests.

- le TDD ✔️

 Le TDD (Test-Driven Development) est une approche de développement qui met l'accent sur l'écriture des tests unitaires avant d'écrire le code de production. 
 Tout d'abord, un test unitaire est écrit pour définir le comportement attendu d'une unité de code. Ce test est généralement simple et vérifie un aspect spécifique de la fonctionnalité à développer.
 Puis le code est implémenté pour faire passer les tests, et si les tests sont vérifiés le code peut être refactoré si nécessaire.

 Le TDD offre plusieurs avantages, notamment une meilleure qualité du code, une meilleure conception logicielle, une réduction des erreurs, une meilleure compréhension des exigences et une plus grande confiance dans le fonctionnement du système.

 Cependant, il est important de noter que le TDD peut demander plus de temps et d'efforts pour écrire les tests avant de coder. 


- les tests par snapshot ❌ / ✔️

## 💻 J'utilise

### Un exemple personnel commenté ✔️

Extrait des tests du ServiceResolver

```javascript
//définition de la mutation

export const CREATE_SERVICE = gql`
mutation CreateService($data: ServiceInput!) {
  createService(data: $data) {
    id
    name
    color
    acronym
    isOpen
    waitingRoom {
      id
      name
    }
  }
}
`;

//définition des mocks

const firstServiceInput = {
  name: 'Service1',
  acronym: 'SV1',
  isOpen: false,
  color: '#ffffff',
};

const secondServiceInput = {
  name: 'Service2',
  acronym: 'SV2',
  isOpen: false,
  color: '#eeeeee',
};

const waitingRoomInput = { name: 'Wait1' };

// Début des tests

describe('Service Resolver', () => {
    // Fonction à tester
  describe('Create Service', () => {
    // En cas de succès
    describe('Success cases', () => {
        // Description du résultat attendu
      it('1. should create a ticket', async () => {
        // Création de l'entité lié via l'API de l'ORM afin d'isoler le test
        const waitingRoom = await dataSource.getRepository(WaitingRoom).save(waitingRoomInput);
        // Test de la mutation sans entité liée
        const res1 = await client.mutate({
          mutation: CREATE_SERVICE,
          variables: {
            data: {
              ...firstServiceInput,
            },
          },
        });
        // Test de la mutation avec entité liée
        const res2 = await client.mutate({
          mutation: CREATE_SERVICE,
          variables: {
            data: {
              ...secondServiceInput,
              waitingRoom: { id: waitingRoom.id },
            },
          },
        });

        //Résultat attendu pour chaque cas
        expect(res1.data?.createService).toHaveProperty('id');
        expect(res1.data?.createService).toHaveProperty('name', 'Service1');
        expect(res1.data?.createService).toHaveProperty('acronym', 'SV1');
        expect(res1.data?.createService).toHaveProperty('isOpen', false);
        expect(res1.data?.createService).toHaveProperty('color', '#ffffff');

        expect(res2.data?.createService).toHaveProperty('id');
        expect(res2.data?.createService).toHaveProperty('name', 'Service2');
        expect(res2.data?.createService).toHaveProperty('acronym', 'SV2');
        expect(res2.data?.createService).toHaveProperty('isOpen', false);
        expect(res2.data?.createService).toHaveProperty('color', '#eeeeee');
        expect(res2.data?.createService.waitingRoom).toHaveProperty('id', waitingRoom.id);
      });
    });
    describe('Error cases', () => {
        // En cas d'échec
      it('1. should throw a waiting room not found error', async () => {
        try {
        // Test de la mutation avec entité liée mais sans création préalable
          await client.mutate({
            mutation: CREATE_SERVICE,
            variables: {
              data: {
                ...firstServiceInput,
                waitingRoom: { id: 1 },
              },
            },
          });
          // Déclenchement d'une erreur afin de tomber dans le catch
          expect(true).toBe(false);
        } catch (e) {
        // Résultats attendus
          expect(e).toBeDefined();
          expect(e.graphQLErrors).toBeDefined();
          expect(e.graphQLErrors.length).toBeGreaterThan(0);
          expect(e.graphQLErrors[0].message).toMatch('WaitingRoom not found');
        }
      });
    });
  });

// Et ainsi de suite avec chaque fonction du resolver
});
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
