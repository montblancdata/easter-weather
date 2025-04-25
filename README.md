
# Analyse de la pluviométrie à Pâques (1974 – 2023)

## Description

Ce projet propose une analyse statistique de la pluviométrie observée lors du week-end de Pâques sur trois stations météo françaises entre 1974 et 2023.  
L’objectif : **vérifier l’intuition populaire selon laquelle “il pleut toujours à Pâques”**, à travers une approche rigoureuse de collecte, traitement et visualisation de données météorologiques ouvertes.

## Contexte

La date de Pâques étant mobile (basée sur le cycle lunaire), il est nécessaire de calculer dynamiquement les dates concernées pour chaque année du jeu de données.  
L’algorithme de Butcher-Meeus est utilisé pour déterminer la date du **dimanche de Pâques** (et par extension celle du  **lundi de Pâques**).  
Ces deux jours sont ensuite extraits des historiques météorologiques pour analyse.

## Stations analysées

- **CHAMBERY-AIX** (Savoie) – Climat montagnard
- **ROUBAIX** (Nord) – Climat océanique
- **CAP CAMARAT** (Var) – Climat méditerranéen

## Données utilisées

- Source : [data.gouv.fr – Données Météo-France](https://data.gouv.fr)
- Fichiers CSV contenant les observations journalières de :
  - Précipitations (RR)
  - Températures minimales/maximales
  - Vent

## Structure du projet

```
easter-weather/
├── src_data/                       # Données brutes (.csv)
├── easter-weather.ipynb            # Notebook principal
├── canvas_linkedin.png             # Illustration utilisée pour la communication
└── README.md                       # Présentation du projet
```

## Dépendances

Le notebook utilise les bibliothèques Python suivantes :

- `pandas` : manipulation de données
- `matplotlib` : visualisation
- `folium` : cartographie
- `datetime` : gestion de dates
- `IPython.display` : affichage interactif

## Fonctionnalités du code

- **Chargement des données météo** à partir de fichiers CSV
- **Nettoyage** et conversion des dates (format `AAAAMMJJ` → `datetime`)
- **Calcul des dates de Pâques** pour chaque année via l’algorithme de Butcher-Meeus
- **Filtrage** des données météo sur les dimanches et lundis de Pâques
- **Agrégation annuelle** des précipitations cumulées pour ces deux jours
- **Analyse comparative** des périodes :
  - 1974–1998
  - 1999–2023
- **Visualisations** : barplots, analyse statistique, carte des stations

## Exemple de résultat

Visualisation comparative par station :

| Station       | 1974–1998 (avant 1999) | 1999–2023 (depuis 1999) |
|---------------|------------------------|--------------------------|
| Aix-Chambéry  | 64 % jours pluvieux, 9.50 mm | 52 % jours pluvieux, 4.23 mm |
| Roubaix       | 64 %, 6.19 mm                 | 72 %, 4.94 mm                 |
| Cap Camarat   | 24 %, 3.98 mm                 | 52 %, 4.05 mm                 |

## Auteur

**Pierrick Girard**  
MontBlanc Data  
[LinkedIn](https://www.linkedin.com/in/pierrick-g-4721a2190/) • [GitHub](https://github.com/montblancdata)

## Licence
Projet distribué sous licence libre.
