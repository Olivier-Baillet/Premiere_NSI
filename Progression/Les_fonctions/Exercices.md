# Exercices

## **Exercice 1**

Écrire une fonction `maximum` qui prend deux nombres en paramètres et qui renvoie le plus grand des deux.

## **Exercice 2**

Transformez les programmes des exercices 4 et 5 de la section 6.1.3 (if) en fonctions.

- **Exercice 4** : la fonction prend un entier (l'année) en paramètre et renvoie `True` ou `False` selon que l'année est bissextile ou non.
- **Exercice 5** : la fonction prend une chaine de caractères en paramètre et renvoie le nombre de voyelles.

## **Exercice 3**

Écrire une fonction `leet_speak` qui prend en paramètre une chaine de caractères (en minuscules) et qui renvoie sa traduction en «Leet Speak».

C'est-à-dire la même chaîne de caractères en ayant remplacé:

- les `a` par des `4`;
- les `e` par des `3`;
- les `s` par des `5`;
- les `i` par des `1`;
- les `o` par des `0`.

Par exemple, votre fonction doit produire le résultat suivant:

```python
>>> leat_speak('leet speak')
 l33t 5p34k
```

## **Exercice 4**

Écrire une fonction `diviseurs` qui prend un nombre entier en paramètre et qui **affiche** ses diviseurs (penser bien évidemment à utiliser le reste de la division euclidienne).

## **Exercice 5**

Écrire une fonction `est_premier` qui prend un nombre entier en paramètre et qui renvoie un booléen déterminant si le nombre est premier ou non.

## **Exercice 4**

Écrire une fonction `nb_voyelles` qui prend en paramètre la chaine de caractères `mot` renvoie le nombre de voyelles de `mot`.

*Exemple d'utilisation*

```python
>>> nb_voyelles("bonjour")
3
```

## **Exercice 5**

Définissez une **fonction** `decale` qui décale de 3 rangs dans l'alphabet la lettre majuscule `lettre` passée en paramètre (après Z, on recommencera à A..)

*Aide*

```python
>>> ord('A')
65
>>> chr(65)
'A'
```

*Exemple d'utilisation*

```python
>>> decale('F')
'I'
```

## **Exercice 6**

Rajoutez un paramètre `n` à la fonction précédente pour pouvoir décaler la lettre de `n` rangs.

*Exemple d'utilisation*

```python
>>> decale('B', 5)
'G'
```

## **Exercice 7**

Utilisez la fonction précédente pour créer la fonction `decale_phrase` qui prend en paramètres une phrase `p` et un nombre `n` et qui décale toutes les lettres de `p` de `n` rangs. On laissera les espaces intacts.

*Exemple d'utilisation*

```python
>>> decale_phrase("PAS MAL DU TOUT", 4)
'TEW QEP HY XSYX'
```

## **Exercice 8**

Décodez la phrase `RT BTHHPVT CT RDCIXTCI GXTC S XCITGTHHPCI`.

## **Exercice 9**

La [conjecture de Syracuse](https://fr.wikipedia.org/wiki/Conjecture_de_Syracuse) (ou de Collatz) postule ceci :

*Prenons un nombre  : si  est pair, on le divise par 2, sinon on le multiplie par 3 puis on ajoute 1. On recommence cette opération tant que possible. Au bout d'un certain temps, on finira toujours par tomber sur le nombre 1.*

**Q1.** Écrire une fonction `suivant` qui prend en paramètre un nombre `n` renvoie le successeur de`n`, suivant les règles énoncées ci-dessus.

**Q2.** Écrire une fonction `syracuse` qui affiche tous les termes de la suite de Syracuse depuis un nombre `n` passé en paramètre jusqu'à (on l'espère !) 1.

## **Exercice 10**

**Q1.** Écrire une fonction `temps_de_vol` qui prend un nombre `n` en paramètre et qui renvoie le nombre d'étapes pour arriver à 1, en partant de `n`.

**Q2.** Écrire une fonction `temps_max(nmax)` qui affiche le plus grand temps de vol pour un nombre entre 1 et `nmax`.

**Q3.** Modifier cette fonction pour afficher aussi le nombre de départ donnant ce plus grand temps de vol.