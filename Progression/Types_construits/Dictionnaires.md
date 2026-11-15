# Dictionnaires

Jusqu'à présent, nous avons rencontré deux types de **conteneurs** (ou ensemble d'éléments) : les listes et les tuples. Ces deux types ont en commun le repérage de leurs éléments par un *indice*, qui est un nombre entier. Ces deux types sont **ordonnés**, on les appelle des **séquences**. L'indice est la **clé** qui permet d'accéder à un élément de l'ensemble.

Prenons comme exemple un autre ensemble d'éléments: les numéros de téléphone sauvegardés dans l'application « Contacts » de votre smartphone. Ces numéros ne sont pas ordonnés, et ne sont pas repérables par un *indice*, mais (en général) par un nom.

Grosso modo, le contenu de votre application « Contacts » est un ensemble d'associations `nom: numéro`. En Informatique, on parle de tableau associatif ou de *p-uplet nommé*: un ensemble de (p) valeurs appelées par un descripteur autre qu'un indice.

En Python, on représentera ces *p-uplets nommés* par des **dictionnaires**.

# 1 Définition d'un dictionnaire, clés et valeurs

### **Le type `dict`**

```python
>>> contacts = {"pap": '0155551010', "bénédicte": '0516526600', "christophe": '0545974500'}
```

- Un dictionnaire (type `dict`) est une donnée composite qui n'est pas ordonnée (à la différence des listes !). Il fonctionne par un système de `clé: valeur`.
- Les clés, comme les valeurs, peuvent être de types différents.
- Un dictionnaire est délimité par des accolades, les associations `clé: valeur` séparées par des espaces.
- On accède à une valeur par sa clé :

```python
>>> contacts["pap"]
'0155551010'
```

### **Méthodes `keys` et `values`**

On peut lister les clés d'un dictionnaires:

```python
>>> contacts.keys()
dict_keys(['pap', 'bénédicte', 'christophe'])
```

et ses valeurs:

```python
>>> contacts.values()
dict_values(['0155551010', '0516526600', '0545974500'])
```

### **Ajout/modification/suppression d'éléments**

Pour modifier une valeur associée à une clé, on réaffecte la nouvelle valeur :

```python
>>> contacts["pap"] = '0605040302'
>>> contacts
{'pap': '0605040302', 'bénédicte': '0516526600', 'christophe': '0545974500'}
```

Si la clé n'existe pas, cela ajoute une paire `clé: valeur` au dictionnaire:

```python
>>> contacts["xavier"] = '0545387000'
>>> contacts
{'pap': '0605040302', 'bénédicte': '0516526600', 'christophe': '0545974500', 'xavier': '0545387000'}
```

La suppression d'une clé (et donc de sa valeur) se fait par le mot-clé `del`:

```python
>>> del contacts["pap"]
>>> contacts
{'bénédicte': '0516526600', 'christophe': '0545974500', 'xavier': '0545387000'}
```

# 2 Méthodes sur les dictionnaires

## **Parcours d'un dictionnaire**

On utilise comme pour les listes une boucle `for` avec l'opérateur `in`. Cet opérateur `in` peut également tester l'appartenance d'une clé à un dictionnaire, hors d'un `for`.

### **Méthode basique**

On parcourt par défaut sur les clés:

```python
>>> for nom in contacts:
...    print(nom)
bénédicte
christophe
xavier
>>> for nom in contacts:
...    print("le numéro de", nom," est",contacts[nom])
...
le numéro de bénédicte est 0516526600
le numéro de christophe est 0545974500
le numéro de xavier est 0545387000
```

Il serait équivalent de faire `for nom in contacts.keys()`.

On peut également parcourir le dictionnaire sur les valeurs, mais sans possibilité alors de récupérer la clé à partir de la valeur (puisque plusieurs clés peuvent avoir la même valeur).

On utilisera pour cela:

```python
>>> for v in contacts.values():
...    print(v)
...
0516526600
0545974500
0545387000
```

### **Méthode avancée avec `items`**

Il peut être utile de parcourir à la fois sur les clés et sur les valeurs, c'est à dire sur l'élément complet `clé: valeur` du dictionnaire, notamment si on souhaite récupérer la clé associée à une valeur donnée.

```python
>>> for k, v in contacts.items():
...     print(v," est associé à",k)
...
0516526600 est associé à bénédicte
0545974500 est associé à christophe
0545387000 est associé à xavier
```

---

## **Création d'un dictionnaire vide et construction de dictionnaire**

Comme les listes, il est très fréquent qu'on ait besoin de construire le dictionnaire par ajouts successifs en partant d'un dictionnaire vide.

On peut créer un dictionnaire vide de deux façons: `{}` ou `dict()`:

```python
>>> dico = {}
>>> dico = dict()
>>> chiffres = ['zéro', 'un', 'deux', 'trois', 'quatre', 'cinq', 'six', 'sept', 'huit', 'neuf']
>>> for c in chiffres:
...     dico[c] = len(c)
...
>>> dico
{'zéro': 4, 'un': 2, 'deux': 4, 'trois': 5, 'quatre': 6, 'cinq': 4, 'six': 3, 'sept': 4, 'huit': 4, 'neuf': 4}
```

On peut bien évidemment créer un dictionnaire en compréhension (**hors-programme**). On peut résumer le code précédent en:

```python
dico = {c: len(c) for c in chiffres}
```

## **Gaspard's corner**

Pour récupérer les clés d'un dictionnaire en fonction de leur valeur, il n'y a pas d'autre moyen que de parcourir le dictionnaire et de sélectionner les clés dont la valeur est celle cherchée.

### **Version par ajouts successifs**

Dans le dictionnaire `dico` de l'exemple précédent, si on cherche les clés dont la valeur est égale à 4 par exemple:

```python
liste = []
for cle in dico:
    if dico[cle] == 4:
        liste.append(cle)
```

---

ce qui donne:

```python
>>> liste
['zéro', 'deux', 'cinq', 'sept', 'huit', 'neuf']
```

Mieux, on écrit une fonction qui prend en paramètre un dictionnaire et une valeur (entière par exemple) à chercher, ainsi que quelques tests:

```python
def get_keys(d:dict, v:int) -> list:
    liste = []
    for cle in d:
        if d[cle] == v:
            liste.append(cle)
    return liste

assert get_keys(dico, 4) == ['zéro', 'deux', 'cinq', 'sept', 'huit', 'neuf']
assert get_keys(dico, 2) == ['un']
assert get_keys(dico, 1) == []
assert get_keys({}, 2) == []
```

### **Version «en compréhension»**

Puisqu'on a créé une liste par ajout successifs dans une liste vide en parcourant un *iterable* (le dictionnaire `dico`), on peut également la créer en compréhension...

```python
liste = [cle for cle in dico if dico[cle] == 4]
```

---

Et la fonction deviet tout simplement:

```python
def get_keys(d:dict, v:int) -> list:
    return [cle for cle in d if d[cle] == v]
```

---

---

# 3 Bilan

**En résumé**

- `dico = dict()` crée un dictionnaire vide appelé `dico`,
- `dico[cle] = contenu` met la valeur `contenu` pour la clé `cle` dans le dictionnaire `dico`,
- `dico[cle]` renvoie la valeur associée à la clé `cle` dans le dictionnaire `dico`,
- `cle in dico` renvoie un booléen indiquant si la clé `cle` est présente dans le dictionnaire `dico`.
- `len(dico)` renvoie le nombre de clés d'un dictionnaire.
- `for cle in dico:` permet d'itérer sur les clés d'un dictionnaire.
- `for valeur in dico.values():` permet d'itérer sur les valeurs d'un dictionnaire.
- `for cle, valeur in dico.items():` permet d'itérer sur les clés **et** les valeurs d'un dictionnaire.