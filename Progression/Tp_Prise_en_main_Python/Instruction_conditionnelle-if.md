# L'instruction conditionnelle if

L'instruction conditionnelle `if` permet de soumettre l'exécution d'instructions à une condition donnée. Cette condition sera une expression booléenne, comme pour la boucle `while`.

![](https://cgouygou.github.io/1NSI/T06_Python/images/if_meme.jpg)

## Premiers exemples

Testez les codes suivants (plusieurs fois en variant les valeurs) dans un IDE:

### **`if`**

```python
n = int(input("Donne moi un nombre: "))
if n == 42:
    print("C'est le sens de la vie")
```

---

### **`if else`**

```python
n = int(input("Donne moi un nombre: "))
if n == 42:
    print("C'est le sens de la vie")
else:
    print("Ce n'est pas le sens de la vie")
```

---

### **Imbriquer les `if`**

```python
moyenne  = int(input("Donne moi une moyenne : "))

if moyenne < 8:
    print("raté")
else:
    if moyenne < 10:
        print("repêchage")
    else:
        if moyenne < 12:
            print("admis")
        else:
            if moyenne < 14:
                print("mention AB")
            else:
                if moyenne < 16:
                    print("mention B")
                else:
                    print("mention TB")
```

---

## La syntaxe

**L'instruction `if`**

**Syntaxe générale:**

```python
if expression:
    *instructions à effectuer si expression est vraie*
else:
    *instructions à effectuer si expression est fausse*
```

---

**Remarques:**

- `expression` est évaluée par Python à l'exécution du programme : elle doit renvoyer une valeur **booléenne** (`True` ou `False)`. En pratique, c'est souvent une égalité, une comparaison, une appartenance ou une opération booléenne (`and`, `or`) sur ce genre d'expressions ;
- il faut terminer la ligne commençant par `if` et `else` par `:` , comme pour le `for` ;
- les instructions à effectuer selon l'évaluation d'`expression` doivent être indentées;
- le `else` est facultatif (comme au premier exemple);
- en cas d'emploi du `else`, aucune expression n'est attendue.

**Exemple incontournable**

Pour tester si un nombre `n` est divisible par un nombre `d`, on teste si le **reste de la division euclidienne** de `n` par `d` est égal à 0 :

```python
n = int(input("Donne moi un nombre: "))
if n % 2 == 0:
    print(n, "est un nombre pair")
else:
    print(n, "est un nombre impair")
```

---

## `elif` et les cas multiples

Dans les situations où l'on veut effectuer des instructions différentes selon les différentes valeurs prises par une variable, comme dans le troisième exemple, on peut imbriquer les instructions `if` ... `else`.

Mais cela est vite long et peu lisible, et les différents niveaux d'indentation sont parfois piégeux.

Il existe alors une instruction qui contracte `else` et `if` : `elif` (sinon si).

Le code du troisième exemple devient alors:

```python
if moyenne < 8:
    print("raté")
elif moyenne < 10:
    print("repêchage")
elif moyenne < 12:
    print("admis")
elif moyenne < 14:
    print("mention AB")
elif moyenne < 16:
    print("mention B")
else:
    print("mention TB")
```

---

## Exercices

### **Exercice 1**

Écrire un programme qui demande deux nombres et qui affiche le plus grand des deux.

**Rappel:** pour stocker dans une variable `n` un nombre tapé au clavier par l'utilisateur, on utilise l'instruction:

```python
n = int(input('Entrez un nombre'))
```

### **Exercice 2**

On calcule l'IMC (Indice de Masse Corporelle) par la formule  où M est la masse (en kg) d'une personne et T sa taille (en m). Selon la classification de l'OMS, une personne est en état de maigreur si son IMC est inférieur à 18 et en surpoids si son IMC est supérieur à 25.

1. Écrire un programme qui demande la masse et la taille d'une personne, calcule son IMC et annonce si la personne est en état de maigreur.
2. Modifier ensuite le programme pour qu'il annonce si la personne est en état de maigreur, en surpoids ou bien si son IMC est normal.

### **Exercice 3**

Une année est déclarée bissextile (et compte donc 366 jours au lieu de 365) dans l'un des deux cas :

- elle est divisible par 4 mais n'est pas divisible par 100 ;
- elle est divisible par 400.

Écrire un code qui détermine si une année est bissextile ou non.

---

Bonus : Si vous avez tout finit
Le site [https://compute-it.toxicode.fr/](https://compute-it.toxicode.fr/) vous demande d'exécuter mentalement les instructions affichées, à l'aide des touches directionnelles de votre clavier. Attention, ce site est très addictif !