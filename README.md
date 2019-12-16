# À propos de ce document

React Boilerplate est un environnement de travail React préconfiguré pour le développement et le déploiement en production d’applications de toutes tailles.
Cet ensemble outils React créé par Max Stoiber présente de nombreux avantages comme: 
Rester concentrer sur son code et mettre l'accent sur les performances
Adopter des pratiques de programmation inspirées des meilleurs développeurs.
Garantir automatiquement la qualité du code et des modifications.
Prendre en charge le référencement 
Développer des Application Web native.
Charger les polices de caractère plus rapidement
De gagner du temps (beaucoup de temps… )

Malheureusement, la prise-en-main du boilerplate peut sembler complexe aux non-initiés et encore plus aux non-anglophones. 

L'objectif de ce document sera donc principalement de proposer une traduction intégrale et en français de la documentation officielle de React Boilerplate et accessoirement de démystifier l’utilisation de React Boilerplate via des leçons et des exercices pratiques.

# Table des matières
- [1. Général](general)
  - [1.1. Commandes CLI](general/commands.md)
  - [1.2. Introduction ](general/introduction.md)
  - [1.3. Configuration: fichiers](general/files.md)
  - [1.4. Configuration serveur](general/server-configs.md)
  - [1.5. Déploiement](general/deployment.md)
  - [1.6. Débogage](general/debugging.md)
  - [1.7. Questions fréquemment posées](general/faq.md)
  - [1.8. Écueils](general/gotchas.md)
  - [1.9. Suppression](general/remove.md)
  - [1.10. Extraction de composants](general/components.md)
- [2. Tests](testing)
  - [2.1. Test Unitaire](testing/unit-testing.md)
  - [2.2. Test des composants](testing/component-testing.md)
  - [2.3. Test à distance](testing/remote-testing.md)
- [3. Style (CSS)](css/README.md)
  - [3.1. CSS nouvelle génération](css/README.md#next-generation-css)
  - [3.2. Support CSS](css/README.md#css-we-support)
  - [3.3. styled-components](css/README.md#styled-components)
  - [3.4. Feuilles de style](css/README.md#stylesheet)
  - [3.5. Modules CSS](css/README.md#css-modules)
  - [3.6. Sass](css/README.md#sass)
  - [3.7. LESS](css/README.md#less)
- [4. JavaScript](js)
  - [4.1. Redux](js/redux.md)
  - [4.2. Immer](js/immer.md)
  - [4.3. reselect](js/reselect.md)
  - [4.4. Redux-saga](js/redux-saga.md)
  - [4.5. i18n](js/i18n.md)
  - [4.6. Routage](js/routing.md)
- [5. Maintenance](maintenance)
  - [5.1. Mettre à jour les Dépendances](maintenance/dependency.md)
- [6. Forks](forks)

## Vue d'ensemble

### Démarrage rapide

1.  Commençons en lançant l'exemple d'application _Repospective_ fourni avec ce projet pour faire la démonstration de certaines de ses meilleures fonctionnalités:

    ```Shell
    npm run setup && npm start
    ```

1.  Ouvrez [localhost:3000](http://localhost:3000) pour voir l’exemple en action...

    - Ajoutez un nom d'utilisateur Github pour voir Redux et Redux Sagas en action: les mises à jour asynchrone de l'état sans effort et les effets de bord sont maintenant à vous :)
    - Modifiez le fichier `./app/components/Header/index.js` pour que le texte du composant `<Button>` affiche "Features !!!" ... Le [rechargement à chaud du module](https://webpack.js.org/guides/hot-module-replacement/) vous donne une boucle de rétroaction avec votre interface utilisateur si lisse qu'elle est presque conversationnelle !
    - Cliquez sur votre bouton Features (nouvellement vigoureux) pour voir React Router en action... Vous pouvez maintenant partager un lien direct vers ce contenu en privé sur votre réseau local ou adressable globalement à n'importe quel appareil, n'importe où. Pas mal pour une application monopage exécutée localement.

1.  Il est temps de créer votre propre application: lancez

    ```shell
    npm run clean
    ```

    ... et utilisez les générateurs intégrés pour débuter votre première fonctionnalité.

### Development

Exécutez `npm start` pour voir votre application fonctionner sur `localhost:3000`

### Compilation et déploiement

1.  Lancez `npm run build`, cela compilera tous les fichiers nécessaires dans le dossier
    `build`.

2.  Envoyez le contenu du dossier `build` dans le dossier racine de votre serveur Web.

### Structure

Le dossier [`app/`](../../../tree/master/app) contient l'intégralité de votre code d'application, y compris CSS, JavaScript, HTML et tests. 

Les autres dossiers et fichiers n'existent que pour vous faciliter la vie et ne doivent pas être touchés.

_(S'ils doivent être modifiés, veuillez [soumettre le problème](https://github.com/react-boilerplate/react-boilerplate/issues)!)_

### CSS
En utilisant des [littéraux de modèle balisés](https://www.styled-components.com/docs/advanced#tagged-template-literals) (un ajout récent à JavaScript) et la [puissance de CSS](https://github.com/styled-components/styled-components/blob/master/docs/css-we-support.md), les `styled-components` vous permettent d'écrire du code CSS réel pour styliser vos composants. 
Il supprime également le mappage entre les composants et les styles - l'utilisation de composants comme construction de style 
de bas niveau ne pourrait pas être plus facile ! 

Voir la [documentation CSS](./css/README.md) pour plus d'informations. 

### JS
Nous regroupons tous vos scripts côté client et les découpons en plusieurs fichiers en utilisant le fractionnement de code lorsque cela est possible. Nous optimisons ensuite automatiquement votre code lors de la compilation pour la production afin que vous n'ayez pas à vous en soucier. 

Consultez la [documentation JS](./js/README.md) pour plus d'informations sur le côté JavaScript des choses. 

### SEO
Nous utilisons [react-helmet](https://github.com/nfl/react-helmet) pour gérer les balises <head> de document. Des exemples sur la façon d'écrire les balises head peuvent être trouvés [ici](https://github.com/nfl/react-helmet#examples).
  
### Test 
Pour une explication approfondie de la procédure de test, consultez la documentation de [test](./testing/README.md)! ! 
  
### Test navigateur 
`npm run start:tunnel`rend votre application exécutée localement disponible globalement sur le Web via une URL temporaire: idéal pour tester sur différents appareils, démos client, etc. ! 
  
### Tests unitaires 
Les tests unitaires se trouvent dans les répertoires `test/` juste à côté des composants testés et sont exécutés avec `npm run test`.
