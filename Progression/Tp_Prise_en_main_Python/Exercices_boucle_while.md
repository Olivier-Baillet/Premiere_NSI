# Exercices sur la boucle while

## **Exercice 1**

Pour chaque code, écrire ce qui va s'afficher en console.

**Code A**

```python
c = 0
while c <= 3:
    print("ok")
    c += 1
```

---

**Code B**

```python
k = 0
while k > 3:
    print("ok")
    k += 1
print("fini")
```

---

**Code C**

```python
n = 0
while n < 4:
    print("ok")
    n += 2
```

---

## **Exercice 2**

Que va afficher le code ci-dessous ?

```python
c = 0
mot = 'a'
while mot != 'aaaa':
    mot += 'a'
    c += 1
print(c)
```

---

## **Exercice 3**

Un capital de 10 000 € est placé au taux annuel de 4 %.

Écrire le code permettant d'afficher au bout de combien d'années le capital va dépasser 14 000 €.

On rappelle qu'une augmentation de 4 % correspond à une multiplication par 1,04.





## **Exercice 4**

Luke, Obi-Wan, Han et Chewbacca sont sur le point de quitter Tatooine et partent pour Aldorande. Mais ils sont pris en chasse par des croiseurs interstellaires de l'empire. Le faucon millénium pourra distancer ses poursuivants dès qu'ils sera passé en vitesse lumière.

Obi-Wan et Luke pressent Han de calculer les coordonnées pour passer en vitesse lumière, mais Han leur explique :

Il faut un petit moment, le temps de définir les navi-composantes. Il suffit d'une petite erreur de calcul et la trajectoire passe à travers une étoile ou bien on frôle une supernova et là, la balade est terminée.

Calculer les navi-composantes n'est pas si simple. Étant donné un point d'arrivée souhaité, donné par 3 valeurs x, y et z, le calcul des navi-composantes est fait par l'algorithme suivant (* est la multiplication et % est le reste de la division entière (modulo)):

```python
initialiser x, y, et z
tant que 10 * x > y :
    x = (y * z) % 10000
    y = (3 * z) % 10000
    z = (7 * z) % 10000



afficher les navi-composantes : x, y, z
```

Le point d'arrivée (valeurs initiales de x, y et z) est donné en entrée du problème. Fournissez les navi-composantes obtenues par l'algorithme qui précède (trois nombres entiers séparés par des virgules) pour valider le défi et passer en vitesse lumière.
