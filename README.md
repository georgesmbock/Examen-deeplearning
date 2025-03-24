Classification des Cellules Infectées par le Paludisme à l’Aide de CNN
## Description du Projet
Ce projet vise à classer les images de cellules infectées et non infectées par le paludisme à l’aide de réseaux de neurones convolutifs (CNN). Deux architectures CNN ont été proposées et comparées pour identifier celle offrant les meilleures performances.

## Structure du Projet
Importation des Packages : Chargement des bibliothèques nécessaires (Keras, TensorFlow, OpenCV, etc.)

Prétraitement des Données : Chargement, redimensionnement et normalisation des images.

Exploration Visuelle : Visualisation des cellules infectées et non infectées.

Création des Modèles CNN : Proposition et entraînement de deux architectures CNN.

Évaluation des Performances : Comparaison des modèles à l’aide des métriques d’évaluation.

## Technologies Utilisées
Python 3.x

TensorFlow / Keras

OpenCV

Matplotlib & Seaborn

NumPy & Pandas

Scikit-Learn

## Exploration des Données
Les données sont issues d’un ensemble d’images de cellules classées en deux catégories :

Parasitized (1) : Cellules infectées par le paludisme

Uninfected (0) : Cellules non infectées

Exemples de cellules infectées et non infectées :

Cellules Infectées :

Cellules Non Infectées :

## Prétraitement des Données
Les images ont été redimensionnées à 50x50 pixels et converties en tableaux numpy.

Une normalisation a été appliquée pour réduire les valeurs entre 0 et 1.

Les données ont été divisées en :

80 % pour l’entraînement

10 % pour la validation

10 % pour le test

## Architecture des Modèles CNN
### Modèle 1 : CNN Simple
3 Convolution Layers (32, 64, 64 filtres)

MaxPooling2D après chaque couche

Dense Layer (128 neurones) avec Dropout (0.5)

Fonction d’activation : ReLU

Sortie : 1 Neurone (Sigmoïde)

Optimiseur : Adam

Perte : Binary Crossentropy

Nombre de Paramètres :

Total : 187,649 paramètres

### Modèle 2 : CNN Amélioré avec Batch Normalization
4 Convolution Layers (32, 64, 128, 256 filtres)

BatchNormalization après chaque convolution

MaxPooling2D après chaque couche

Dense Layers (256 et 128 neurones) avec Dropout (0.5)

Fonction d’activation : ReLU

Sortie : 1 Neurone (Sigmoïde)

Optimiseur : Adam avec un Learning Rate de 0.0001

Perte : Binary Crossentropy

Nombre de Paramètres :

Total : 489,153 paramètres

## Entraînement des Modèles
Nombre d’Époques : 10

Batch Size : 64

Callback : EarlyStopping et ReduceLROnPlateau

Optimiseur : Adam

Critère d’Arrêt Précoces : Patience de 2 à 3 epochs sans amélioration

## Performances des Modèles
Modèle 1 : CNN Simple
Précision d’Entraînement : 96.52 %

Précision de Validation : 95.90 %

Perte de Validation : 0.1248

Modèle 2 : CNN Amélioré
Précision d’Entraînement : 95.84 %

Précision de Validation : 93.75 %

Perte de Validation : 0.1704

## Conclusion
Le Modèle 1 a montré une meilleure généralisation et stabilité avec une précision de validation de 95.9 %.

Le Modèle 2 a connu un problème de surapprentissage, malgré une meilleure capacité d’apprentissage sur les données d’entraînement.

Modèle Recommandé : Modèle 1 pour une classification efficace des cellules infectées.

## Prédictions
Le modèle optimal (Modèle 1) a été utilisé pour effectuer des prédictions sur l’ensemble de test.
Voici quelques exemples de résultats :

Classe Prédite : 0 (Non infectée)

Classe Réelle : 0

Classe Prédite : 1 (Infectée)

Classe Réelle : 1

