# TP Bonus : Modularité (avec Turtle)

## Présentation du TP

### But

On souhaite écrire un programme qui permet de générer « aléatoirement » le dessin d’une rue de 4 immeubles.
On utilisera pour cela le module Turtle de Python.

![image.png](TP%20Bonus%20Modularit%C3%A9%20(avec%20Turtle)/image.png)

### Contraintes

Les contraintes urbanistiques sont les suivantes :
o Les immeubles ont au minimum un rez-de-chaussée et au maximum 4 étages (5 niveaux) ;
o Les immeubles ont une largeur de 140 pixels;
o Les immeubles ont une couleur unique pour toute la façade ;
o Chaque niveau (rez-de-chaussée ou étage) a une façade de hauteur 60 pixels;
o Les rez-de-chaussée n'ont qu'une seule porte et 2 fenêtres placées aleatoirement ;
o Toutes les fenêtres sont identiques, de taille 30 pixels sur 30 pixels ;
o Toutes les portes fenêtre ont un balcon et font une taille de 30 pixels en largeur et 50 pixels en hauteurs
o Le toit peut avoir 2 formes : plat ou triangulaire ::

- Si le toit est plat : il fait une épaisseur de 10 pixels
- Si le toit est triangulaire, il fait une hauteur de 40 pixels pour une base de 160 pixels

### Exemples

La série d'exemples ci-dessous est basée sur :

- une couleur aléatoire pour les façades ;
- deux modèles de toits ;
- deux modèles de portes avec une couleur aléatoire ;
- deux modèles d'ouvertures pour les étages : fenêtre ou porte-fenêtre avec balcon ;
- trois éléments horizontalement pour chaque niveau.

![image.png](TP%20Bonus%20Modularit%C3%A9%20(avec%20Turtle)/image%201.png)

### Travail à faire

Proposer un programme sous forme de modules qui réponde au problème posé en utilisant le module Turtle de Python.
Vous utiliserez donc le plus de petites fonctions possible comme décrit ci-dessous.

![image.png](TP%20Bonus%20Modularit%C3%A9%20(avec%20Turtle)/image%202.png)

Vous travaillerez collectivement et en interdépendance à travers des importations de
modules.
Pour cela on a recensé toutes les fonctions à écrire. Leurs dépendances sont décrites dans le
schéma ci-contre. 
Vous devez donc vous répartir les modules à écrire en commençant par ceux du bas car il ne dépende pas des autres.

Pour vous aider dans votre tâche, dans chaque module, les importations et les docstrings ont
déjà été faits ainsi que les commentaires. Il ne vous reste qu’à écrire le code en ayant bien compris ce que votre module importe avant de commencer.

```python
def immeuble(x, y_sol)
#x : abscisse du centre de l'étage
#y_sol : ordonnée du sol du la rue

def sol(y_sol):
#y_sol : ordonnée du sol du la rue

def rdc(x, y_sol, c_facade, c_porte) :
#x : (int) abscisse du centre
#y_sol : ordonnée du sol du la rue
#c_facade : couleur de la façade
#c_porte : couleur de la porte

def etage(x, y_sol, couleur, niveau) :
#x : abscisse du centre de l'étage
#y_sol : ordonnée du sol du la rue
#couleur : couleur de la façade de l'étage
#niveau : numéro de l'étage en partant de 0 ( RDC)

def couleur_aleatoire():
#Cette fonction retourne un triplet de 3 nombres
#entiers compris entre 0 et 255 correspondant à du RGB

def toit(x, y_sol, niveau):
#x : abscisse du centre de l'étage
#y_sol: ordonnée du sol
#niveau : numéro de l'étage en partant de 0 (RDC)

def porte(x,y,couleur):
#x est l'abscisse du centre de la porte
#y est l'ordonnée du sol du niveau de la porte

def facade(x, y_sol, couleur, niveau):
#x : abscisse du centre de la façade
#y_sol : ordonnée du sol du la rue
#couleur : couleur de la façade
#niveau : num du niveau (0 pour les rdc, ...)

def fenetre(x,y):
#x est l'abscisse du centre de la fenêtre
#y est l'ordonnée du sol du niveau de la fenêtre

def fenetre_balcon(x,y):
#x est l'abscisse du centre de la porte-fenêtre-balcon
#y est l'ordonnée du sol du niveau de la portefenetre-balcon

def toit1(x, y_sol, niveau):
#x : abscisse du centre du toit
#y_sol : ordonnée du sol du la rue
#Niveau : num du niveau (0 pour les rdc, ...)

def toit2(x, y_sol, niveau):
#x : abscisse du centre du toit
#y_sol : ordonnée du sol du la rue
#niveau : num du niveau (0 pour les rdc, ...)

def rectangle(x,y,w,h):
#x, y : coordonnées du centre de la base de rectangle
#w : largeur du rectangle
#h : hauteur du rectangle

def trait(x1,y1,x2,y2):
#x1, y1 : coordonnées du début du trait
#x2, y2 : coordonnées de la fin du trait
```