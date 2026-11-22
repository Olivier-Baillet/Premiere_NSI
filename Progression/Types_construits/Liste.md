<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>
<style>
.rappel {
    background-color: #eef6ff;
    border-left: 5px solid #3182ce;
    padding: 15px 20px;
    margin: 20px 0;
    border-radius: 5px;
}

.attention {
    background-color: #fff4df;
    border-left: 5px solid #e6a23c;
    padding: 15px 20px;
    margin: 20px 0;
    border-radius: 5px;
}

.methode {
    background-color: #eaf7ee;
    border-left: 5px solid #38a169;
    padding: 15px 20px;
    margin: 20px 0;
    border-radius: 5px;
}
</style>

# 1 Notion de tableau, indices

En informatique (comme ailleurs...), un tableau permet de stocker de façon structurée plusieurs valeurs, en général de même type**1**.

Voici comment on se représente traditionnellement un tableau de 6 entiers, avec des cases (ou cellules):

![](https://cgouygou.github.io/1NSI/T02_TypesConstruits/images/tableau.png)

Bien entendu, il faut stocker ce tableau dans un variable et lui donner un nom. Appelons-le `tab`. Ce tableau est **ordonné**, le premier élément est 4, le deuxième est 2, et le dernier est 12.

## **Notion d'indice (importantissime)**

- Les indices commencent **toujours** à `0`. Le premier élément d'une liste `tab` (non vide) est donc toujours `tab[0]`.
- On utilise la notation `tab[i]` pour désigner l'élement d'indice `i` du tableau `tab`. Dans l'exemple ci-dessus, `tab[3]` désigne la valeur 42.

![](https://cgouygou.github.io/1NSI/T02_TypesConstruits/images/tableau_indice.png)

- On repère chaque élément du tableau par sa position, le numéro de la case, qu'on appelle **indice**.

<div class="rappel" markdown="1">

### **Indice vs. élément**

**Il ne faut surtout pas confondre** `i` (l'indice d'un élément) et `tab[i]` (l'élément de la liste `tab` d'indice `i`).

</div>

Enfin la **taille** ou **longueur** d'un tableau est le nombre d'éléments qu'il contient. Ici le tableau `tab` a une taille égale à 6.

# 2 Tableau et liste de Python

## **Le type `list`**

En Python, on implémente le type abstrait de tableau par le type `list`. On définit un tableau avec des **crochets** et on sépare ses éléments par des **virgules**. Par abus de langage on parle de liste plutôt que de tableau.

Une liste vide se déclarera par `[]`.

```python
>>> tab = [4, 2, 1, 42, 78, 12]
>>> type(tab)
<class'list'>
>>> tab[3]
42
>>> len(tab)
6
>>> tab[6]
Traceback (most recent call last):
File "<pyshell>", line 1, in <module>
IndexError: list index out of range
>>> tab[-1]
12
>>> liste_vide = []
>>> len(liste_vide)
0
```

<div class="rappel" markdown="1">

**Remarques**:

- on obtient la taille d'une liste avec la fonction `len`;
- un indice supérieur à `len(tab) - 1` provoque une erreur `IndexError: list index out of range` (en dehors de la liste);
- on peut utiliser les indices négatifs: en particulier l'indice -1 permet d'accèder facilement au **dernier** élement.
</div>

# 3 Modification de liste

En Python, les objets de type `list` sont modifiables (on emploie le mot *mutable*). Et c'est souvent une bonne chose, car des listes peuvent évoluer après leur création.

## **Modification d'un élément existant**

On modifie un élément du tableau par simple affectation, en écrasant sa valeur avec la nouvelle.

```python
>>> famille = ["Bart", "Lisa", "Maggie"]
>>> famille[0] = "Bartholomew" # oui, c'est son vrai nom
>>> famille
['Bartholomew', 'Lisa', 'Maggie']
```

## **Ajout d'un élément en fin de liste**

La méthode `append` permet d'ajouter un élément en fin de liste (et donc d'augmenter la taille de la liste).

```python
>>> famille = ["Bart", "Lisa", "Maggie"]
>>> famille.append("Homer")
>>> famille
['Bart', 'Lisa', 'Maggie', 'Homer']
>>> famille.append("Marge")
>>> famille
['Bart', 'Lisa', 'Maggie', 'Homer', 'Marge']
```

<div class="rappel" markdown="1">

### **Un par un**

La méthode `append` ne prend **qu'un seul** paramètre: on ne peut donc ajouter qu'un élément à la fois. Si on a plusieurs éléments à ajouter à une liste, il faudra donc autant d'instruction `append` que d'éléments à ajouter.

</div>

## **Concaténation**

Comme avec les chaînes de caractères, on peut concaténer deux listes avec l'opérateur `+` :

```python
>>> ['truc', 'bidule'] + ['chose', 'machin']
['truc', 'bidule', 'chose', 'machin']
```

---

On pourrait donc se dire qu'on peut ajouter un élément en se passant de la méthode `append`, comme dans l'exemple suivant, à la **différence majeure** qu'en concaténant, une nouvelle liste est créée et les listes initiales sont inchangées.

```python
>>> liste = [1, 1, 2, 3, 5]
>>> liste + [8]
[1, 1, 2, 3, 5, 8]
>>> liste
[1, 1, 2, 3, 5]
>>> liste.append(8)
>>> liste
[1, 1, 2, 3, 5, 8]
>>> liste += [13, 21, 34, 55]
```

---

En pratique, on ne connaît souvent que le prochain élément à ajouter à une liste et on utilisera donc majoritairement la méthode `append`.

## **Suppression d'un élément**

La métode `remove` permet de supprimer la **première** occurrence de l'élément (et seulement la première). À condition bien entendu que l'élément soit dans la liste...

```python
>>> matieres = ["nsi", "maths", "anglais", "français", "maths"]
>>> matieres.remove("maths")
>>> matieres
["nsi", "anglais", "français", "maths"]
>>> matieres.remove("espagnol")
Traceback (most recent call last):
File "<pyshell>", line 1, in <module>
ValueError: list.remove(x): x not in list
```

# 4 Création de listes

Jusqu'à présent on a créé des listes en *extension*, c'est-à-dire qu'on a écrit tous les éléments un par un entre crochets. Voici deux autres façons de faire, souvent pratiques et parfois plus rapides lorsque la taille de la liste est grande.

## **Avec une boucle `for`**

On crée une liste vide, puis on lui ajoute élément par élément.

Création d'une liste contenant les entiers multiples de 3 ou de 5 inférieurs à 100:

```python
multiples = []
for k in range(101):
    if k % 3 == 0 or k % 5 == 0:
        multiples.append(k)
```

---

## **Élements identiques**

Il est souvent pratique d'initialiser une liste de taille donnée, souvent en la remplissant de la même valeur, souvent 0. Par exemple, pour produire une liste contenant 26 zéros:

```python
>>> lst = 26 * [0]
>>> lst
[0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0]
```

# 5 Parcours de listes

Il existe principalement deux méthodes pour parcourir une liste: par ses éléments ou par les indices. Mais dans les deux cas on utilise une boucle `for`.

## **Parcours par élément**

On l'a déjà rencontré sur la boucle `for`:

```python
famille = ["Bart", "Lisa", "Maggie", "Homer", "Marge"]
for membre in famille:
    print(membre)
```

---

affichera:

```python
Bart
Lisa
Maggie
Homer
Marge
```

## **Parcours par indice**

Chaque élément étant accessible par son indice (de `0` à `len(liste) - 1` ), il suffit de faire parcourir à une variable `i` l'ensemble des entiers de `0` à `len(liste) - 1`, par l'instruction `range(len(liste))` :

Le code suivant affichera donc la même chose que le précédent:

```python
famille = ["Bart", "Lisa", "Maggie",  "Homer", "Marge"]
for i in range(len(famille)):
    print(famille[i])
```

---
