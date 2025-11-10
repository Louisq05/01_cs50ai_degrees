# 🎬 Degrees — Degrees of Separation Between Actors

> Find the shortest cinematic path between two actors using graph search (Breadth-First Search);  inspired by _Six Degrees of Kevin Bacon_.

Ce projet détermine le nombre minimal de « degrés de séparation » entre deux acteurs, en utilisant leurs collaborations cinématographiques. Les données proviennent d’IMDb (via CS50AI).

---

## 🚀 Fonctionnalités

- 🔍 Recherche du chemin le plus court entre deux acteurs
- 🎥 Affichage de chaque étape via les films partagés
- 📂 Chargement de grandes bases de données CSV (`people`, `movies`, `stars`)
- 🧠 Implémentation d’un algorithme **BFS** 
- 🧼 Gestion des homonymes d'acteurs

---

## 📦 Exemple d'utilisation

```bash
python degrees.py large Loading data... Data loaded. Name: Emma Watson Name: Jennifer Lawrence 3 degrees of separation. 1: Emma Watson and Brendan Gleeson starred in Harry Potter and the Order of the Phoenix 2: Brendan Gleeson and Michael Fassbender starred in Trespass Against Us 3: Michael Fassbender and Jennifer Lawrence starred in X-Men: First Class`
```
---

## 🧠 Concept

Selon le jeu _Six Degrees of Kevin Bacon_, tout acteur d’Hollywood peut être relié à Kevin Bacon via max **6 acteurs**.

Dans ce projet, on applique le même principe mais pour **n’importe quels acteurs** :

- Chaque **acteur** = un nœud
- Chaque **film partagé** = une connexion
- Objectif → trouver le **chemin le plus court**

✅ Résolution par **Breadth-First Search (BFS)**

---

## 🗂️ Structure du projet

`degrees/ │── degrees.py        # Programme principal (où BFS est implémenté) │── util.py           # Node, StackFrontier, QueueFrontier (fournis par CS50) │── README.md         # Ce fichier │── small/            # Petit dataset pour tests │── large/            # Grand dataset (IMDb)`

---

## ⚙️ Installation

### 1️⃣ Cloner le projet

`git clone https://github.com/<your-username>/degrees.git cd degrees`

### 2️⃣ Exécuter

> Python recommandé : **3.12**

`python degrees.py small`

---

## 🧪 Tests

Avec _check50_ (si installé) :

`check50 ai50/projects/2024/x/degrees`

Vérifier le style :

`style50 degrees.py`

---

## 📁 Données

|Fichier|Contenu|
|---|---|
|`people.csv`|id, nom, année de naissance|
|`movies.csv`|id, titre, année de sortie|
|`stars.csv`|liens acteurs ↔︎ films|

---

## 🤖 Algorithme

- Représentation du problème sous forme de graphe
- Utilisation d'une **file FIFO** → BFS (shortest path garanti)
- Retour d'une liste de tuples `(movie_id, person_id)` jusqu’au but

---

## ✅ Résultat attendu

- Liste ordonnée des films permettant de relier les deux acteurs
- Message explicatif des étapes

Retour `None` si aucune connexion trouvée.

---

## 📝 À propos

Projet réalisé dans le cadre du cours **CS50’s Introduction to Artificial Intelligence with Python**.
Sources de données : IMDb (licence & permission CS50)

---

## 🙌 Remerciements

- Harvard CS50 AI Team
- IMDb pour les données (utilisées avec consentement)