# Titre de la compétence

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- l'état (_state_) pour contrôler l'affichage d'un composant ✔️

"Le hook useState de React permet de générer un state, un variable réactive composée de ladite variable et d'une fonction pour l'actualiser. Ainsi , à l'utilisation de la fonction d'actualisation la variable se voit modifiée à l'écran sans rechargement de l'écran. Il peut s'agir d'une chaîne de caractère comme d'un booléen conditionnant l'affichage ou non d'un composant ou d'un tableau d'objets à afficher sur notre page."

- les composants enfants et les _props_ qu'on leur passe ✔️

"La partie render d'un composant React permet de faire appel à d'autre composant pour par exemple conditionner l'affichage de données. L'appelant est alors désigné comme "composant parent", et l'appelé "composant enfant". Outre pour des soucis d'affichage, ce système hiérarchique entre également en jeu dans la transmission de données. Imaginons par exemple une page (composant parent) faisant appel à des cartes (enfants) pour afficher ses données. Les données à affichées détenues par le parent sont transmises individuellement aux enfants lors de leur appel. Les enfants quant à eux s'attendent à recevoir la donnée d'un parent afin de l'intégrer à leur propre fonctionnement. Ces données transmises de parent à enfants s'appelle des "props" et fonctionnent toujours par transmission de l'appelant vers l'appelé."

- le déclenchement d'instructions en fonction des actions de l'utilisateur ✔️

"Le format jsx permet l'utilsation du XML partie rendu. Ce langage permet notamment l'appel de fonctions lors d'évènements utilisateurs. Si une logique de traitement de formulaire et d'envoi de ses champs en base de données peut être définie avant la partie render, cette dernière peut faire appel à cette logique, par exemple grâce à l'option "onClick" d'un bouton."

- le déclenchement d'instructions en fonction de l'étape du cycle de vie du composant ou du changement de valeur de ses props ✔️

"Le hook useEffect permet de déclencher des instructions en fonction du cycle de vie du composant (lors de son montage ou de son démontage) mais également lors de l'actualisation d'un valeur. Pour effectuer l'équivalement d'un componentDidMount(), le hook prendra un tableau de dépendance vide en argument. La logique de componentWillUnmount() se trouvera dans un return dans le scope du hook. Si nous voulons que la logique du hook s'applique lorsque qu'une valeur change, il nous faudra mettre cette variable dans le tableau de dépendance pour que useEffect écoute l'état de cette dernière."

- l'usage d'un reducer (_useReducer_) pour gérer un état composé dans un composant ✔️

Le hook useReducer permet d'associer plusieurs traitements logiques à un state.
Comme illustré ci-dessous, une fonction reducer concentrera les différents traitements à appliquer au state à l'appel du dispatch
```javascript
import { useReducer } from 'react';

function reducer(state, action) {
  if (action.type === 'incremented_age') {
    return {
      age: state.age + 1
    };
  }
    if (action.type === 'decremented_age') {
    return {
      age: state.age - 1
    };
  }
  throw Error('Unknown action.');
}

export default function Counter() {
  const [state, dispatch] = useReducer(reducer, { age: 32 });

  return (
    <>
      <button onClick={() => {
        dispatch({ type: 'incremented_age' })
      }}>
        Increment age
      </button>
            <button onClick={() => {
        dispatch({ type: 'decremented_age' })
      }}>
        Decrement age
      </button>
      <p>Hello! You are {state.age}.</p>
    </>
  );
}

```

- l'état stocké dans un composant avec un _context provider_ et accessible dans ses descendants via `useContext` ✔️

"Un context est un espace dans lequel peuvent être stockés des données et traitements logiques. A chaque context est associé un provider matérialisé sous forme de balises qui viendra englober le scope du contenu du provider. Ainsi un composant compris entre les balises d'un provider pourra faire appel au contenu de son context sans passer par une transmisson de props. Les enfants d'un composant exposé au provider se verront bénéficier des mêmes accès au context que leur parent."

## 💻 J'utilise

### Un exemple personnel commenté ✔️

Hook custom destiné à gérer le comportement des fenêtres modales

```javascript
import { useState } from 'react';

const useModal = () => {
    // initialisation du state
  const [isModalOpen, setIsModalOpen] = useState(false);

    // fonction commandant l'ouverture de la modale
  const openModal = () => setIsModalOpen(true);

    // fonction commandant la fermeture de la modale
  const closeModal = () => setIsModalOpen(false);

    // Elements accessibles via l'appel du hook
  return { isModalOpen, openModal, closeModal };
};

export default useModal;
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
