# 🏠 Prédiction des prix de biens immobiliers

## 📌 Description
Ce projet a été réalisé dans le cadre du **Data Challenge de l’Institut Louis Bachelier**.  
L’objectif est de développer un **modèle de machine learning** capable de prédire le prix de biens immobiliers en France à partir de caractéristiques structurelles, géographiques et socio-économiques.

Le projet repose sur l’enrichissement du jeu de données initial par des **données externes** pertinentes (prix moyen au m², revenu moyen, insécurité, distances aux grandes villes) afin d’améliorer les performances de prédiction.

---

## 📊 Données
- **50 000 biens immobiliers**
  - 40 000 observations pour l’entraînement
  - 10 000 pour le test
- 26 variables initiales (type de bien, nombre de pièces, localisation bruitée, etc.)
- Données additionnelles issues de sources publiques (*data.gouv.fr*, *INSEE*)

⚠️ Les prix correspondent aux **prix des offres immobilières**, et non aux prix de transaction.

---

## 🎯 Métrique
- **MAPE (Mean Absolute Percentage Error)**
- Objectif : minimiser l’erreur relative de prédiction
- Benchmark du challenge : **XGBoost – MAPE ≈ 36,8 %**

---

## 🧠 Méthodologie
1. **Préparation des données**
   - Imputation des valeurs manquantes (médiane)
   - Encodage des variables catégorielles (One-Hot Encoding)
   - Analyse des corrélations

2. **Feature Engineering**
   - Ajout du prix moyen au m² par commune
   - Revenu moyen
   - Niveau d’insécurité
   - Distance à Paris, Lyon, Marseille et grandes villes françaises

3. **Modèles testés**
   - KNN
   - Régression linéaire
   - Arbre de décision
   - Random Forest
   - **XGBoost (modèle final)**

4. **Optimisation**
   - Recherche d’hyperparamètres via **GridSearch avec cross-validation**

---

## 🏆 Résultats
- Modèle final : **XGBoost**
- Paramètres principaux :
  - `max_depth = 10`
  - `n_estimators = 200`
  - `learning_rate = 0.1`
  - `subsample = 0.8`
- **Performance finale : MAPE inférieure au benchmark**
- Valeur finale de prédiction obtenue : **28,44**

---

## 📂 Contenu du repository
- `notebook.ipynb` : implémentation complète du pipeline (prétraitement, entraînement, évaluation)
- `rapport de projet.pdf` : rapport détaillé du projet et de l’analyse
- `README.md` : description du projet

---

## 🛠️ Technologies utilisées
- Python
- Pandas, NumPy
- Scikit-learn
- XGBoost
- Google Colab

---

## 🔍 Perspectives d’amélioration
- Intégration des **images des biens** (vision par ordinateur)
- Feature engineering plus avancé
- Modèles hybrides combinant données tabulaires et visuelles


Projet réalisé – Mai 2025
