# Titre de la compétence

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- les différences et points communs entre du code react et du code react native ✔️

React est utilisé pour développer des applications web interactives en utilisant des composants réutilisables, tandis que React Native est utilisé pour développer des applications mobiles natives pour iOS et Android en utilisant du code JavaScript. Les deux utilisent une syntaxe similaire et permettent la réutilisation des composants. Cependant, certains composants de React Native sont spécifiques à chaque plateforme et offrent un accès direct aux fonctionnalités du système d'exploitation, ce qui permet une meilleure performance et une expérience utilisateur plus fluide.

- ce que devient et comment est interprêté le code javascript dans une application react native ✔️

Dans une application React Native, le code JavaScript est exécuté par un moteur JavaScript intégré dans l'application native. Le moteur JavaScript interprète le code, génère l'interface utilisateur native et effectue des opérations spécifiques à la plateforme. Ainsi, le code JavaScript est responsable de la création des composants et de la gestion des états, tandis que l'application native se charge de la génération de l'interface utilisateur réelle.

- les avantages et inconvénients de react native ✔️

React Native offre des avantages tels que le développement multiplateforme avec un codebase commun, des performances proches de celles des applications natives, la réutilisation des compétences en React, une communauté active et un écosystème robuste, ainsi que des mises à jour facilitées. Cependant, il présente des inconvénients tels que des performances limitées pour certaines fonctionnalités avancées, une dépendance aux mises à jour de React Native, une nécessité de connaître le développement natif dans certains cas, et une taille d'application plus importante.

- la différence entre react native et expo ✔️

React Native est un framework qui permet de développer des applications mobiles natives en utilisant JavaScript et React, offrant une flexibilité et des performances avancées. Expo est un framework basé sur React Native qui simplifie le développement en fournissant des outils supplémentaires et en abstrayant certaines complexités, ce qui permet un développement rapide et facile, mais avec certaines limitations en termes de personnalisation et de performances avancées.

- les principales briques qui composent react native (core components) ✔️

Le core components sont des éléments d'interface utilisateur prédéfinis utilisés pour construire des applications mobiles.
Voici les principaux :

    View :
    Le composant View est l'équivalent d'un conteneur de vue dans une application mobile. Il est utilisé pour créer une zone rectangulaire sur l'écran où vous pouvez placer d'autres éléments (à l'instar d'une <div> en React).

    Text :
    Le composant Text est utilisé pour afficher du texte à l'écran. Il permet de styliser et de formater le texte en utilisant des propriétés telles que la taille de police, la couleur, etc. React décline ses balises textuelles via différentes instances hiérarchisées (<h1>, <h2>, <p>, <span>, etc...)

    Image :
    Le composant Image est utilisé pour afficher des images dans l'application. Il permet de charger et d'afficher des images à partir de différentes sources, telles que des fichiers locaux ou des URL distantes, tout comme la balise <img>.

    TextInput :
    Le composant TextInput est utilisé pour la saisie de texte. Il permet à l'utilisateur d'entrer du texte à partir du clavier de l'appareil et offre des fonctionnalités telles que la validation de saisie et la gestion d'événements liés à la saisie. En React, la balise <input> peut se voir attitrer un type spécifique afin de préciser le besoin auquel il répond et le comportement qui en découle (exemple avec les types "text" et "password")

    ScrollView :
    Le composant ScrollView est utilisé pour afficher une liste ou du contenu défilable. Il permet d'afficher une grande quantité de contenu en le faisant défiler verticalement ou horizontalement. Sans réel équivalent React, on utiliserait une <div> avec une propriété CSS overflow: scroll pour créer une zone défilable qui affiche du contenu.

    Pressable :
    Le composant Pressable est utilisé pour créer des éléments interactifs dans l'application. Il permet de définir des zones tactiles qui répondent aux actions de l'utilisateur, telles que les pressions ou les clics. Si sémantiquement la balise correspondant serait un <button>, on peut également associer un comportement à d'autres composants via l'attribu onClick pour les rendre interractifs.

    StyleSheet :
    StyleSheet est un module intégré à React Native qui permet de définir et de gérer les styles des composants. Il offre une syntaxe similaire aux feuilles de style CSS, permettant de définir les propriétés de style des composants. Si le style est applicable via des classNames, on peut également le définir via l'attribu "style" d'un composant.


- comment écrire du style en react native ✔️

L'écriture du style en React Native se fait via l'utilisation de l'objet StyleSheet, généralement après la description de notre composant comme suit :

```javascript

const styles = StyleSheet.create({
  container: {
    position: 'relative',
    flex: 1,
    backgroundColor: 'black',
  },
  alertText: {
    textAlign: 'center',
    textAlignVertical: 'center',
    fontSize: 10,
  },
});

```

Les noms de propriétés et les valeurs des styles en React Native sont généralement similaires à ceux du CSS standard, mais avec certaines différences. Par exemple, au lieu d'utiliser des tirets comme dans le CSS (background-color), on utilise la notation camelCase (backgroundColor)

- comment est géré le layout en react native ✔️

Le layout en React Native est géré principalement par deux concepts : le système de flexbox et les composants fournis par React Native.

    Le système de flexbox est utilisé pour positionner et aligner les éléments dans un conteneur en spécifiant les propriétés telles que flex, flexDirection, justifyContent, alignItems, etc.

    Les composants de base tels que View, Text, Image, etc., sont utilisés pour structurer l'interface utilisateur de l'application et peuvent être stylisés à l'aide de propriétés CSS-like.
    Les composants spécifiques à React Native, tels que ScrollView et FlatList, permettent quant à eux de gérer des mises en page plus avancées, comme l'affichage de contenu défilable ou de listes d'éléments.

## 💻 J'utilise

### Un exemple personnel commenté ✔️
Composant QrCodeScanner
Notons que le style est en majorité assuré par tailwindcss
Ici commenté les comportements semblables (✔️) et différents (❌) de React

```javascript
// déclaration des props ❌
type NavigationProps = NativeStackScreenProps<RootStackParamList, 'QrCodeScanner'>;

// déclaration du fonctionnal component ✔️
export default function QrCodeScanner({ navigation }: NavigationProps) {

    // mise en place des states ✔️
  const [hasPermission, setHasPermission] = useState<boolean | null>(null);
  const [scanned, setScanned] = useState<boolean>(false);

// mise en place d'un useEffect pour gérer les comportements au montage du composant ✔️
  useEffect(() => {
    const getBarCodeScannerPermissions = async () => {
      const { status } = await BarCodeScanner.requestPermissionsAsync();
      setHasPermission(status === 'granted');
    };

    getBarCodeScannerPermissions();
  }, []);

  // déclaration d'une fonction ✔️

  const handleBarCodeScanned = ({ data } : { data: string }) => {
    setScanned(true);

    if (!data) {
      return console.warn('No data found');
    }

    return navigation.navigate('ServicesSelectionScreen', { waitingRoomId: data });
  };

  return (
    <BarCodeScanner
      onBarCodeScanned={scanned ? undefined : handleBarCodeScanned}
      style={[StyleSheet.absoluteFillObject, styles.container]}
    >
    {/* Equivalent <button> ❌ */}
      <Pressable
        className="ml-6 mt-14"
        onPress={() => navigation.goBack()}
      >
        <AntDesign name="left" size={28} color="white" />
      </Pressable>
      <BarCodeScannerLens />
      {scanned
        && (
        <Pressable
          className="border-white border-2 rounded-xl mx-auto w-2/3"
          onPress={() => setScanned(false)}
        >
        {/* Equivalent <p> ou <h1> ❌ */}
          <Text className="py-4 text-white f-xl-center">Appuyer pour scanner à nouveau</Text>
        </Pressable>
        )}
      {hasPermission === null
          && <Text style={styles.alertText}>Demande d'autorisation d'accées à la caméra</Text>}
      {!hasPermission
          && <Text style={styles.alertText}>L'application n'a pas accées à la caméra</Text>}
          {/* Equivalent <div> ❌ */}
      <View
        className="absolute flex flex-row justify-center w-full"
        style={{ top: 650 }}
      >
        <Text className="text-white font-bold text-5xl">Wait</Text>
        <Text className="text-orange-500 text-5xl">it</Text>
      </View>
    </BarCodeScanner>
  );
}

// Déclaration du style ❌
const styles = StyleSheet.create({
  container: {
    position: 'relative',
    flex: 1,
    backgroundColor: 'black',
  },
  alertText: {
    textAlign: 'center',
    textAlignVertical: 'center',
    fontSize: 10,
  },
});
```

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
