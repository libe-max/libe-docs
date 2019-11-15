# Notions générales pour le développement d'outils Libé Labo

Quelques informations d'ordre général avant de se lancer dans le développement ou la mise à jour d'outils ou de formats Libé Labo.

## Sommaire
- [Architecture globale des outlis Libé Labo](https://github.com/libe-max/Docs/blob/master/technical-guidelines-overview.md#architecture-globale)
- [Choix techniques](https://github.com/libe-max/Docs/blob/master/technical-guidelines-overview.md#choix-techniques)
- [Nomenclature et mise en forme du code](https://github.com/libe-max/Docs/blob/master/technical-guidelines-overview.md#nomenclature-et-mise-en-forme)
- [Publication & versionnement](https://github.com/libe-max/Docs/blob/master/technical-guidelines-overview.md#publication--versionnement)

## Architecture globale

Les principaux projets techniques de Libé Labo et la façon dont ils interagissent entre eux est décrite dans le tableau et le schéma ci-dessous.

| Nom                                                          | Description                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [libe-apps-template](https://github.com/libe-max/libe-apps-template) | Application React. Socle commun pour tous les formats récents de Libé Labo. |
| [libe-components](https://github.com/libe-max/libe-components) | Module npm, contient différents composants réutilisables pour les formats (`<Paragraph />`, `<PageTitle />`, `<Tweet />`, etc, ...) |
| [libe-utils](https://github.com/libe-max/libe-utils)         | Module npm, contient des fonctions JavaScript génériques utilisées par tous les formats (`parseTsv()`, `parseCookies()`, `getClosestDomParent()`, etc, ...) |
| [libe-static-ressources](https://github.com/libe-max/libe-static-ressources) | Dossier de fichiers statiques (css, svg, etc, ...), hébergés sur https://www.liberation.fr/apps/static/ |
| [libe-data-server](https://github.com/libe-max/libe-data-server) | Application Express hébergée sur https://libe-labo-2.site, permettant de fournir et stocker (MongoDb) de la donnée pour les formats |
| [libe-tools](https://github.com/libe-max/libe-tools)         | Application Express (back) et React (front) fournissant des éditeurs visuels pour permettre à la rédaction de créer des formats simplement |

![Schéma de l'architecture globale des outils de Libé Labo](https://github.com/libe-max/Docs/raw/master/assets/applications-scheme.jpg)

## Choix techniques

- Les applications client sont construites avec [React](https://reactjs.org/), par le biais de [create-react-app](https://reactjs.org/docs/create-a-new-react-app.html).
- Les applications serveur sont des applications [Express](https://expressjs.com/), exécutées par [Node.js](https://nodejs.org/en/).
- Les dépendences et scripts des projets client et serveur sont géré•e•s avec [NPM](https://www.npmjs.com/).
- Les applications de base de données sont des applications [MongoDB](https://www.mongodb.com/).

Certains projets ont à leur racine des scripts de démarrage, compilation ou publication. Ces scripts peuvent être des scripts [Shell](https://en.wikipedia.org/wiki/Shell_script), [Python](https://en.wikipedia.org/wiki/Python_(programming_language)), ou [JavaScript](https://en.wikipedia.org/wiki/JavaScript) éxécutables par [Node.js](https://nodejs.org/en/).

**Attention :** ces scripts n'ont pas vocation à être éxécutés directement, ils doivent avoir leur commande npm dédiée dans `[PROJET]/package.json` (ex : `scripts: { build: node build.js }`).

Dans le cadre des applications React (à l'exception du projet [Libé Tools front](https://github.com/libe-max/libe-tools-front)), et au sujet des outils de CSS modulaire (ex : [styled-components](https://www.styled-components.com/)). Chaque modification de CSS entraînant nécessairement une nouvelle compilation du code, la solution du CSS modulaire est écartée, ne permettant pas de traiter simplement un chamgement de style à appliquer sur toute la production Libé Labo. La solution retenue est d'inclure de manière traditionnelle (par une balise link dans le head du document) des styles communs entre les applications (voir [Libé Static Ressources](https://github.com/libe-max/libe-static-ressources)).

De manière générale, les intentions sont :
- Maintenir une organisation simple et descriptive des dossiers et fichiers source.
- Refuser tout choix technologique impliquant d'installer et/ou configurer un transpileur. Liste non exhaustive des technologies exclues : Webpack, TypeScript, tout pré-processeur de CSS, Mustache, Pug, etc.
- Limiter au maximum l'installation de dépendances, quand une solution peut être développée à la main.

## Nomenclature et mise en forme

- Tous les dossiers et fichiers de code doivent être nommés en [lower-dash-case](https://en.wikipedia.org/wiki/Letter_case#Special_case_styles).
- Un fichier javascript contenant des exports doit être nommé selon le nom de l'objet exporté par défaut (converti en [lower-dash-case](https://en.wikipedia.org/wiki/Letter_case#Special_case_styles)).
- Pour les composants React, ils sont exportés dans le dossier components, à l'interieur d'un dossier nommé selon le composant exporté en [PascaleCase](https://en.wikipedia.org/wiki/Letter_case#Special_case_styles), sous le nom de index.js, soit : `[PROJET]/src/components/MonComposantReact/index.js`.

### HTML
- Valide W3C
- Indentation à 2 espaces
- Pas de lignes vides sauf au dessus d'une ligne de commentaire
- Les valeurs des attributs  `<tag attribut="valeur">` sont délimitées par des guillemets informatiques doubles.

### CSS
- Les classes des composants doivent suivre la nomenclature de la [BEM methodology](https://en.bem.info/methodology/)

- Par convention, dans chaque application, `1rem === 16px`, et les propriétés responsive sont définies en **max-width** autour de deux breakpoints : `63rem` (1008px) et `40rem` (640px).

- Un "block" au sens de la BEM ne doit pas se préoccuper pas de ce qui est en dehors de lui. Les propriétés margin, width, height et position ne peuvent pas être définies à ce niveau.

- Pour chaque bloc, le css décrit dans l'ordre :

  - les propriétés générales :

    ```css
    .bloc .bloc__element { color: red; }
    ```

  - les effets des modifieurs :

    ```css
    .bloc.bloc_modifier .bloc__element { color: blue; }
    ```

  - les propriétés responsive :

    ```css
    @media screen and (max-width: 63rem) {
      .bloc .bloc__element { color: yellow; }
      .bloc.bloc_modifier .bloc__element { color: green; }
    }
    ```

### JavaScript

Tout le JavaScript produit doit être conforme au standard [ES6]([http://es6-features.org](http://es6-features.org/)), avec possibilité d'utiliser certains éléments plus récents (ex : `async`, `await`), puisque le code est transpilé avant d'être déployé en production.

Le code exécuté par Node.js importe et exporte des modules à la façon [CommonJS](https://fr.wikipedia.org/wiki/CommonJS) :

```javascript
const module = require('module')
function myFunc (param) { /* Do some crazy stuff */ }
module.exports = myFunc
```

Le code éxécuté par les navigateurs importe et exporte à la façon ES6 (puisque transpilé avant mise en production) :

```javascript
import module from 'module'
function myFunc (param) { /* Do some crazy stuff */ }
export default myFunc
```

Le code produit doit passer les tests de [standardjs](https://standardjs.com/) (chaque projet contient dans son `package.json` un script `"standard-fix": "standard --fix --verbose | snazzy"`).

### Commits
Les noms de commits doivent être en minuscule, nommés comme une action au présent (`update dependencies` plutôt que `Updated dependencies`), descriptifs autant que possible, et préfixés par le nom de fichier ou de la partie de l'application concernée si le commit ne concerne qu'une partie de l'application (ex : `"parse-tsv.js – trim input data"`). Idéalement, si le travail est mené à plusieurs sur un projet, la branche master ne contient que des merge d'autres branches.

## Publication & versionnement

Les projets ayant vocation à être utilisés comme dépendances d'autres projets (libe-static-ressources, libe-components, libe-utils, libe-apps-template, etc...) doivent être versionnés. Le process est le suivant :

- des modifications au code sont apportées et les commits correspondants sont correctement nommés et pushés sur GitHub.
- une fois le code testé et passé par standardjs (si nécessaire, nommer le commit `"run standardjs"`), il faut changer le champ `version` dans `package.json`. Le nouveau numéro de version doit suivre la règle du [semantic versionning](https://semver.org/).
- Lancer à nouveau `npm install` pour mettre à jour `package-lock.json`
- Commit & push à nouveau : `git commit -m "v{MAJOR}.{MINOR}.{PATCH}" && git push origin master`. Ex : [libe-components@1.1.1](https://github.com/libe-max/libe-components/commit/4270ae8afd7fec16aa5196175d3570a896a4ea8f)
- Si besoin, transpiler puis publier sur NPM : `npm run build && npm publish`.
- Dans le cas de [libe-static-ressources](https://github.com/libe-max/libe-static-ressources), ne pas oublier d'uploader les fichiers modifiés sur https://www.liberation.fr/apps/static 

## Auteurs

- **Maxime Fabas** - _Rédaction_ - [maximefabas.github.io](https://maximefabas.github.io)

___
![Logo Libération](https://www.liberation.fr/apps/static/assets/liberation-logo_raster_64.png)       ![Logo Libé labo](https://www.liberation.fr/apps/static/assets/libe-labo-logo_raster_64.png)

