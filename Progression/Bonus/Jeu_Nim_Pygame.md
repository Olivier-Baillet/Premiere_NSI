# Développement du Jeu de Nim avec Pygame

## Introduction & Règle du Jeu

Le **Jeu de Nim** (popularisé par l'émission *Fort Boyard*) se joue à deux joueurs avec un tas d'allumettes.

- On commence la partie avec **20 allumettes**.
- À chaque tour, un joueur peut retirer **1, 2 ou 3 allumettes**.
- **Règle (Variante Misère) :** Le joueur qui prend la dernière allumette a **perdu**.

## ÉTAPE 1 : Le Squelette Graphique

Pour commencer, nous mettons en place la structure d'affichage. Les boutons pour choisir le nombre d'allumettes à retirer sont définis grâce à des objets `pygame.Rect`.

**À FAIRE :** Créez un fichier nommé `nim.py`, copiez-y le code ci-dessous et exécutez-le.

```python
import pygame
import sys

pygame.init()
fenetre = pygame.display.set_mode((800, 600))
pygame.display.set_caption("Le Jeu de Nim - NSI")

# 1. VARIABLES D'ÉTAT DU JEU
allumettes_restantes = 20
joueur_actuel = 1  # Peut valoir 1 ou 2
partie_terminee = False
message = "Au tour du Joueur 1"

police = pygame.font.SysFont("Arial", 30)

# 2. CRÉATION DES BOUTONS (Zones de clic)
# Syntaxe : pygame.Rect(X, Y, Largeur, Hauteur)
btn1 = pygame.Rect(100, 500, 150, 50)
btn2 = pygame.Rect(325, 500, 150, 50)
btn3 = pygame.Rect(550, 500, 150, 50)

while True:
    fenetre.fill((255, 255, 255)) # Fond blanc

    # Affichage du message texte
    texte = police.render(message, True, (0, 0, 0))
    fenetre.blit(texte, (50, 50))

    # Affichage des allumettes
    for i in range(allumettes_restantes):
        x_allumette = 60 + i * 32
        pygame.draw.rect(fenetre, (139, 69, 19), (x_allumette, 200, 12, 200)) # Bois
        pygame.draw.rect(fenetre, (200, 0, 0), (x_allumette, 185, 12, 15))  # Bout rouge

    # Affichage des 3 boutons gris
    pygame.draw.rect(fenetre, (200, 200, 200), btn1)
    pygame.draw.rect(fenetre, (200, 200, 200), btn2)
    pygame.draw.rect(fenetre, (200, 200, 200), btn3)

    # Texte sur les boutons
    fenetre.blit(police.render("Prendre 1", True, (0,0,0)), (btn1.x + 20, btn1.y + 10))
    fenetre.blit(police.render("Prendre 2", True, (0,0,0)), (btn2.x + 20, btn2.y + 10))
    fenetre.blit(police.render("Prendre 3", True, (0,0,0)), (btn3.x + 20, btn3.y + 10))

    # Gestion des événements
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            pygame.quit()
            sys.exit()

    pygame.display.flip()
```

### Questions d'analyse :

1. Quelles sont les coordonnées du coin supérieur gauche et du coin inférieur droit du bouton `btn2` ?
2. Comment le programme sait-il combien d'allumettes dessiner à l'écran ? Quelle structure Python permet cela ?

## ÉTAPE 2 : Capter le clic et détecter le bouton (IHM)

En Pygame, l'événement `pygame.MOUSEBUTTONDOWN` permet de savoir quand l'utilisateur clique. On peut récupérer les coordonnées de la souris grâce à `event.pos`.

Plutôt que d'écrire des inégalités mathématiques complexes, nous allons utiliser la méthode `.collidepoint()` fournie par les objets `Rect`. Elle renvoie `True` si le clic a eu lieu à l'intérieur du rectangle.

**À FAIRE :** Complétez la boucle des événements dans votre code pour détecter sur quel bouton le joueur a cliqué.

```python
        if event.type == pygame.MOUSEBUTTONDOWN and not partie_terminee:
            # event.pos contient un tuple (x, y) de l'emplacement du clic
            position_clic = event.pos
            pris = 0 # Nombre d'allumettes à retirer

            # --- À COMPLÉTER (MISSION A) ---
            # Utilisez la méthode collidepoint pour savoir quel bouton a été cliqué.
            # Exemple : if btn1.collidepoint(position_clic): pris = 1
            # Écrivez les conditions pour btn1, btn2 et btn3 :

            # [Votre code pour la détection ici]

            # Si le clic a touché un bouton valide
            if pris > 0:
                allumettes_restantes = allumettes_restantes - pris
```

### Questions d'analyse :

1. Quel est l'intérêt d'ajouter la condition `and not partie_terminee` lors de la détection du clic de souris ?

## ÉTAPE 3 : Alternance des joueurs

Dès qu'un coup valide a été joué, le nombre d'allumettes diminue, mais c'est toujours au tour du même joueur car nous n'avons pas mis à jour l'état.

**À FAIRE :** (MISSION B) Juste après la ligne `allumettes_restantes = allumettes_restantes - pris`, écrivez une structure conditionnelle (`if / else`) qui permet de changer la valeur de `joueur_actuel`.

- Si `joueur_actuel` vaut 1, il doit devenir 2.
- S'il vaut 2, il doit devenir 1.
- N'oubliez pas de mettre à jour la chaîne de caractères de la variable `message` pour que le changement s'affiche à l'écran (Exemple : `message = "Au tour du Joueur " + str(joueur_actuel)`).

## ÉTAPE 4 : Sécurité et Fin de partie

Il reste deux problèmes majeurs à régler :

1. **La triche :** S'il reste 2 allumettes, un joueur peut cliquer sur "Prendre 3", ce qui amène le jeu à $-1$ allumette.
2. **La victoire :** Le jeu ne s'arrête jamais quand le tas atteint 0.

**À FAIRE :** (MISSION C) Ajoutez des conditions de sécurité et de fin de partie pour obtenir le comportement attendu.

1. Modifiez vos conditions de l'**Étape 2** pour qu'on ne puisse choisir un bouton *que s'il reste assez d'allumettes*.
    - *Exemple :* `if btn3.collidepoint(position_clic) and allumettes_restantes >= 3:`
2. À la fin de votre traitement de clic, ajoutez une vérification : si `allumettes_restantes == 0`, changez la variable `partie_terminee` à `True` et modifiez le `message` pour déclarer le vainqueur.
    
    *(Rappel : le joueur qui vient de jouer a pris la dernière allumette, il a donc perdu. C'est l'autre qui gagne !)*
    

## EXERCICES D'APPROFONDISSEMENT

### Défi A : L'effet de survol (*Hover*)

Pour rendre le jeu plus professionnel, faites en sorte que le bouton change de couleur lorsque la souris passe au-dessus de lui, avant même qu'on ne clique.

- *Indice :* Utilisez `pygame.mouse.get_pos()` dans votre boucle d'affichage pour récupérer la position de la souris à chaque instant, puis testez le `.collidepoint()` pour changer la couleur du bouton lors de l'appel à `pygame.draw.rect()`.

### Défi B : Mode "Contre l'Ordinateur" (Intelligence Artificielle)

Modifiez le jeu pour que le Joueur 1 affronte l'ordinateur (Joueur 2).

- Lorsque `joueur_actuel == 2`, utilisez le module `random` pour que la machine choisisse un nombre aléatoire cohérent (1, 2 ou 3) d'allumettes à retirer, attendez une seconde, puis appliquez le coup automatiquement sans attendre de clic.