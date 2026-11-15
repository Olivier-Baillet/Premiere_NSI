# Valeurs booléennes

<aside>

## **Histoire de l'informatique**

![](https://cgouygou.github.io/1NSI/images/portraits/George_Boole.jpg)

[George Boole](https://fr.wikipedia.org/wiki/George_Boole) (1815-1864) est un mathématicien et logicien britannique connu pour avoir créé la logique moderne, appelée *algèbre de Boole*.

Cette algèbre binaire n'accepte que deux valeurs, 0 et 1, et a donc d'importantes et nombreuses applications en informatique...

</aside>

# 1 Un peu de logique

En informatique, comme en mathématiques, on s'intéresse à la valeur de vérité de phrases ou d'expressions qui peuvent être soit vraies, soit fausses. Mais rien d'autre, c'est le principe du [tiers-exclu](https://fr.wikipedia.org/wiki/Principe_du_tiers_exclu).

Par exemple, que diriez-vous de ces phrases?

- A: Vous êtes en classe de première.
- B: Baudelaire a écrit «Les fleurs du mal».
- C: La Terre est plate.
- D: .
- E: La lettre `e` est dans le mot `abracadabra`.
- F: Georges Perec a écrit un roman de près de 300 pages sans aucune lettre `e`.
- G:
- H: La couleur orange est la plus belle des couleurs.

# 2 Algèbre de Boole

## **Valeurs et opérations fondamentales**

L'algèbre de Boole consiste à étudier des opérations sur un ensemble uniquement constitué de deux éléments qu'on appelle **booléens**.

Selon le contexte (logique, calcul, électronique), ces deux éléments sont notés:

- Faux (F) / Vrai (V)
- 0 / 1
- `False`/`True` (en Python, comme dans de nombreux langages)

Les opérations fondamentales ne sont plus l'addition et la multiplication mais:

- la **négation**, notée ¬, ou plus simplement «NON» (`not` en Python);
- la **conjonction**, notée &, ou plus simplement «ET» (`and` en Python);
- la **disjonction**, notée |, ou plus simplement «OU» (`or` en Python).

**Négation, ¬, «NON», `not`**

| **x** | **¬x** |
| --- | --- |
| F | V |
| V | F |

**Conjonction, &, «ET», `and`**

| **x** | **y** | **x & y** |
| --- | --- | --- |
| F | F | F |
| F | V | F |
| V | F | F |
| V | V | V |

**Disjonction, |, «OU», `or`**

| **x** | **y** | **x | y** |
| --- | --- | --- |
| F | F | F |
| F | V | V |
| V | F | V |
| V | V | V |

<aside>

### **`True` & `False`**

- Il existe deux valeurs booléennes en Python : `True` et `False`.
- Une variable prenant l'une de ces deux valeurs est de type `bool`.

```python
>>> type(True)
<class'bool'>
>>> x = False
>>> x
False
>>> type(x)
```

</aside>

### **Exemples**

```python
>>> a = 2
>>> a == 3
False

>>> a == 2
True

>>> a != 1
True

>>> a > 2
False

>>> a <= 5
True

>>> a % 2 == 0
True

>>> x = (0 == 1)
>>> x
False

>>> y = (3 + 2 == 5)
>>> y
True
```

```python
>>> 'e' in 'abracadabra'
False

>>> 'b' in 'abracadabra'
True

>>> 'A' not in 'abracadabra'
True
```

### **Opérateurs de comparaison**

| **Opérateur** | **Signification** |
| --- | --- |
| `==` | est égal à |
| `!=` | est différent de |
| `<` | inférieur à |
| `>` | supérieur à |
| `<=` | inférieur ou égal à |
| `>=` | supérieur ou égal à |
| `in` | appartient à |
| `not in` | n'appartient pas à |

```python
>>> True and False
False

>>> True and True
True

>>> False or True
True

>>> not True
False
```