# Cartographie #

### Année 4 / Sujet 2 « Cartographie » ###

#### Sujet ####

Si l’on reprend la définition du mot _devise_ communiquée pour le sujet « Papier-monnaie », on remarque qu’une monnaie est liée à un territoire ou un espace géographique.

En accord avec vos recherches pour votre monnaie, vous réaliserez une cartographie de son territoire.
Vous pouvez vous baser sur des éléments géographiques existants ou penser une topographie et des territoires complètement imaginaires.

Cette cartographie sera pensée pour être visible dans une page web (nous verrons le fonctionnement de l’outil [LeafletJS](http://leafletjs.com)).
À cet effet, vous devrez produire les éléments suivants :

- au minimum 2 niveaux d’échelle dans votre carte (correspondant à 2 niveaux de zooms différents)
- une typologie de symboles (types de lieux, marqueurs géographiques, indications)
- une légende
- une page web permettant de visualiser votre carte

La production de cette carte respectera la chronologie suivante :

- recherches papiers
- dessin dans un outil vectoriel (avec mise en place de librairies de symboles et de styles de tracés)
- intégration dans une page web (possibilité de suivi avec Michel Ravey)

#### À propos de LeafletJS ####

Pour générer le code nécessaire à votre fichier HTML, et générer les vignettes aux différentes résolutions, vous pouvez utiliser l'outil [MapTiler](http://www.maptiler.org). Celui ci est disponible dans une version gratuite(mais qui affiche un watermark dans vos images), et utilisable sur un système os X, Windows ou Linux.

L'image que cous allez fournir à MapTiler devra avoir des dimensions basées sur des puissances de 2 (à partir de 256 x 256 pixels).

Ainsi votre largeur et/ou votre hauteur devront suivre cette progression dans leurs dimensions (ce n'est pas indispensable, mais préférable pour éviter des zones blanches) :


| min | x 2 | x 2 | x 2 | x 2 | etc. |  
| ------	| ------	| ------	| ------	| ------	| ------	|  
|256|512|1024|2048|5096|etc.|

Le code généré par MapTiler devrait ressembler à ce qui suit (attention c'est juste un exemple, mais certains paramètres changeront en fonction de vos réglages), vous pouvez également consulter les fichiers `leaflet.html` dans les exemples.

Attention, le code par défaut va cherche les différents fichiers LeafletJS en ligne. Si vous souhaitez pouvoir consulter vos fichiers sans être connecté à Internet, il faudra récupérer les fichiers indiqués dans les balises suivantes, et bien sur mettre à jour leur chemin :

```html
<link rel="stylesheet" href="http://cdn.leafletjs.com/leaflet-0.6.4/leaflet.css" />
<link rel="stylesheet" href="http://cdn.leafletjs.com/leaflet-0.6.4/leaflet.ie.css" />
<script src="http://cdn.leafletjs.com/leaflet-0.6.4/leaflet.js"></script>
```


#### Liens utiles ####

- [https://www.openstreetmap.org/about](https://www.openstreetmap.org/about)
- [http://www.osmfoundation.org/wiki/Main_Page](http://www.osmfoundation.org/wiki/Main_Page)
- [https://www.here.com](https://www.here.com)
- [https://www.google.fr/maps](https://www.google.fr/maps)
- [https://www.bing.com/maps/](https://www.bing.com/maps/)
- [http://www.geoportail.gouv.fr/accueil](http://www.geoportail.gouv.fr/accueil)
- [http://fr.mappy.com](http://fr.mappy.com)
- [http://stamen.com](http://stamen.com)
- [http://maps.stamen.com/](http://maps.stamen.com/)
- [http://lust.nl/#medium-Map](http://lust.nl/#medium-Map)

