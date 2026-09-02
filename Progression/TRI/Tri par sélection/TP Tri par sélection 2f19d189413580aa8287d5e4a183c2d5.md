# TP : Tri par sélection

## 1. Animation

Considérons la liste `[5, 4, 2, 1]`

Voici le fonctionnement de l'algorithme :

![](https://cgouygou.github.io/1NSI/T07_Algorithmes/images/Selection_sort_numbers.gif)

## 2. Principe

Comme dans tous les autres algorithmes de tri que nous allons étudier, nous allons travailler **en place**. Cela signifie que nous ne travaillons que sur la liste initiale, sans en créer de nouvelles. Le tri sera fait en permutant des éléments.

Très très grossièrement, l'idée de l'algorithme est la suivante :

- on cherche le minimum de toute la liste, et on le place au tout début de la liste.
- on cherche maintenant le minimum de toute la liste SAUF le 1er terme, et on le place en 2ème position.
- on continue ainsi jusqu'à la fin.

Pour réaliser ceci, le travail va se faire en manipulant les indices des éléments de la liste.

### **Description de l'algorithme**

Le travail se fait essentiellement sur les **indices**.

- du premier élément jusqu'à l'avant-dernier :
    - on considère que cet élément est l'élément minimum, on stocke donc son indice dans une variable *indice du minimum*.
    - on parcourt les éléments suivants, et si on repère un élémént plus petit que notre mininum on met à jour notre *indice du minimum*.
    - une fois le parcours fini, on échange l'élément de travail avec l'élément minimum qui a été trouvé.

## 3. Implémentation de l'algorithme

**Tri par sélection**  

```python
def tri_selection(lst) :
	for i in range(len(lst)-1):
        indice_min = i
        for k in range(i+1, len(lst)) :
            if lst[k] < lst[indice_min]:
                indice_min = k
        lst[i], lst[indice_min] = lst[indice_min], lst[i]
    
```

---

*Vérification :*

```python
>>> ma_liste = [7, 5, 2, 8, 1, 4]
>>> tri_selection(ma_liste)
>>> ma_liste
[1, 2, 4, 5, 7, 8]
```