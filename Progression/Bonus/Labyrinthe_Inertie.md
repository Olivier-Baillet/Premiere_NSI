# Le Labyrinthe à Inertie

## Principe et Représentation du Monde

Le jeu se déroule sur une grille carrée (par exemple $10 \times 10$ cases). Chaque case mesure 60 pixels.

Pour représenter notre grille en Python, nous utilisons une **matrice** (une liste de listes) où :

- `0` représente une case vide.
- `1` représente un mur (un obstacle).

La pierre est positionnée sur une case $(x, y)$. Lorsqu'une touche directionnelle est pressée, la pierre se déplace dans cette direction **et ne s'arrête que si la case suivante est un mur (`1`) ou le bord de l'écran**.

## ÉTAPE 1 : Le Squelette et l'Affichage de la Grille

**À FAIRE :** Créez un fichier `pierre.py`. Voici le code de départ qui génère le niveau et affiche la grille, la pierre (en gris), le point de départ A (en bleu) et l'arrivée B (en vert).

```python
import pygame
import sys

pygame.init()
fenetre = pygame.display.set_mode((600, 600)) # Grille de 10x10 cases de 60px
pygame.display.set_caption("La Pierre Glissante - NSI")

# CARTE DU JEU (0 = Vide, 1 = Mur)
# Matrice de 10 lignes et 10 colonnes
grille = [
    [1, 1, 1, 1, 1, 1, 1, 1, 1, 1],
    [1, 0, 0, 0, 1, 0, 0, 0, 0, 1],
    [1, 0, 1, 0, 0, 0, 1, 1, 0, 1],
    [1, 0, 1, 1, 0, 0, 0, 0, 0, 1],
    [1, 0, 0, 0, 0, 1, 1, 0, 0, 1],
    [1, 0, 1, 0, 0, 1, 0, 0, 1, 1],
    [1, 0, 1, 1, 0, 0, 0, 0, 0, 1],
    [1, 0, 0, 0, 0, 1, 0, 1, 0, 1],
    [1, 0, 0, 0, 0, 0, 0, 0, 0, 1],
    [1, 1, 1, 1, 1, 1, 1, 1, 1, 1]
]

# COORDONNÉES (Ligne, Colonne) dans la matrice
pierre_x = 1  # Colonne 1
pierre_y = 1  # Ligne 1

arrivee_x = 7 # Point B (Colonne 7)
arrivee_y = 6 # Point B (Ligne 6)

TAILLE_CASE = 60

while True:
    fenetre.fill((255, 255, 255))

    # Dessin de la grille
    for ligne in range(10):
        for col in range(10):
            x = col * TAILLE_CASE
            y = ligne * TAILLE_CASE

            if grille[ligne][col] == 1:
                pygame.draw.rect(fenetre, (50, 50, 50), (x, y, TAILLE_CASE, TAILLE_CASE)) # Mur Gris foncé
            else:
                pygame.draw.rect(fenetre, (230, 230, 230), (x, y, TAILLE_CASE, TAILLE_CASE), 1) # Grille

    # Dessin du Point B (Arrivée en Vert)
    pygame.draw.rect(fenetre, (0, 200, 0), (arrivee_x * TAILLE_CASE + 15, arrivee_y * TAILLE_CASE + 15, 30, 30))

    # Dessin de la Pierre (Cercle Gris)
    centre_x = pierre_x * TAILLE_CASE + TAILLE_CASE // 2
    centre_y = pierre_y * TAILLE_CASE + TAILLE_CASE // 2
    pygame.draw.circle(fenetre, (120, 120, 120), (centre_x, centre_y), 20)

    # Événements
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            pygame.quit()
            sys.exit()

    pygame.display.flip()
```

## ÉTAPE 2 : Coder l'Inertie (Le déplacement glissant)

Contrairement à un jeu classique où appuyer sur "Droite" déplace le personnage d'une seule case, ici, appuyer sur "Droite" doit lancer une boucle qui déplace la pierre **tant que** la case suivante est vide (`0`).

**À FAIRE : (MISSION A)** Ajoutez la détection des touches dans la boucle des événements. Complétez le code pour les directions **Gauche**, **Haut** et **Bas** en suivant le modèle de la direction **Droite**.

```python
        if event.type == pygame.KEYDOWN:

            if event.key == pygame.K_RIGHT:
                # TANT QUE la case juste à droite (colonne + 1) est vide (0)
                 # --- À COMPLÉTER ---
                 ...
                    pierre_x = ... # La pierre glisse d'une case vers la droite

            if event.key == pygame.K_LEFT:
                # --- À COMPLÉTER ---
                # Si on va à gauche, on teste la case (pierre_x - 1).
                # Quelle coordonnée doit-on modifier si la case est vide ?

            if event.key == pygame.K_UP:
                # --- À COMPLÉTER ---
                # Attention, monter d'une ligne revient à faire (pierre_y - 1) dans la matrice.

            if event.key == pygame.K_DOWN:
                # --- À COMPLÉTER ---
                # Descendre d'une ligne revient à faire (pierre_y + 1).
```

## ÉTAPE 3 : Condition de Victoire

La partie s'arrête avec succès dès que les coordonnées de la pierre correspondent exactement aux coordonnées de l'arrivée (Point B).

**À FAIRE :** 

1. Créez une variable `police` pour le texte.
2. Juste après le traitement des touches du clavier, ajoutez un test de comparaison : si `pierre_x == arrivee_x` et `pierre_y == arrivee_y`, alors affichez un message "BRAVO ! Objectif atteint" à l'écran et bloquez les mouvements.

## EXERCICES D'APPROFONDISSEMENT

### Défi 1 : Compteur de coups (Optimisation)

Le propre de ce genre de jeu est de résoudre l'énigme en un **minimum de mouvements**.

- Ajoutez une variable `score` initialisée à 0.
- Augmentez ce score de `1` chaque fois que le joueur appuie sur une touche directionnelle (mais uniquement si la pierre a effectivement bougé !).
- Affichez ce compteur en haut de l'écran.

### Défi 2 : Ajouter des "Trous" (Pièges mortels)

On souhaite ajouter de la difficulté en mettant des trous noirs sur la carte. Si la pierre passe ou s'arrête sur un trou, le joueur a perdu et la pierre réapparaît au point A.

- Modifiez la matrice en ajoutant une nouvelle valeur, par exemple `2`, à certains endroits stratégiques pour représenter les trous.
- Modifiez l'affichage pour dessiner ces cases en noir (ou rouge).
- Ajoutez la condition de défaite dans votre gestionnaire de mouvements.