# Notions générales pour le développement d'outils Libé Labo

Quelques informations d'ordre général avant de se lancer dans le développement ou la mise à jour d'outils ou de formats Libé Labo.

## Sommaire
- [Architecture globale des outlis Libé Labo](https://github.com/libe-max/Docs/blob/master/technical-guidelines-overview.md#architecture-globale)
- [Choix techniques](https://github.com/libe-max/Docs/blob/master/technical-guidelines-overview.md#choix-techniques)
- [Nomenclature et mise en forme du code](https://github.com/libe-max/Docs/blob/master/technical-guidelines-overview.md#nomenclature-et-mise-en-forme)
- [Publication & versionning](https://github.com/libe-max/Docs/blob/master/technical-guidelines-overview.md#publication--versionning)

## Architecture globale

![Schéma de l'architecture globale des outils de Libé Labo](https://github.com/libe-max/Docs/raw/master/assets/applications-scheme.jpg)

## Choix techniques

- Les applications client sont construites avec [React](https://reactjs.org/), par le biais de [create-react-app](https://reactjs.org/docs/create-a-new-react-app.html).
- Les applications serveur sont des applications [Express](https://expressjs.com/), exécutées par [Node.js](https://nodejs.org/en/).
- Les dépendences et scripts des projets client et serveur sont géré•e•s avec [NPM](https://www.npmjs.com/).
- Les applications de base de données sont des applications [MongoDB](https://www.mongodb.com/).

Certains projets ont à leur racine des scripts de démarrage, compilation ou publication. Ces scripts peuvent être des scripts [Shell](https://en.wikipedia.org/wiki/Shell_script), [Python](https://en.wikipedia.org/wiki/Python_(programming_language)), ou [JavaScript](https://en.wikipedia.org/wiki/JavaScript), éxécutables par [Node.js](https://nodejs.org/en/). ⚠️ Ces scripts n'ont pas vocation à être éxécutés directement, ils doivent avoir leur commande npm dédiée dans `[PROJET]/package.json` (ex : `scripts: { build: node build.js }`).

Dans le cadre des applications React (à l'exception du projet [Libé Tools front](https://github.com/libe-max/libe-tools-front)), et au sujet des outils de CSS modulaire (ex : [styled-components](https://www.styled-components.com/)). Chaque modification de CSS entraînant nécessairement une nouvelle compilation du code, la solution du CSS modulaire est écartée, ne permettant pas de traiter simplement un chamgement de style à appliquer sur toute la production Libé Labo. La solution retenue est d'inclure de manière traditionnelle (par une balise link dans le head du document) des styles communs entre les applications (voir [Libé Static Ressources](https://github.com/libe-max/libe-static-ressources)).

De manière générale, les intentions sont :
- Maintenir une organisation simple et descriptive des dossiers et fichiers source.
- Refuser tout choix technologique impliquant d'installer et/ou configurer un compileur. Liste non exhaustive des technologies exclues : Webpack, TypeScript, tout pré-processeur de CSS, Mustache, Pug, etc.
- Limiter au maximum l'installation de dépendances, quand une solution peut être développée à la main.

## Nomenclature et mise en forme

- Tous les dossiers et fichiers de code doivent être nommés en [lower-dash-case](https://en.wikipedia.org/wiki/Letter_case#Special_case_styles).
- Un fichier javascript contenant des exports doit être nommé selon le nom de l'objet exporté par défaut (converti en [lower-dash-case](https://en.wikipedia.org/wiki/Letter_case#Special_case_styles)).
- Pour les composants React, ils sont exportés dans le dossier components, à l'interieur d'un dossier nommé selon le composant exporté en [PascaleCase](https://en.wikipedia.org/wiki/Letter_case#Special_case_styles), sous le nom de index.js, soit : `[PROJET]/src/components/MonComposantReact/index.js`.

### HTML
- Valide W3C
- Indentation à 2 espaces
- Pas de lignes vides sauf au dessus d'une ligne de commentaire

### CSS
- Les classes des composants doivent suivre la nomenclature de la [BEM methodology](https://en.bem.info/methodology/)
- Un "block" au sens de la BEM ne doit pas se préoccuper pas de ce qui est en dehors de lui. Les propriétés margin, width, height et position ne peuvent pas être définies à ce niveau.

### JavaScript
Éviter les double quotes
ES6
BEM method
Standard.js

### Commits
commits

## Publication & versionning

Publication et versionning

## Authors

- **Maxime Fabas** - _Rédaction_ - [maximefabas.github.io](https://maximefabas.github.io)

___
![Logo Libération](https://www.liberation.fr/apps/static/assets/liberation-logo_raster_64.png)       ![Logo Libé labo](https://www.liberation.fr/apps/static/assets/libe-labo-logo_raster_64.png)

