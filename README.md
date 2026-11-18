# UA2 — Projet Analyse de données : Airbnb New York 2019

Projet d'équipe du cours *Projet Analyse de données* (S3, La Cité collégiale).
Équipe : Hamza Reguieg (Scrum Master et Product Owner), Anas Fouad, Houmad Chiky, Juba Bourennane.
Enseignant : Dr. Nacereddine Benzebouchi.

## Objectif

Comprendre comment les prix et la disponibilité des annonces Airbnb varient selon l'arrondissement, le quartier et le type de logement à New York en 2019, en suivant la démarche CRISP-DM et une organisation Scrum (Jira, clés `SCRUM-xx`).

## État d'avancement

| Sprint | Contenu | État |
|---|---|---|
| Sprint 1 | Cadrage, audit de qualité, fichier socle (Niveau 1), questions analytiques | Terminé |
| Sprint 2 | **Q1** : prix médian par arrondissement et type de logement. **Q2** : top 10 des quartiers | Livré dans ce dépôt |
| Sprint 3 | Q3 (type ou arrondissement ? R² et bootstrap), Q4 (disponibilité), Q5 (prix et disponibilité) | À venir |
| Sprint 4 | Tableau de bord, rapport final, présentation | À venir |

## Structure du dépôt

```
UA2/
├── README.md                  Ce fichier
├── .gitignore                 Fichiers exclus de Git (données lourdes, environnement, temporaires)
├── requirements.txt           Bibliothèques Python
├── data/
│   ├── raw/                   Données originales (AB_NYC_2019.csv), non versionnées
│   └── processed/             Fichiers propres générés par le notebook, non versionnés
├── notebooks/
│   └── analyse_airbnb_simple.ipynb   Notebook du Sprint 2 (étapes 1 à 5)
├── outputs/                   Figures 1, 2, 3 et 8 et tableaux de Q1 et Q2
└── docs/
    ├── Rapport_Sprint2_Airbnb_NYC_2019.docx
    └── Repartition_des_taches_Projet_Analyse_NYC_v2.docx
```

## Reproduire les résultats

1. Installer Python 3.10 ou plus récent, puis les bibliothèques :
   ```
   pip install -r requirements.txt
   ```
2. Télécharger `AB_NYC_2019.csv` depuis Kaggle
   (<https://www.kaggle.com/datasets/dgomonov/new-york-city-airbnb-open-data>) et le placer dans `data/raw/`.
   Le fichier n'est pas versionné : il pèse plus de 7 Mo et contient des prénoms d'hôtes.
3. Ouvrir `notebooks/analyse_airbnb_simple.ipynb` et exécuter toutes les cellules de haut en bas.
   Les chemins sont relatifs au dossier `notebooks/`.
4. Comparer les sorties au tableau « Chiffres à retrouver » à la fin du notebook.

## Chiffres clés du Sprint 2

| Élément | Valeur |
|---|---|
| Annonces du fichier socle | 48 895 (16 colonnes) |
| Population d'analyse des prix | 48 410 annonces (prix > 0 et ≤ 799 $, le 99e centile) |
| Q1 — segment le plus cher | Manhattan / logement entier : 190 $ la nuit (médiane) |
| Q1 — segment le moins cher (au moins 100 annonces) | Brooklyn / chambre partagée : 36 $ |
| Q2 — quartier n° 1 | Tribeca : 275,50 $ (156 annonces); les 10 premiers sont à Manhattan |

Les cellules de moins de 100 annonces sont signalées dans les tableaux et les graphiques. Les données datent de 2019 et sont observationnelles : les résultats décrivent des associations, pas des causes.

## Conventions de travail

- **Branche principale** : `main`.
- **Branches de travail** : `feature/SCRUM-xx-description`, fusionnées dans `main` par pull request avec une ou deux revues de code.
- **Messages de commit** : style conventionnel, par exemple `feat: ajouter la carte de chaleur de Q1` ou `docs: mettre à jour le README`.
- **Clé Jira** : indiquée dans le titre de la pull request (par exemple `SCRUM-33 : vérifier la Figure 2`).
- **Données** : jamais de fichier de plus de 100 Mo dans Git; les données brutes restent hors du dépôt.

## Seuils et paramètres à ne pas modifier

Seuil de prix de 799 $ (99e centile), seuil d'effectif de 100 annonces (`SEUIL_EFFECTIF`) et graine aléatoire 20260928 : un changement modifie les chiffres de toutes les questions.
