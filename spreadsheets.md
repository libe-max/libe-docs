# Spreadsheets – Guide d'utilisation

## Structure du document

- L'onglet `_output` est l'onglet qui est lu par le format en ligne. Il rassemble les données des autres onglets. Par conséquent, mieux vaut ne pas y toucher.
- Il est possible de créer de nouveaux onglets dans le document, cela n'aura pas d'impact sur l'onglet `_output`. Cependant, un spreadsheet bien rangé limite les risques de suppression malencontreuse d'information.
- Ne pas créer de nouvelles colonnes dans les onglets sans en discuter avec Libé Labo (les formats s'attendent à recevoir les données sous un format précis, un ajout de colonne casserait le format s'il n'est pas adapté au préalable)
- Ne pas modifier les éléments contenus dans les lignes d'entête du document (lignes fixes qui suivent le scroll)

## Remplissage et manipulation du document

- Lors du remplissage des onglets, ne pas laisser de ligne vide ou partiellement remplie, ce qui pourrait "casser" l'affichage du format en ligne. Si besoin d'un document de brouillon pour consigner certaines informations incomplètes, créer un nouvel onglet ou dupliquer le document.
- Ne pas supprimer les lignes d'un onglet (clic droit › Supprimer la ligne), ne pas les réorganiser en les glissant les unes au dessus des autres. Privilégier la méthode qui consiste en :
  - Clic droit > insérer une ligne au dessus ou en dessous
  - Copier les cellules de la ligne que l'on veut déplacer
  - La coller dans la ligne fraichement créée
  - Vider les cellules de la ligne copiée
- Veiller à ne pas laisser de retour à la ligne en fin de case, ce qui peut arriver lorsque l'on colle dans une case du texte copié ailleurs. Les retours à la ligne en fin de case feront systématiquement planter les applications et seront difficiles à retrouver par la suite, il faut donc être vigilant au moment du remplissage

## À propos des colonnes "ID"

- Certains onglets contiennent une colonne ID (généralement en première position).
- Un ID est ce qui permet de faire référence à une ligne depuis un autre onglet. Exemple :
  - Pour l'appli "Pronos", on a un onglet "Équipes", et un onglet "Poules"
  - Dans "Équipes", chaque ligne représente une Équipe, soit : un ID, un nom, une icône, et deux couleurs
  - Dans "Poules", chaque ligne représente une poule. La colonne "ID équipes" attend une liste d'IDs, séparés par des virgules.
- On en déduit que :
  - Chaque élément d'un onglet doit avoir un ID unique
  - 🚨**On ne change jamais un ID**🚨. Si l'ID d'une ligne est modifié alors que d'autres lignes dans le document mentionnent l'ID, le lien entre ces lignes est rompu.

## Délai de mise à jour dans le format

- Après que des modifications sont faites dans le document, il faut compter un maximum de 10 minutes pour les voir apparaitre dans le format.

## Auteurs

- **Maxime Fabas** - _Rédaction_ - [maximefabas.github.io](https://maximefabas.github.io)

___

![Logo Libération](https://www.liberation.fr/apps/static/assets/liberation-logo_raster_64.png)       ![Logo Libé labo](https://www.liberation.fr/apps/static/assets/libe-labo-logo_raster_64.png)

