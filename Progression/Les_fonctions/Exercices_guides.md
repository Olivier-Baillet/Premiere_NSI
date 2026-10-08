## Exercice 9 — Suite de Syracuse

La conjecture de Syracuse décrit une suite de nombres construite à partir d'un nombre de départ.

À chaque étape :

- si le nombre est **pair**, on le divise par 2 ;
- s'il est **impair**, on le multiplie par 3 puis on ajoute 1.

On recommence avec le résultat obtenu jusqu'à atteindre `1`.

Par exemple, en partant de `6` :

```
6 → 3 → 10 → 5 → 16 → 8 → 4 → 2 → 1
```

### Q1. Fonction `suivant`

Écrire une fonction `suivant(n)` qui :

- prend un entier `n` en paramètre ;
- renvoie le nombre obtenu **après une seule étape** de la suite de Syracuse.

Exemples :

```python
suivant(6)   # renvoie 3
suivant(3)   # renvoie 10
suivant(10)  # renvoie 5
```

### Q2. Fonction `syracuse`

Écrire une fonction `syracuse(n)` qui affiche **tous les nombres de la suite**, en commençant par `n` et en terminant par `1`.

Par exemple :

```python
syracuse(6)
```

doit afficher :

```
6
3
10
5
16
8
4
2
1
```

**Indication :** la fonction `suivant` permet de passer d'un terme au terme suivant. Il faut donc la réutiliser dans une boucle.

---

## Exercice 10 — Temps de vol

On appelle **temps de vol** d'un nombre le **nombre d'étapes nécessaires pour atteindre `1`**.

Par exemple :

```
6 → 3 → 10 → 5 → 16 → 8 → 4 → 2 → 1
```

Pour aller de `6` à `1`, il faut effectuer **8 étapes**.

On a donc :

```python
temps_de_vol(6)  # renvoie 8
```

### Q1. Calculer un temps de vol

Écrire une fonction `temps_de_vol(n)` qui :

- prend un entier `n` en paramètre ;
- utilise la fonction `suivant` pour passer d'un terme au suivant ;
- compte le nombre d'étapes effectuées ;
- renvoie le nombre d'étapes nécessaires pour atteindre `1`.

Exemples :

```python
temps_de_vol(1)  # renvoie 0
temps_de_vol(2)  # renvoie 1
temps_de_vol(4)  # renvoie 2
temps_de_vol(6)  # renvoie 8
```

**Attention :** atteindre `1` signifie que le calcul est terminé. Il ne faut donc pas compter une étape supplémentaire après avoir obtenu `1`.

### Q2. Rechercher le plus grand temps de vol

Écrire une fonction `temps_max(nmax)` qui étudie **tous les nombres de `1` à `nmax`** et affiche le plus grand temps de vol rencontré.

Par exemple, pour :

```python
temps_max(10)
```

la fonction doit calculer les temps de vol de :

```
1, 2, 3, 4, 5, 6, 7, 8, 9 et 10
```

puis afficher le **plus grand temps de vol** trouvé.

**Indication :** utiliser une boucle permettant de parcourir tous les nombres de `1` à `nmax` et utiliser `temps_de_vol` pour chacun d'eux.

### Q3. Retrouver le nombre correspondant

Modifier `temps_max(nmax)` pour qu'elle affiche **à la fois** :

1. le plus grand temps de vol trouvé ;
2. le nombre de départ qui possède ce temps de vol.

Par exemple, si le plus grand temps de vol parmi les nombres étudiés est obtenu pour `n = 9`, on souhaite obtenir un affichage du type :

```python
Temps de vol maximal : 19
Nombre de départ : 9
```

**Indication :** en plus de mémoriser le temps de vol maximal, il faut mémoriser le nombre qui a produit ce maximum.
