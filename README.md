# ÉNONCÉ du TP1 — Analyse et transformation d’une image en niveaux de gris avec Python

## Objectif général

Dans ce travail pratique, vous devrez manipuler une image numérique comme un ensemble de données, puis analyser certaines de ses caractéristiques à l’aide de Python.

Ce TP vous permettra de réinvestir les notions vues jusqu’à maintenant dans le cours, notamment :

- l’utilisation d’un environnement Python local ;
- l’exécution de code dans un notebook Jupyter ;
- la manipulation de tableaux NumPy ;
- l’affichage de données avec Matplotlib ;
- la transformation simple d’images ;
- la création et la modification de dataframes avec Pandas.

L’objectif est de vous amener à comprendre qu’une image n’est pas seulement un objet visuel : c’est aussi une structure de données que l’on peut explorer, transformer et résumer.

---

## Travail à réaliser

Vous devez produire un notebook Jupyter dans lequel vous analysez une image en niveaux de gris, appliquez plusieurs transformations simples, puis organisez vos résultats dans un dataframe.

Vous devez utiliser Python et les librairies suivantes :

```python
import numpy as np
import matplotlib.pyplot as plt
import pandas as pd
from skimage import io, color
```

Vous pouvez également utiliser une image fournie par une librairie si vous le souhaitez.

---

## Choix de l’image

Pour ce TP, vous devez utiliser **une image en niveaux de gris de votre choix**.

Votre image doit respecter les conditions suivantes :

- elle doit être exploitable sous forme de matrice 2D ;
- elle doit être en niveaux de gris, ou convertie en niveaux de gris avant le travail ;
- elle doit être suffisamment nette et contrastée pour que les transformations soient visibles ;
- elle doit être appropriée au contexte scolaire.

Évitez :

- les images trop petites ;
- les images trop floues ;
- les images déjà binaires ;
- les images presque entièrement noires ou blanches ;
- les photos contenant des informations personnelles, des documents, des visages d’enfants ou d’autres contenus sensibles.

Si vous choisissez une image couleur, vous devez d’abord la convertir en niveaux de gris avant de commencer l’analyse.

Au début du notebook, indiquez en une ou deux phrases pourquoi vous avez choisi cette image.

---

## Consignes générales

- Le travail est individuel.
- Le notebook doit être exécutable du début à la fin.
- Le code doit être clairement organisé en sections.
- Chaque section doit contenir un titre ou un court commentaire expliquant ce qui est fait.
- Chaque image ou graphique affiché doit avoir un titre.
- Vous devez rédiger vos réponses explicatives dans le notebook, en français correct.
- Vous devez utiliser uniquement les notions vues jusqu’à maintenant dans le cours.

---

# Partie 1 — Chargement et exploration de l’image

1. Chargez votre image.
2. Affichez-la correctement avec Matplotlib.
3. Donnez les informations suivantes :
   - la forme de l’image ;
   - le type numérique de ses valeurs ;
   - la valeur minimale ;
   - la valeur maximale.

4. Expliquez brièvement ce que représentent ces informations.

### Attendu

Vous devez montrer que vous comprenez qu’une image est stockée sous forme de matrice numérique.

---

# Partie 2 — Extraction d’une zone d’intérêt

1. Sélectionnez une zone de l’image à l’aide du slicing.
2. Créez une copie de cette zone.
3. Affichez cette zone d’intérêt.
4. Indiquez ses dimensions.
5. Expliquez pourquoi il est préférable de travailler sur une copie lorsqu’on veut modifier une sous-partie de l’image.

### Attendu

Vous devez montrer que vous savez extraire une région d’un tableau NumPy et que vous comprenez la différence entre une vue et une copie.

---

# Partie 3 — Transformations de l’image

À partir de la zone d’intérêt extraite dans la partie 2, réalisez les transformations suivantes :

1. une version éclaircie ;
2. une version assombrie ;
3. une version seuillée partielle, où les pixels très foncés deviennent noirs, les pixels très clairs deviennent blancs, et les pixels intermédiaires conservent leur intensité ;
4. une version binaire, où chaque pixel doit prendre uniquement la valeur 0 ou la valeur 255.

Là, la distinction devient nette :

dans l’image seuillée partielle, on conserve encore certains gris ;

dans l’image binaire, on supprime tous les gris.

Pour chacune de ces transformations :

- effectuez la modification avec des opérations sur les tableaux NumPy ;
- affichez le résultat obtenu ;
- donnez un titre clair à l’image affichée.

### Important

Vous devez faire attention aux limites des valeurs des pixels. Les intensités d’une image en niveaux de gris ne doivent pas dépasser les bornes permises par leur type numérique.

### Attendu

Vous devez montrer que vous savez transformer les données d’une image et observer les conséquences visuelles de ces transformations.

---

# Partie 4 — Histogrammes et mise à plat des données

1. Utilisez `flatten()` pour transformer l’image originale en vecteur à une dimension.
2. Affichez l’histogramme des intensités de l’image originale.
3. Choisissez une image transformée parmi celles produites à la partie 3.
4. Transformez également cette image en vecteur.
5. Affichez son histogramme.
6. Comparez brièvement les deux histogrammes.

Votre comparaison doit répondre aux questions suivantes :

- Que remarquez-vous ?
- Quelle transformation semble avoir modifié la répartition des intensités ?
- Que peut-on déduire de l’histogramme sur l’image elle-même ?

### Attendu

Vous devez montrer que vous comprenez le lien entre la distribution numérique des pixels et l’aspect visuel de l’image.

---

# Partie 5 — Organisation des résultats avec Pandas

Vous devez maintenant créer un dataframe qui résume les différentes images obtenues.

Le dataframe doit contenir au minimum une ligne pour chacune des images suivantes :

- image originale ;
- zone d’intérêt ;
- image éclaircie ;
- image assombrie ;
- image seuillée.

Pour chaque image, votre dataframe doit contenir au minimum les informations suivantes :

- nom de l’image ;
- nombre de lignes ;
- nombre de colonnes ;
- valeur minimale ;
- valeur maximale ;
- moyenne ;
- écart-type.

Ensuite, vous devez effectuer les opérations suivantes :

1. afficher le dataframe complet ;
2. renommer au moins deux colonnes ;
3. supprimer au moins une colonne que vous jugez peu utile ;
4. créer un sous-dataframe contenant seulement les images transformées ;
5. créer un second sous-dataframe contenant seulement les colonnes les plus utiles pour comparer les intensités ;
6. afficher ces résultats.

### Attendu

Vous devez montrer que vous êtes capables d’utiliser un dataframe pour organiser, sélectionner et comparer des données.

---

# Partie 6 — Interprétation des résultats

Rédigez une courte conclusion d’environ 10 à 15 lignes dans laquelle vous répondez aux questions suivantes :

1. Pourquoi avez-vous choisi cette image ?
2. Quelle transformation vous semble la plus utile pour faire ressortir certaines zones de l’image ?
3. Quelle différence faites-vous entre l’image affichée à l’écran et les données numériques qui la représentent ?
4. En quoi l’utilisation d’un histogramme aide-t-elle à mieux comprendre une image ?
5. En observant votre dataframe, quelle transformation semble modifier le plus les intensités des pixels ? Justifiez votre réponse à l’aide des valeurs numériques obtenues.

### Attendu

Votre réponse doit montrer que vous savez relier :

- l’observation visuelle ;
- les transformations appliquées ;
- les données numériques ;
- les informations résumées dans un dataframe.

---

# Contraintes techniques

Votre notebook doit contenir :

- du code fonctionnel ;
- des affichages clairs ;
- des réponses rédigées ;
- une structure propre.

Vous ne devez pas simplement empiler du code. Le notebook doit pouvoir être lu comme un travail expliqué.

---

# Critères d’évaluation

## 1. Qualité de l’exploration initiale — 15 %

- image correctement chargée et affichée ;
- propriétés correctement identifiées ;
- explications justes.

## 2. Extraction et manipulation de la zone d’intérêt — 15 %

- slicing correct ;
- copie correctement créée ;
- compréhension de la manipulation locale de l’image.

## 3. Transformations réalisées — 25 %

- transformations correctes ;
- bonne gestion des intensités ;
- affichages clairs et pertinents.

## 4. Histogrammes et analyse — 15 %

- utilisation correcte de `flatten()` ;
- histogrammes justes ;
- interprétation pertinente.

## 5. Utilisation de Pandas — 20 %

- dataframe complet ;
- renommage de colonnes ;
- suppression de colonne ;
- sélection de lignes et de colonnes ;
- clarté des résultats.

## 6. Qualité générale du notebook — 10 %

- structure ;
- lisibilité ;
- rigueur ;
- qualité du français.

---

# Conseils

- Testez votre notebook du début à la fin avant de le remettre.
- Vérifiez que chaque cellule s’exécute correctement.
- Relisez vos explications.
- Assurez-vous que vos titres et vos affichages permettent de comprendre rapidement votre démarche.
- Ne vous contentez pas d’obtenir un résultat visuel : cherchez toujours à comprendre ce que disent les données.

---

# Défi facultatif

Ajoutez une section bonus dans laquelle vous appliquez la même démarche à une deuxième image en niveaux de gris, puis comparez les résultats obtenus.

---

# Petit rappel utile

Une image peut sembler noir et blanc à l’œil, tout en étant stockée en couleur dans un tableau à trois dimensions. Vous devez donc vérifier la structure réelle de votre image avant de commencer le travail.

---
