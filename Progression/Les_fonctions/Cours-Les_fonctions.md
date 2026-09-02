# Cours : Les fonctions

La notion de fonction est essentielle en programmation. Ces fonctions sont des blocs d'instructions auquels on donne un nom, et qui ont une tâche bien précise. L'utilisation de fonctions permet de construire des programmes plus simples à écrire, à lire, à vérifier et à modifier, en découpant le programme en sous-programmes. Autre avantage, on peut utiliser ces fonctions à plusieurs endroits du programme et éviter une certaine lourdeur.

Nous avons déjà rencontré des **fonctions** depuis le début de l'année:
par exemple `print`, `bin`, `len`.

En Python, on peut définir une fonction avec le mot-clé `def`.

## Schéma général d'une fonction

![](https://cgouygou.github.io/1NSI/T06_Python/images/schema_fonction.png)

En règle générale, une fonction s'applique à un ou plusieurs paramètres, et renvoie (au moins) une valeur.

<aside>
💡

### **Définir une fonction - syntaxe générale**

Pour définir une fonction, on utilise le mot-clé `def` suivi du nom de la fonction, avec le(s) paramètre(s) entre parenthèses. Le bloc d'instructions constituant **le corps** de la fonction doit être indenté.

On renvoie une valeur avec le mot-clé `return`.

</aside>

```python
def ma_fonction(parametre):
    *instructions*
    return valeur_renvoyee
```

---

Reprenons par exemple un programme écrit en exercice sur la boucle `for` qui calcule la somme des entiers naturels jusqu'à 1000:

```python
s = 0
for k in range(1, 1001):
    s = s + k
print(s)
```

---

Transformons-le en une fonction. L'objectif est de pouvoir utiliser cette fonction quand on en aura besoin, et éventuellement pour calculer la somme des entiers jusqu'à n'importe quelle valeur, pas nécessairement 1000. Cette valeur va être le paramètre de la fonction. Et on ne veut plus afficher la somme, mais que cette somme soit renvoyée par la fonction (pour l'affecter à une variable, ou bien pour affichage).

```python
def somme(n):
    s = 0
    for k in range(1, n+1):
        s = s + k
    return s
```

---

Exécutez ce code dans Geany. Que se passe-t-il?

Lorsque l'interpréteur Python parcourt cette fonction, rien ne s'affiche : la fonction est maintenant prête à être appelée, mais n'est pas exécutée tant que l'utilisateur ne le demande pas explicitement.

Ce sera le cas pour toutes les fonctions : elles doivent être **appelées** pour s'exécuter.

Dans la console, faites un appel à la fonction:

```python
>>> somme(42)
903
```

<aside>
💡

### **Vocabulaire**

Dans cet exemple:

- on a **appelé** la fonction `somme` en lui **passant** l'**argument** `42`;
- la variable `n` est le **paramètre** de la fonction `somme`;
- l'appel à cette fonction a **renvoyé** la valeur `903`.
</aside>