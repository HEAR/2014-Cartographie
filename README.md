# Cartographie #

### Année 3 / Sujet 2 « Cartographie » ###

## Sujet ##

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
- intégration dans une page web


## Faire une carte personnalisée avec des dimensions en pixels ##

### À propos de LeafletJS ###

Pour générer le code nécessaire à votre fichier HTML, et générer les vignettes aux différentes résolutions, vous pouvez utiliser l'outil [MapTiler](http://www.maptiler.org). Celui ci est disponible dans une version gratuite(mais qui affiche un watermark dans vos images), et utilisable sur un système os X, Windows ou Linux.

Les tuiles gérées par lealetJS ont toutes une dimension de 256 x 256 pixels. Sachant qu'au changement d'échelle, chaque tuile est divisée en 4, les dimensions optimales d'une image devraient respecter la progression suivante :

Ainsi votre largeur et/ou votre hauteur devront suivre cette progression dans leurs dimensions (ce n'est pas indispensable, mais préférable pour éviter des zones blanches) :

- level 0 > 256
- level 1 > 512
- level 2 > 1024
- level 3 > 2048
- level 4 > 4096
- level 5 > 8192
- level 6 > 16348
- …

Le code généré par MapTiler devrait ressembler à ce qui suit (attention c'est juste un exemple, mais certains paramètres changeront en fonction de vos réglages), vous pouvez également consulter les fichiers `leaflet.html` dans les exemples.

Attention, le code par défaut va chercher les différents fichiers LeafletJS en ligne. Si vous souhaitez pouvoir consulter vos fichiers sans être connecté à Internet, il faudra récupérer les fichiers indiqués dans les balises suivantes, et bien sur mettre à jour leur chemin :

```html
<link rel="stylesheet" href="http://cdn.leafletjs.com/leaflet-0.6.4/leaflet.css" />
<link rel="stylesheet" href="http://cdn.leafletjs.com/leaflet-0.6.4/leaflet.ie.css" />
<script src="http://cdn.leafletjs.com/leaflet-0.6.4/leaflet.js"></script>
```



### Générer la carte ###

Vous pouvez générer les différentes **tuiles** avec un script dans le terminal de votre ordinateur en utilisant un programme nommé imagemagick (cf le tutorial sur cette page : [http://omarriott.com/aux/leaflet-js-non-geographical-imagery/](http://omarriott.com/aux/leaflet-js-non-geographical-imagery/)).

Néanmoins cette méthode peut être assez technique. Vous pouvez également utiliser un programme comme [MapTiler](http://www.maptiler.org). Celui ci s'occupe de générer toutes les vignettes de votre carte, ainsi que le fichier html nécessaire à l'utilisation de leafletJS. Attention, dans sa version gratuite, le programme ne permet pas de gérer des images dont les dimensions sont supérieures à 10240 pixels. Les *tuile* auront également un watermark "maptiler" inscrit dessus.

### Placer un marqueur avec des coordonnées en pixels ###

Même avec une carte en pixels le système de coordonnées adopté est basé sur les coordonnées GPS d'OpenStreetMap. Ceci, notamment pour prévenir les problèmes de positionnement lié aux changements d'échelle.

Pour pouvoir positionner l'abcisse et l'ordonnée d'un point en pixels, il faut utiliser la fonction suivante :

```js
map.unproject(
  [x, y],
  map.getMaxZoom()
)

```

Ainsi le positionnement d'un marqueur au point 1000, 1000 se fera de la manière suivante :

```js
var marker = L.marker(
    map.unproject(
      [1000, 1000],
      map.getMaxZoom()
    )
).addTo(map);
```



## Liens utiles ##

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

