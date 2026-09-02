# Approfondissement Python (Boucle & Fonction)

# Objectifs du TP

Ce TP a pour objectif d'approfondir vos connaissances en Python, particulièrement sur les structures de contrôle (boucles) et les fonctions. Vous mettrez en pratique les concepts théoriques vus en cours à travers différents exercices.

## Partie 1 : Les boucles en Python

### Rappel théorique

En Python, il existe deux types principaux de boucles :

- **La boucle for** : utilisée pour itérer sur une séquence (liste, tuple, chaîne de caractères, etc.)
- **La boucle while** : exécute un bloc de code tant qu'une condition est vraie

### Exercice 1 : Analyse de boucles

Pour chacun des exemples suivants, déterminez sans exécuter le nombre d'itérations et la valeur finale des variables :

```python
# Exemple 1
compteur = 0
for i in range(5):
    compteur += i
print(compteur)

# Exemple 2
n = 10
somme = 0
while n > 0:
    somme += n
    n -= 2
print(somme)

# Exemple 3
liste = [3, 7, 2, 8, 4]
resultat = 0
for element in liste:
    if element % 2 == 0:
        resultat += element
print(resultat)
```

### Exercice 2 : Créer vos propres boucles

Écrivez des programmes Python pour réaliser les tâches suivantes :

- Afficher les 10 premiers nombres de la suite de Fibonacci (rappel Fibo)
- Calculer la factorielle d'un nombre entré par l'utilisateur (factorielle + input)
- Déterminer si un nombre entré par l'utilisateur est premier (input)

<aside>
💡

Input() est une fonction qui a pour but de stopper le programme jusqu’à que l’utilisateur entre une information et appuie sur “entrée”.
Exemple : age = input(”Quelle est ton âge ?”)

</aside>

## Partie 2 : Les fonctions en Python

### Rappel théorique

Une fonction est un bloc de code réutilisable qui effectue une tâche spécifique. En Python, les fonctions sont définies avec le mot-clé `def` et peuvent accepter des paramètres et retourner des valeurs.

### Exercice 3 : Analyse de fonctions

Pour chacune des fonctions suivantes, déterminez ce qu'elle fait et quelle sera la valeur retournée pour les paramètres indiqués :

```python
# Fonction 1
def mystere1(n):
    if n <= 1:
        return n
    else:
        return mystere1(n-1) + mystere1(n-2)

# Que retourne mystere1(5) ?

# Fonction 2
def mystere2(liste):
    if len(liste) <= 1:
        return liste
    else:
        pivot = liste[0]
        gauche = [x for x in liste[1:] if x < pivot]
        droite = [x for x in liste[1:] if x >= pivot]
        return mystere2(gauche) + [pivot] + mystere2(droite)

# Que retourne mystere2([5, 2, 9, 1, 7]) ?
```

### Exercice 4 : Créer vos propres fonctions

Écrivez des fonctions Python pour réaliser les tâches suivantes :

- Une fonction qui calcule le PGCD de deux nombres en utilisant l'algorithme d'Euclide
- Une fonction qui convertit une température de Celsius en Fahrenheit (et vice-versa)
- Une fonction récursive qui calcule la somme des n premiers entiers naturels

## Partie 3 : Projet intégratif

Pour finaliser ce TP, vous devrez créer un petit programme qui utilise à la fois des boucles et des fonctions pour résoudre un problème concret.

### Exercice 5 : Analyse de données

Considérez la liste suivante qui contient les températures moyennes (en °C) pour chaque mois de l'année :

```python
temperatures = [3.2, 4.1, 7.3, 10.8, 14.5, 17.6, 19.8, 19.5, 16.1, 11.7, 6.9, 3.8]
```

Écrivez un programme qui :

- Calcule et affiche la température moyenne annuelle
- Trouve le mois le plus froid et le mois le plus chaud
- Calcule l'écart type des températures
- Convertit toutes les températures en Fahrenheit et les affiche