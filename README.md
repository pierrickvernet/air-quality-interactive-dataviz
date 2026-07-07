# Data Cleaning & Interactive Air Quality Exploration (Périgueux 2023)

## 📌 Présentation du Projet
Ce projet est dédié à l'**Analyse Exploratoire des Données** et à la **Data Visualization** des polluants atmosphériques de la ville de Périgueux. L'objectif est d'analyser l'influence fine des facteurs météorologiques et temporels sur les concentrations d'Ozone ($O_3$) au cours de l'année 2023.

🔗 **[Consulter le rapport interactif complet (HTML sur GitHub Pages)](https://pierrickvernet.github.io/air-quality-interactive-dataviz/)**

## 🛠️ Pipeline de Data Engineering & Préparation
* **Missing Data Management :** Analyse du taux de complétion et suppression ciblée des variables non exploitables.
* **Feature Engineering :** * Conversion et harmonisation des types de variables.
  * Extraction et ingénierie temporelle des composantes mensuelles et horaires.

## 📈 Extraits des Résultats Majeurs
* **Saisonnalité Thermique :** Alignement synchrone des cycles de l'ozone avec les pics de chaleur estivaux et de fin d'après-midi (visualisé via des graphiques à double échelle et heatmaps de densité).
* **Antagonisme Chimique :** Mise en évidence d’une relation inverse et non linéaire entre l’$O_3$ et le bloc de pollution routière ($NO, NO_2, PM_{10}$), illustrant le phénomène chimique urbain de titration.
* **Impact Aérologique :** Utilisation d'un calcul customisé du rapport de corrélation ($\eta^2 = 0.0976$) pour quantifier l'impact des secteurs de provenance du vent sur la dispersion ou l'accumulation de la pollution.

## 🧰 Stack Technique
* **Langage :** R
* **Packages clés :** `tidyverse` (`dplyr`, `ggplot2`, `tidyr`), `plotly` (visualisations dynamiques), `corrplot`, `patchwork`, `rmdformats` (layout du rapport).
