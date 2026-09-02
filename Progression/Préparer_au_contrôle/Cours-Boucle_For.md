# Cours : Boucle For

## **La boucle `for`**

<aside>
💡

**Vocabulaire**
En programmation, on parle de **boucle** pour toute instruction qui permet de répéter des instructions. On utilise plutôt le verbe *itérer* et on parle d'*itérations*.

</aside>

### La syntaxe

Pour mettre en place cette boucle, on a besoin d'identifier:

- Les instructions à répéter
- Pour quelle intervalle de valeurs on doit les répéter :
on a donc besoin d'une variable et d'un itérable que cette variable va parcourir
- Identifier dans les instructions ce qui dépend de cette variable de boucle

**Syntaxe générale:**

```python
 for var in iterable:
    *instructions à répéter*
```

où `var` est un nom de variable (non précédemment déclarée dans le programme), `iterable` est un objet ... itérable.

On dit que `var` parcourt l'ensemble `iterable`.

---

### Exercices

[https://pythontutor.com/render.html#mode=display](https://pythontutor.com/render.html#mode=display)

Afficher à la suite les chiffres de 1 à 9 compris. 

```python
i = 1
while(i < 10):
	print(i)
	i += 1
	
#-----------------------#

for i in range(x, y):
	print(i)
```

---

Donner les valeurs consécutives de i, f, g, jusqu’à la fin du programme.

```python
f = 0
g = 1
for i in range(0, 6):
	print(f)
	f = f + g
	g = f - g
```

| Valeur de i |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- |
| Valeur de f |  |  |  |  |  |  |
| Valeur de g |  |  |  |  |  |  |

---

Savoir passer d’une boucle `for` à une boucle `while` et inversement.

```python
f = 0
g = 1
cpt = 0
while(cpt < 6):
	print(f)
	f = f + g
	g = f - g
	cpt += 1
```

<aside>
💡

**À retenir**

- La boucle `for` s'utilise lorsqu'on connaît à l'avance le nombre de répétitions à effectuer: soit un nombre entier, soit un ensemble de valeurs contenus dans un *iterable*. On parle de boucle **bornée**.
- La variable de boucle prend alors successivement **chacune** des valeurs de l'*iterable*, et les instructions sont répétées pour chaque valeur.
- Les instructions répétées peuvent - mais ce n'est pas obligatoire - faire appel à la variable de boucle, mais il ne faut pas que ces instructions la modifient.
- Ne pas oublier les `:` et l'indentation !
- `range(n)` génère une séquence de `n` nombres entiers: on s'en servira dès qu'on aura besoin de répéter `n` fois des instructions.
</aside>