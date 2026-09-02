# La boucle while

La boucle `for` s'utilise lorsqu'on connaît à l'avance le nombre de répétitions à effectuer: soit un nombre entier, soit un ensemble de valeurs contenus dans un *iterable* dont le nombre de valeurs est fixe. On parle de boucle **bornée**.

Mais il arrive fréquemment qu'on doive répéter des instructions un *certain* nombre de fois, qui n'est pas connu à l'avance. On a donc besoin d'une boucle **non bornée**, `while` en Python, qui s'éxécutera tant qu'une condition est réalisée et qui stoppera dès que cette condition ne le sera plus.

Si jamais cela arrive...

![](https://cgouygou.github.io/1NSI/T06_Python/images/danger.jpg)

## Un premier exemple

> Combien de fois doit-on plier une feuille de papier pour que son épaisseur dépasse la hauteur de la Tour Eiffel (324 m)?
> 

Sous réserve que cela soit techniquement possible, on va donc partir d'une feuille de papier classique, d'une épaisseur de 0,1 mm, puis on va plier, plier, plier... sachant que l'épaisseur va doubler à chaque pliage.

Il est donc nécessaire d'utiliser une boucle pour répéter ces pliages (c'est-à-dire les calculs successifs de l'épaisseur de papier). Répeter, d'accord, mais combien de fois? Justement, on ne le sait pas, puisque c'est la question !!!

En revanche, on sait qu'on doit s'arrêter de plier dès que l'épaisseur de papier sera supérieure à 324 m. Autrement dit, on doit repéter **tant que l'épaisseur est inférieure à 324 m**.

On obtient donc le code:

```python
epaisseur = 0.0001
nombre_pliages = 0

while epaisseur < 324:
    epaisseur = 2 * epaisseur
    nombre_pliages += 1

print(f"Il faut {nombre_pliages} pliages.")
```

---

## La syntaxe

**La boucle `while`**

**Syntaxe générale:**

```python
while expression:
    *instructions à répéter*
```

---

**Remarques:**

- `expression` doit renvoyer une valeur **booléenne** : une égalité, comparaison, appartenance, etc. ;
- `while` repète le bloc d'instructions à répéter tant que cette expression est égale à `True` ;
- il faut terminer la ligne commençant par `while` par `:` ;
- le bloc d'instructions à répéter (le corps de la boucle) doit être indenté.

---

## Les dangers de la boucle `while`

### Ne JAMAIS ENTRER dans la boucle

**No Entrance**

Le programme suivant ne va pas faire grand chose... à part afficher `fini!`. Voyez-vous pourquoi?

```python
toto = 0
while toto >= 1:
    toto = toto + 1
    print("ce texte ne s'écrira jamais")
print("fini!")
```

---

### Ne JAMAIS SORTIR de la boucle

Je vous rassure tout de suite, aucun programmeur professionnel n'est passé à côté de ce piège...

**No Exit**

Que va faire le programme suivant?

```python
toto = 1
while toto < 10:
    toto = 2
    print("ok")
print("fini!")
```

---

### **Éviter une boucle infinie**

Il faut **toujours** s'assurer que le corps de la boucle contienne une instruction qui fera en sorte qu'à un moment donné l'expression booléenne prendra la valeur `False`.

![](https://cgouygou.github.io/1NSI/T06_Python/images/while_meme.jpg)

---

## Exercices

### **Exercice 1**

Trouver le plus petit nombre entier $n$ tel que $2^n$ soit supérieur à 1 milliard.

### **Exercice 2**

Demander à l'utilisateur de taper la lettre S (puis sur la touche Entrée). Recommencer tant qu'il n'a pas obéi.

On utilisera la fonction `input` pour récupérer une saisie clavier : 

```python
n = input('Entrez une touche')
```

### **Exercice 3**

Le jeu du FizzBuzz : il s'agit de compter à partir de 1 en remplaçant certains nombres par Fizz, Buzz ou Fizzbuzz :

- si le nombre est divisible par 3, on ne le dit pas et on le remplace par Fizz.
- si le nombre est divisible par 5, on ne le dit pas et on le remplace par Buzz.
- si le nombre est divisible par 3 et par 5, on ne le dit pas et on le remplace par FizzBuzz.
- dans tous les autres cas, on donne le nombre.

Ainsi on doit obtenir : 1, 2, Fizz, 4, Buzz, Fizz, 7, 8, etc.

Écrire un code qui joue au FizzBuzz jusqu'à 50 (ou plus).

### **Exercice 4**

Écrire un programme de «révision» des tables de multiplication :
On doit demander plusieurs fois le résultat d'une multiplication de deux nombres choisis aléatoirement et le programme doit s'arrêter quand 10 bonnes réponses ont été données. Il faut également afficher le score (c'est-à-dire le nombre d'essais pour atteindre 10 bonnes réponses).

Ouvertures possibles: en fin de test, demander si l'utilisateur veut recommencer, mémoriser le meilleur score, ...

---

Exercice Bonus :

### **Exercice : pydéfi**

SW IV : On passe en vitesse lumière : [https://pydefis.callicode.fr/defis/VitesseLumiere/txt](https://pydefis.callicode.fr/defis/VitesseLumiere/txt)

Comment compter le nombre de passages dans la boucle?

### **Exercice : pydéfi**

L'algorithme du professeur Guique : [https://pydefis.callicode.fr/defis/Algorithme/txt](https://pydefis.callicode.fr/defis/Algorithme/txt)