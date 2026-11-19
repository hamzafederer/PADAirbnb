# Analyse des annonces Airbnb — New York 2019

Projet du cours *Projet Analyse de données* (La Cité collégiale)

## Objectif

Comprendre comment les prix et la disponibilité des annonces Airbnb varient selon l'arrondissement, le quartier et le type de logement à New York en 2019.

## Avancement

- **Sprint 1** : cadrage, audit de qualité, nettoyage (fichier socle), questions analytiques.
- **Sprint 2** : Q1 (prix médian par arrondissement et type de logement) et Q2 (top 10 des quartiers).
- **Sprints 3 et 4** : Q3 à Q5, tableau de bord, rapport final.

## Structure

```
├── README.md
├── requirements.txt
├── .gitignore
├── data/
│   ├── raw/          Données originales (non versionnées)
│   └── processed/    Fichiers propres générés par le notebook (non versionnés)
└── notebooks/
    └── analyse_airbnb_simple.ipynb
```

## Résultats clés

| Élément | Valeur |
|---|---|
| Annonces analysées | 48 895, dont 48 410 pour les prix (de 0 $ à 799 $ exclus : prix nuls et extrêmes) |
| Q1 — segment le plus cher | Manhattan / logement entier : 190 $ la nuit (médiane) |
| Q1 — segment le moins cher (au moins 100 annonces) | Brooklyn / chambre partagée : 36 $ |
| Q2 — quartier n° 1 | Tribeca : 275,50 $ (156 annonces); les 10 premiers sont à Manhattan |


## Source des données

*New York City Airbnb Open Data*, Kaggle, d'après Inside Airbnb.