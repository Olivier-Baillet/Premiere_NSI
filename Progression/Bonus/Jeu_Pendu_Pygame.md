# Développement du Jeu du Pendu avec Pygame

## Introduction & Principe du Jeu

Le but de ce TP est de réaliser le célèbre jeu du **Pendu**. La machine choisit un mot (ici fixe pour commencer), et l'utilisateur doit deviner ce mot en tapant des lettres au clavier.

- Si la lettre est dans le mot, elle est révélée.
- Si la lettre n'est pas dans le mot, le joueur perd une vie et une partie du pendu se dessine.
- Le joueur a droit à **6 erreurs maximum** avant de perdre la partie.

## ÉTAPE 1 : Mettre en place la fenêtre et l'état initial

Pour démarrer, nous avons besoin d'une fenêtre graphique et de variables pour stocker "l'état" de notre jeu (le mot secret, le mot affiché avec des tirets, et le compteur d'erreurs).

**À FAIRE :** Créez un fichier nommé `pendu.py`, copiez-y le code ci-dessous et exécutez-le.

```python
import pygame
import sys

# Initialisation de Pygame
pygame.init()
fenetre = pygame.display.set_mode((800, 600))
pygame.display.set_caption("Mon Premier Pendu - NSI")

# VARIABLES D'ÉTAT DU JEU
mot_secret = "INFORMATIQUE"
# On crée une liste de tirets de la même longueur que le mot secret
mot_affiche = ["_", "_", "_", "_", "_", "_", "_", "_", "_", "_", "_", "_"]
erreurs = 0

# Police d'écriture pour l'affichage du texte
police = pygame.font.SysFont("Arial", 40)

# BOUCLE PRINCIPALE
while True:
    fenetre.fill((255, 255, 255)) # Efface l'écran avec un fond blanc

    # Affichage du mot masqué à l'écran
    # .join() permet de transformer la liste ['_', '_'] en texte "_ _"
    texte_mot = police.render(" ".join(mot_affiche), True, (0, 0, 0))
    fenetre.blit(texte_mot, (350, 250))

    # Écoute des événements (Fermeture de la fenêtre)
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            pygame.quit()
            sys.exit()

    pygame.display.flip() # Met à jour l'affichage
```

### Questions d'analyse :

1. Quel est le rôle de la ligne `" ".join(mot_affiche)` ? Que se passerait-il si on affichait directement la variable `mot_affiche` ?
2. Quelle est la dimension (largeur et hauteur) de la fenêtre de jeu en pixels ?

## ÉTAPE 2 : Capter les touches du clavier (IHM)

Nous voulons maintenant que le programme réagisse lorsque le joueur appuie sur une touche du clavier.

**À FAIRE :** Dans la boucle des événements (`for event in pygame.event.get():`), ajoutez le bloc de code suivant juste en dessous de la gestion de la fermeture :

```python
        if event.type == pygame.KEYDOWN:
            # On récupère le caractère tapé
            lettre = ...

            # On vérifie si la lettre tapée est bien dans le mot secret
            ...
```

### Questions d'analyse :

1. Rechercher comment fonctionne `event.unicode.upper()` puis l’utiliser .
2. Compléter le code afin de vérifier si la lettre tapée est bien dans le mot secret :
    1. Si c’est le cas, on remplace le tiret par la lettre
    2. Sinon on ajoute une erreur

## ÉTAPE 3 : Dessiner la potence selon les erreurs

Pygame utilise un repère mathématique où l'origine $(0,0)$ est située en **haut à gauche** de l'écran. L'axe des $Y$ est dirigé vers le bas.

**À FAIRE :** Dans la boucle principale, juste après `fenetre.fill((255, 255, 255))`, ajoutez les instructions de dessin suivantes. Elles s'afficheront de manière cumulative selon le nombre d'erreurs du joueur.

```python
    # DESSIN DU PENDU (Évolutif)
    if erreurs >= 1:
        pygame.draw.line(fenetre, (0,0,0), (100, 500), (250, 500), 5) # Base au sol
    if erreurs >= 2:
        pass #pygame.draw.line(fenetre, ...) # Poteau vertical
    if erreurs >= 3:
        pass #pygame.draw.line(fenetre, ...) # Barre transversale
    if erreurs >= 4:
        pygame.draw.line(fenetre, (0,0,0), (275, 200), (275, 250), 3) # Corde
    if erreurs >= 5:
        pygame.draw.circle(fenetre, (0,0,0), (275, 275), 25, 3)       # Tête (Cercle)
    if erreurs >= 6:
        pygame.draw.line(fenetre, (0,0,0), (275, 300), (275, 420), 3) # Corps (Tronc)
```

### Questions d'analyse :

1. Pour le dessin de la corde (`erreurs >= 4`), quelles sont les coordonnées du point de départ et du point d'arrivée de la ligne ?
2. Pourquoi utilise-t-on une suite de blocs `if` indépendants plutôt qu'une structure `if / elif / elif` ?
3. Compléter le code pour les erreurs 2 et 3. 

## ÉTAPE 4 : Gérer la fin de la partie (Victoire / Défaite)

Le jeu doit s'arrêter et afficher un message clair si le joueur a trouvé toutes les lettres ou s'il a atteint 6 erreurs.

**À FAIRE :** 1. Tout en haut du fichier, ajoutez deux variables booléennes.

2. Créez une nouvelle police pour le message de fin : `police_fin = pygame.font.SysFont("Arial", 50, bold=True)`.

3. Modifiez la condition du clavier pour qu'on ne puisse jouer **que si** `not gagne and not perdu`.

4. Ajoutez les conditions de victoire et de défaite dans le code (recherchez l'absence de `_` pour la victoire).

## EXERCICES D'APPROFONDISSEMENT

Si vous avez terminé le jeu de base, choisissez l'une des extensions suivantes pour enrichir votre projet :

### Défi A : Rendre le mot dynamique

Actuellement, le mot est toujours `"INFORMATIQUE"`.

- Importez le module `random`.
- Créez une liste contenant 5 à 10 mots différents.
- Modifiez l'initialisation pour qu'un mot soit tiré au sort à chaque lancement.
- *Attention :* Pensez à adapter la création de la liste `mot_affiche` pour qu'elle s'ajuste automatiquement à la taille du mot sélectionné !

### Défi B : Ajouter les membres manquants

Le pendu actuel s'arrête au tronc à la 6e erreur. Modifiez les étapes de dessin (et changez le nombre maximal d'erreurs autorisées à 8) pour ajouter le dessin des deux bras et des deux jambes au bonhomme. Vous devez calculer leurs coordonnées géométriques $(X, Y)$ par rapport au corps.