## **Exercice 1**

Prédire si les variables suivantes contiennent le booléen `True` ou le booléen `False`.

Contrôlez ensuite en exécutant le code et en inspectant le contenu des variables.

```python
a = (2 > 1)
b = (3 == 1+2)
c = (1 < 0)
d = (2 != 5/2)
e = (2 != 5//2)
f = ('a' == 'A')
g = not a
h = b and c
i = b or c
j = not c and (d or e)
```

## **Exercice 2 : le «ou exclusif»**

Une autre fonction logique importante est le **ou exclusif**, ou «disjonction exclusive».

C'est le «ou» dans le sens de «Fromage *ou* dessert» dans un menu au restaurant. Soit l'un, soit l'autre, mais pas les deux.

Il se note en général `xor` ou `^` en logique (`^` en Python).

Si x et y sont deux booléens, alors $$**x ^ y = (x & ¬y) | (¬x & y)**$$.

Construire la table de vérité du `xor`.

## **Exercice 3**

Construire la table de vérité de l'expression **(x | y) & z** où x, y et z sont trois booléens.

## **Exercice 4**

À l'aide de tables de vérité, démontrer les lois de Morgan:

- $$¬(x | y) = ¬x & ¬y$$
- $$¬(x & y) = ¬x | ¬y$$

## **Exercice 5**

Dans chaque cas, `x` et `y` sont des variables contenant des entiers et `tab` est une variable contenant une liste d'entiers.

Écrire en langage Python une expression booléenne donnant la valeur (vrai ou fausse) de chacune des phrases suivantes:

1. `x` et `y` sont non nuls.
2. `x` est compris entre 0 (exclus) et 10 (inclus).
3. `x` est égal à 0 ou à 1.
4. les deux valeurs `x` et `y` appartiennent à la liste `tab`.
5. `x` appartient à `tab` mais pas `y`.
