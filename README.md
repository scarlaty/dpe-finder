# DPE Finder

Retrouver un DPE — et donc un bien immobilier — à partir des informations d'une annonce (consommation, GES, surface, code postal…), puis le comparer visuellement aux photos de l'annonce.

**Utiliser en ligne :** https://scarlaty.github.io/dpe-finder/

## Fonctionnalités

- Recherche inverse dans la base ADEME « DPE Logements existants (depuis juillet 2021) » avec tolérances (les annonces arrondissent les valeurs).
- Résultats classés par score de proximité, affichés sur une carte.
- Fonds de carte : plan OpenStreetMap, orthophotos IGN (20 cm), Esri World Imagery.
- Panneau de détail : vue aérienne zoomée, photos de rue Panoramax à moins de 40 m (classées selon leur orientation vers le bien), visionneuse 360° orientée automatiquement vers l'adresse.
- Liens directs : DPE complet sur l'observatoire ADEME, Google Street View, Google satellite, Géoportail, Panoramax.
- Marché autour du bien (rayon 150 / 300 / 500 m) :
  - **Vente du bien** : repère les ventes DVF à la même adresse ou sur la même parcelle, de même type et de surface à ±10 %. Elle est dite *probable* si le DPE a été établi dans les 12 mois précédant la vente, *possible* sinon.
  - **Prix au m² constaté** : médiane des prix réellement payés, chacun à sa date de vente.
  - **Prix au m² estimé aujourd'hui** : les mêmes ventes actualisées avec l'indice INSEE-Notaires des prix des logements anciens (zone la plus locale disponible, par type de logement) jusqu'au dernier trimestre publié.
  - **Estimation du bien** : surface du DPE × prix au m² estimé aujourd'hui, avec fourchette 25–75 %.

## Prix constaté vs prix estimé

| | Prix constaté | Prix estimé aujourd'hui |
|---|---|---|
| Nature | Prix réel payé, publié par la DGFiP | Calcul : prix constaté × évolution de l'indice des prix |
| Date de valeur | Date de chaque vente (2021 → 31/12/2025) | Dernier trimestre publié par l'INSEE (ex. T2 2026, provisoire) |
| Précision | Exacte pour chaque vente | Tendance sur une zone large (région, département, agglomération) |

Il n'existe pas de source ouverte de ventes plus récente que DVF (décalage d'environ 6 mois, mise à jour semestrielle) : l'estimation actualisée n'est pas une expertise.

## Utilisation locale

Aucune installation : ouvrir `index.html` dans un navigateur.

## Sources de données

| Source | Usage | Licence |
|---|---|---|
| [ADEME – data.ademe.fr](https://data.ademe.fr/datasets/dpe03existant) | DPE | Licence Ouverte 2.0 |
| [IGN Géoplateforme](https://geoservices.ign.fr/) | Orthophotos | Licence Ouverte 2.0 |
| [Panoramax](https://panoramax.fr/) | Photos de rue | Licence Ouverte 2.0 |
| [DVF – DGFiP](https://app.dvf.etalab.gouv.fr/) | Ventes immobilières | Licence Ouverte 2.0 |
| [INSEE – indices des prix des logements anciens](https://www.insee.fr/fr/statistiques/serie/010567059) | Actualisation des prix | Licence Ouverte 2.0 |
| [API Carto IGN – cadastre](https://apicarto.ign.fr/api/doc/cadastre) | Sections et parcelles | Licence Ouverte 2.0 |
| [OpenStreetMap](https://www.openstreetmap.org/copyright) | Fond de plan | ODbL |
| Esri World Imagery | Fond satellite | Conditions Esri |

## Limites

- Seuls les DPE établis depuis juillet 2021 sont couverts.
- Ventes DVF disponibles de 2021 au 31/12/2025 ; seules les ventes d'un logement unique sont utilisées pour le prix au m² (le prix inclut les dépendances vendues avec).
- Le champ « étage » de l'ADEME est souvent mal renseigné.
- La couverture Panoramax est inégale hors des villes ; Google Street View est proposé en lien externe.
