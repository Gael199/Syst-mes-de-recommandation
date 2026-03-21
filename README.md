# RecoSys_Eudes_Chenny

Application interactive développée avec **Streamlit** pour comparer plusieurs approches de **systèmes de recommandation** sur une matrice de notes utilisateur-item.

L’application met en parallèle quatre méthodes de recommandation :

- **User-User Collaborative Filtering**
- **Item-Item Collaborative Filtering**
- **NMF (Non-negative Matrix Factorization)**
- **NCF (Neural Collaborative Filtering)**

Elle permet d’explorer la performance de chaque approche à travers une matrice partiellement masquée, des recommandations **top-k**, des **heatmaps de similarité**, ainsi que l’analyse des **facteurs latents** et des **embeddings appris**.

---

## Aperçu du projet

Ce projet a pour objectif de comparer différentes familles d’algorithmes de recommandation :

- les méthodes de **voisinage**,
- les méthodes de **factorisation matricielle**,
- les méthodes de **deep learning**.

Une matrice utilisateur-item est construite sous forme d’exemple pédagogique, puis une partie des notes est volontairement masquée pour simuler la **sparsité** des données. Les modèles sont ensuite évalués sur leur capacité à reconstruire ces notes manquantes à l’aide du **RMSE**.

---

## Fonctionnalités

### 1. Comparaison de 4 modèles de recommandation

L’application calcule et compare les prédictions de :

- **User-User** : recommandation basée sur la similarité entre utilisateurs
- **Item-Item** : recommandation basée sur la similarité entre items
- **NMF** : factorisation de matrices non négative
- **NCF** : réseau de neurones pour le filtrage collaboratif

### 2. Contrôle de la sparsité

L’utilisateur peut définir un **taux de masquage** pour cacher une partie des notes observées et créer un **jeu de test interne**.

### 3. Évaluation des performances

Les modèles sont comparés avec la métrique :

- **RMSE (Root Mean Squared Error)** sur les notes masquées

### 4. Recommandations Top-k

L’utilisateur peut choisir un utilisateur cible et afficher les **meilleures recommandations** proposées par chaque méthode.

### 5. Visualisation des similarités

L’application affiche des **heatmaps** pour :

- les similarités **User-User**
- les similarités **Item-Item**

### 6. Interprétabilité des modèles

Deux onglets permettent de mieux comprendre les représentations apprises :

- **NMF factors** : profils latents utilisateurs/items
- **NCF embeddings** : vecteurs d’embeddings appris par le réseau de neurones

---

## Technologies utilisées

- Python
- Streamlit
- NumPy
- Pandas
- Scikit-learn
- PyTorch
- Plotly

---

## Méthodes implémentées

### User-User Collaborative Filtering
Cette méthode prédit une note manquante à partir des utilisateurs les plus similaires à l’utilisateur cible.

### Item-Item Collaborative Filtering
Cette approche s’appuie sur les items les plus similaires à l’item cible à partir des notes déjà données par l’utilisateur.

### NMF
La **Non-negative Matrix Factorization** décompose la matrice de notes en facteurs latents représentant les utilisateurs et les items.

### NCF
La **Neural Collaborative Filtering** utilise des embeddings utilisateurs/items et un réseau de neurones multicouche pour apprendre les interactions.

---

## Interface de l’application

L’interface Streamlit contient :

- une **barre latérale** avec tous les réglages,
- une vue de la **matrice observée** après masquage,
- un tableau des **notes masquées** utilisées pour le test,
- un comparatif des **RMSE** des 4 modèles,
- plusieurs **onglets** pour visualiser les résultats.

### Réglages disponibles

- seed de reproductibilité
- taux de masquage
- nombre de voisins `k` pour User-User et Item-Item
- nombre minimum de co-notes
- nombre de facteurs latents pour NMF
- nombre d’itérations NMF
- dimension des embeddings NCF
- nombre d’epochs NCF
- learning rate
- utilisateur cible
- nombre de recommandations top-k

---

## Structure des données

Le projet repose sur une **matrice de notes utilisateur-item** d’exemple :

- **5 utilisateurs**
- **6 items**
- certaines notes présentes
- certaines notes absentes (`NaN`)

Cette matrice sert de base à la simulation et à l’évaluation des modèles.

---

## Installation

### 1. Cloner le dépôt

```bash
git clone https://github.com/ton-utilisateur/ton-repo.git
cd ton-repo
