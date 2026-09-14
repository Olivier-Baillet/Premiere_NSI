# Exercices sur la boucle for ... in

## **Exercice 1**

On donne une liste d'acteurs :

```python
liste_acteurs = ['Tahar', 'Omar', 'Guillaume', 'Swann', 'Alex', 'Roschdy']
```

Utilisez cette liste pour produire la sortie suivante:

```python
Tahar a eu le César du meilleur acteur
Omar a eu le César du meilleur acteur
Guillaume a eu le César du meilleur acteur
Swann a eu le César du meilleur acteur
Alex a eu le César du meilleur acteur
Roschdy a eu le César du meilleur acteur
```



> 
> 
> 
> ### **Concaténation de caractères**
> 
> Il est possible de *coller* (le vrai mot est *concaténer*) deux chaînes de caractères par l'opérateur `+` :
> 
> ```python
> >>> "a" + "b"
> 'ab'
> ```
> 

## **Exercice 2**

Dans l'extrait de code suivant:

• `chaine` est une variable initialisée avec un `str` vide : `""`;
• on veut qu'en sortie de programme cette variable contienne la valeur `'bravo'`.

L'idée est d'ajouter une par une les lettres à la variable `chaine`.
À l'exécution, le programme doit afficher uniquement `bravo`.

Compléter le code.

```python
chaine = ""
for ... in ['b', 'r', 'a', 'v', 'o']:
    ...
print(chaine)
```

Cette variable chaine est appelée un **accumulateur**.



## **Exercice 3**

En Python, la fonction `ord` renvoie le code Unicode d'un caractère et la fonction `chr` le contraire: elle renvoie le caractère correspondant à un code Unicode.

Par exemple:

```python
>>> ord('a')
97
>>> chr(97)
'a'
```

Voici une liste contenant les codes Unicode des lettres d'un mot secret... À vous d'écrire un programme où en sortie, la variable `mot_secret` contiendra la chaîne de caractères de ce mot.

```python
mystere = [111, 107, 44, 32, 98, 105, 101, 110, 32, 106, 111, 117, 233]
mot_secret = ""

# à vous !
```



## **Exercice 4**

On souhaite calculer la somme des 1000 premiers nombres entiers naturels, c'est-à-dire:

Écrire un programme avec une variable `somme` **accumulateur** (comme à l'exercice 3) qui contiendra la valeur souhaitée en fin de programme.



## **Exercice 5**

Calculer $1 * 2 * 3 * … 99 * 100$ .


## **Exercice 6**

Proposer un code qui écrit la **table de multiplication** de 7, de 8 et de 9.
La sortie doit ressembler à :

```python
7*1 = 7

7*2 = 14

...    
...

9*9 = 81    
```



## **Exercice 7**

Sur un jeu d'échecs, les cases sont repérées par une lettre (de A jusqu'à H) et par un chiffre (de 1 jusqu'à 8).
Les cases sont donc A1, A2, A3, ..., H7, H8.
Proposer un code qui écrit **toutes** les cases possibles.



Autre solution utilisant la conversion d'un entier en chaine de caractères, grâce à la fonction `str` :

```python
for lettre in 'ABCDEFGH':
    for chiffre in range(1, 9):
        case = lettre + str(chiffre)
        print(case)
```

## **Exercice 8**

Dans ma trousse je dispose de 5 feutres de couleur :
• jaune (J)
• vert (V)
• noir (N)
• bleu (B)
• orange (O)

Pour un exercice, je dois colorier 3 pastilles en choissant sans aucune contrainte des couleurs parmi les 5 disponibles. Je peux tout colorier en jaune (`JJJ`) ou bien colorier la 1ère en orange, la 2ème en bleu, la 3ème en vert (`OBV` )

Faire afficher la totalité des combinaisons possibles.
