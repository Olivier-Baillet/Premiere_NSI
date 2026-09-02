# TP : Tri par dichotomie

![](https://cgouygou.github.io/1NSI/T07_Algorithmes/images/binary_search_meme.jpg)

# **1. Principe de l'algorithme:**

- on se place **au milieu** de la liste;
- on compare la valeur cherchée à celle du milieu;
- si la valeur cherchée est inférieure, on ne garde que la première moitié (à gauche) de la liste, sinon on ne garde que la deuxième moitié (à droite);
- on recommence avec la bonne moitié de la liste jusqu'à trouver la valeur cherchée.

## 1.1 Exemple

Cherchons la valeur 14 dans la liste suivante:

![](https://cgouygou.github.io/1NSI/T07_Algorithmes/images/exemple_dichotomie_init.png)

## 1.2 Illustration

La flèche rouge indique la valeur centrale, d'indice `indice_centre`, les flèches bleues les valeurs du début et de fin de la liste à traiter, d'indices respectifs `indice_debut` et `indice_fin`.

![](https://cgouygou.github.io/1NSI/T07_Algorithmes/images/exemple_dichotomie.png)

1. toute la liste est à traiter. On se place sur l'élément central. Ici il y a 9 éléments, donc on se place sur le 4ème, qui est 11.
2. on compare 11 à la valeur cherchée (14). Il faut donc garder tout ce qui est supérieur à 11.
3. on se place au milieu de la liste des valeurs qu'il reste à traiter. Ici il y a 4 valeurs, donc il n'y a pas de valeur centrale. On va donc se positionner sur la 2ème valeur, qui est 18.
4. on compare la valeur 18 à la valeur cherchée : 14. Elle est supérieure, donc on garde ce qui est à gauche. Il n'y a plus qu'une valeur.
5. on se place sur la valeur 14 et on compare avec 14. La valeur est trouvée.

# 2. Programmation de l'algorithme

Méthode de recherche par dichotomie (à compléter)

---

```python
def trouve_dicho(tab: list, valeur: int) :
    '''
    Renvoie l'indice de 'valeur' si 'valeur' est trouvée dans la liste 'tab', et None sinon.

    'tab' doit être une liste triée dans l'ordre croissant.
    '''
    indice_debut = ...
    indice_fin = ...
    while indice_deb  ut <= indice_fin :
        indice_centre = (... + ...) // 2     # on prend l'indice central
        valeur_centrale = ...                # on prend la valeur centrale 
        if valeur_centrale == ... :          # si la valeur centrale est la valeur cherchée...
            return ...
        elif valeur_centrale < ... :         # si la valeur centrale est trop petite...
            indice_debut = ...
        else :
            indice_fin = ...
    return ...

lst = [2, 3, 6, 7, 11, 14, 18, 19, 24]

assert trouve_dicho(lst, 14) == 5
assert trouve_dicho(lst, 3) == 1
assert trouve_dicho(lst, 5) == None
assert trouve_dicho(lst, 0) == None
assert trouve_dicho(lst, 42) == None
```

---