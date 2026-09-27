# DPE Finder

Retrouver un DPE — et donc un bien immobilier — à partir des informations d'une annonce (consommation, GES, surface, code postal…), puis le comparer visuellement aux photos de l'annonce.

**Utiliser en ligne :** https://scarlaty.github.io/dpe-finder/

## Fonctionnalités

- Recherche inverse dans la base ADEME « DPE Logements existants (depuis juillet 2021) » avec tolérances (les annonces arrondissent les valeurs).
- Résultats classés par score de proximité, affichés sur une carte.
- Fonds de carte : plan OpenStreetMap, orthophotos IGN (20 cm), Esri World Imagery.
- Panneau de détail : vue aérienne zoomée, photos de rue Panoramax à moins de 40 m (classées selon leur orientation vers le bien), visionneuse 360° orientée automatiquement vers l'adresse.
- Liens directs : DPE complet sur l'observatoire ADEME, Google Street View, Google satellite, Géoportail, Panoramax.

## Utilisation locale

Aucune installation : ouvrir `index.html` dans un navigateur.

## Sources de données

| Source | Usage | Licence |
|---|---|---|
| [ADEME – data.ademe.fr](https://data.ademe.fr/datasets/dpe03existant) | DPE | Licence Ouverte 2.0 |
| [IGN Géoplateforme](https://geoservices.ign.fr/) | Orthophotos | Licence Ouverte 2.0 |
| [Panoramax](https://panoramax.fr/) | Photos de rue | Licence Ouverte 2.0 |
| [OpenStreetMap](https://www.openstreetmap.org/copyright) | Fond de plan | ODbL |
| Esri World Imagery | Fond satellite | Conditions Esri |

## Limites

- Seuls les DPE établis depuis juillet 2021 sont couverts.
- Le champ « étage » de l'ADEME est souvent mal renseigné.
- La couverture Panoramax est inégale hors des villes ; Google Street View est proposé en lien externe.
