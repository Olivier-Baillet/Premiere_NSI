# Vers le tri par Sélection

<aside>
💡

**Principe de l'algorithme**

Pour toutes les valeurs, en commençant par la deuxième :

- Tant qu'on trouve à gauche une valeur supérieure et qu'on n'est pas revenu à la première valeur, on échange ces deux valeurs.
</aside>

**Pour tester votre code :**

```python
>>> ma_liste = [7, 5, 2, 8, 1, 4]
>>> tri_selection(ma_liste)
>>> ma_liste
[1, 2, 4, 5, 7, 8]

```

```python
def tri_selection(lst) :
    ...
```

```python
def tri_selection(lst) :
    for ... in ... :
        ... = ...
        for ... in ... :
            if ... :
                ...
        ...
```

```python
def tri_selection(lst) :
    for i in range(...):
        ... = i
        for k in range(..., ...) :
            if ... < ... :
                ... = ...
        ..., ... = ..., ...
```

```python
def tri_selection(lst) :
    for i in range(len(lst)-1):
        indice_min = ...
        for k in range(..., len(lst)) :
            if lst[...] < lst[...]:
                indice_min = ...
        lst[...], lst[...] = lst[...], lst[...]
```