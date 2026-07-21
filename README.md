# Data Cleaning & Interactive Air Quality Exploration (Périgueux 2023)

## 1. INTRODUCTION

### Cadre de réalisation
Projet académique d'analyse exploratoire des données environnementales, réalisé dans le cadre du cours de Représentation de données et statistique multidimentionnelle de mon M1 IREF.

### Présentation du sujet
Étude et modélisation descriptive des polluants atmosphériques au sein de l'agglomération de Périgueux au cours de l'année 2023, avec une attention particulière portée aux dynamiques de formation et de dispersion de l'Ozone ($O_3$).

### Intérêt et cas d'usage
Analyse d'impact environnemental, veille sanitaire et création d'outils décisionnels interactifs. Le projet quantifie l'influence des conditions météorologiques et des cycles temporels sur la qualité de l'air, et propose un tableau de bord intégrant un rapport interactif complet hébergé via GitHub Pages.

---

## 2. SOURCES ET DONNÉES

### Origine des données
Fichier `atmo_polluants_Périgueux.xlsx` comprenant les relevés stationnaires d'Atmo Nouvelle-Aquitaine sur la qualité de l'air et les conditions météorologiques associées pour la ville de Périgueux sur l'année 2023.

### Périmètre et variables clés
- **Variable cible / Polluant d'intérêt :** Ozone ($O_3$).
- **Polluants complémentaires :** Monoxyde d'azote ($NO$), dioxyde d'azote ($NO_2$), particules fines ($PM_{10}$).
- **Données météorologiques & aérologiques :** Température, secteurs de provenance et vitesse du vent.
- **Variables temporelles :** Horodatage avec fréquence.

---

## 3. MÉTHODOLOGIE ET DÉTAILS TECHNIQUES

### Pipeline de Data Engineering & Preprocessing
- **Traitement des données manquantes :** Évaluation quantitative des taux de complétion par variable et suppression ciblée des séries présentant un déficit d'observations critique.
- **Ingénierie temporelle & Feature Engineering :** Harmonisation des types de données, extraction systématique des composantes temporelles (cycles horaires, variations nycthémérales, composantes mensuelles).

### Analyse Exploratoire & Modélisation Quantitative
- **Analyse dynamique et thermique :** Évaluation des dépendances saisonnières et quotidiennes de l'ozone via des représentations graphiques à double échelle et des matrices de densité de chaleur (*Heatmaps*).
- **Modélisation de l'antagonisme chimique :** Mise en évidence d'une relation inverse et non linéaire entre l'Ozone ($O_3$) et les émanations du trafic routier ($NO$, $NO_2$, $PM_{10}$), caractérisant le mécanisme urbain de titration de l'ozone.
- **Quantification aérologique :** Calcul customisé du rapport de corrélation ($\eta^2 = 0,0976$) pour estimer la part de variance du polluant expliquée par la provenance sectorielle des masses d'air.

### Stack technologique
- **Langage :** R
- **Manipulation de données :** `tidyverse` (`dplyr`, `tidyr`)
- **Visualisation graphique & Interactive :** `ggplot2`, `plotly`, `corrplot`, `patchwork`
- **Restitution & Reporting :** `rmarkdown`, `rmdformats` (layout HTML interactif)

---

## 4. CONCLUSION ET RÉSULTATS CLÉS

### Enseignements majeurs
- **Saisonnalité & Température :** Alignement synchrone entre la concentration maximale d'Ozone, les épisodes de fortes chaleurs estivales et le pic solaire de fin d'après-midi.
- **Titration de l'Ozone :** Validation empirique de la destruction de l'ozone par le monoxyde d'azote dans les zones urbaines denses à fort trafic routier.
- **Impact du Vent :** Quantification de la dépendance spatio-aérologique ($\eta^2 \approx 9,76\ \%$), démontrant un effet mesurable des directions de vent sur la stagnation ou le balayage des polluants.

### Restitution interactive
L'ensemble du pipeline et des visualisations dynamiques est disponible en ligne :
- [Consulter le rapport interactif complet (GitHub Pages)](https://pierrickvernet.github.io/air-quality-interactive-dataviz/)

### Limites et perspectives
- Intégrer des modèles de séries temporelles avancés (ARIMA, Prophet) pour la prévision à court terme des dépassements de seuils d'alerte.
- Enrichir le dataset avec des données d'ensoleillement direct (rayonnement UV) pour affiner la modélisation de la réaction photochimique.

---

## 5. STRUCTURE DU DÉPÔT

```text
.
├── data/
│   └── atmo_polluants_Périgueux.xlsx   # Données brutes de la station d'Atmo Périgueux (2023)
├── notebook/
│   └── mini_projet_dataviz.Rmd         # Code source RMarkdown du pipeline et des analyses
├── .gitattributes                      # Configuration Git du dépôt
├── index.html                          # Rapport HTML interactif déployé sur GitHub Pages
└── README.md                           # Documentation du projet
```

---
