# Spreadsheets – Guide d'utilisation


### Structure du document

- L'onglet `_output` est l'onglet qui est lu par le format en ligne. Il rassemble les données des autres onglets
- Ne jamais toucher à l'onglet `_output`
- Ne pas créer de nouvel onglet sans en discuter avec Libé Labo
- Ne pas créer de nouvelles colonnes dans les onglets sans en discuter avec Libé Labo (les formats s'attendent à recevoir les données sous un format précis, un ajout de colonne casserait le format s'il n'est pas adapté au préalable)
- Ne pas modifier les éléments contenus dans les lignes d'entête du document (lignes fixes qui suivent le scroll)


### Remplissage et manipulation du document

- Ne pas considérer ce document comme un brouillon : lors du remplissage des onglets, ne pas laisser de ligne vide ou partiellement remplie. Si besoin d'un document de brouillon pour consigner certaines informations incomplètes, dupliquer ce document.
- Ne pas supprimer les lignes d'un onglet, ne pas les réorganiser en les glissant les unes au dessus des autres. Privilégier la méthode qui consiste en :
  - Clic droit > insérer une ligne à l'endroit souhaité
  - Copier les cellules de la ligne que l'on veut déplacer
  - La coller dans la ligne fraichement créée
  - Vider les cellules de la ligne copiée


### À propos des colonnes "ID"

- Certains onglets contiennent une colonne ID (généralement en première position).
- Un ID est ce qui permet de faire référence à une ligne depuis un autre onglet. Exemple :
  - Pour l'appli "Pronos", on a un onglet "Équipes", et un onglet "Poules"
  - Dans "Équipes", chaque ligne représente une Équipe, soit : un ID, un nom, une icône, et deux couleurs
  - Dans "Poules", chaque ligne représente une poule. La colonne "ID équipes" attend une liste d'IDs, séparés par des virgules.
- On en déduit que :
  - Chaque élément d'un onglet doit avoir un ID unique
  - 🚨🚨🚨 ON NE CHANGE JAMAIS UN ID. Ni parce qu'on s'aperçoit qu'il y aurait une faute, ni parce qu'on est sûr que la ligne en question n'est référencée nulle part ailleurs dans le document.


### Délai de mise à jour dans le format

- Après que des modifications sont faites dans le document, il faut compter un maximum de 10 minutes pour les voir apparaitre 
