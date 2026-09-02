# Complexité des algorithmes de tri

# 1. Tri Dichotomie

## 1.1 Terminaison

Contrairement à la première méthode, l'algorithme de recherche par dichotomie contient une boucle `while` : il faut s'assurer que cette boucle s'arrête.

### **Variant de boucle**

Dans la boucle `while`, la valeur `indice_fin - indice_debut` est un **variant de boucle**: c'est un nombre entier positif qui va décroître strictement à chaque passage dans la boucle, ce qui assure la terminaison.

En effet, dans la boucle:

- soit la valeur est trouvée, et le `return` assure la sortie de la boucle;
- soit indice_debut augmente d'au moins 1, et donc `indice_fin - indice_debut` diminue strictement;
- soit indice_fin diminue d'au moins 1, et donc `indice_fin - indice_debut` diminue strictement.

### Complexité

Dans le pire des cas (la valeur cherchée n'est pas dans la liste), combien d'itérations de la boucle sont nécessaires pour une liste de taille N ?

Sachant qu'à chaque itération de la boucle on divise le tableau en 2, cela revient donc à se demander combien de fois faut-il diviser le tableau en 2 pour obtenir, à la fin, un tableau comportant un seul entier ? Autrement dit, combien de fois faut-il diviser N par 2 pour obtenir 1 ?

| **taille de la liste** | **1** | **2** | **4** | **8** | **16** | **64** | **256** | **4096** |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| nombre d'étapes |  |  |  |  |  |  |  |  |

### **Logarithme**

La fonction mathématique *logarithme de base 2* permet de trouver le nombre de puissances que contient un nombre $n$.
On le note  $log_{2}(N)$.

La complexité de l'algorithme de dichotomie est donc **logarithmique**, en $O(log_{2}(n))$.

![](https://cgouygou.github.io/1NSI/T07_Algorithmes/images/ex_dicho.png)

## **1.2 Exercice : mesure du temps d'exécution**

1. Utiliser la fonction suivante pour mesurer les temps d'exécution des deux fonctions `trouve` et `trouve_dicho` sur 100 appels en cherchant la plus grande valeur de la liste `tab_alea` fournie.
    
    ```python
    import random
    import time
    
    def temps_moyen(f, tab: list, valeur: int, n:int) -> float:
        '''
        Renvoie le temps moyen d'exécution sur 'n' itérations de la fonction de recherche 'f',
        appelée sur une recherche de 'valeur' dans la liste 'tab'.
        '''
        t_moy = 0
        for k in range(n):
            t0 = time.time()
            f(tab, valeur)
            t1 = time.time()
            t_moy += t1 - t0
        return t_moy / n
    
    tab_alea=sorted([random.randint(1, 1000000) for _ in range(100000)])
    ```
    
    ---
    
2. Recommencer en augmentant la taille de `tab_alea` (x 10) et comparer les temps d'exécution.

# 2. Tri par sélection

On va s'intéresser au temps d'éxécution de ce tri, et plus particulièrement au lien entre la taille de la liste donnée en entrée et ce temps d'éxécution.

On définit donc :

- une fonction `alea` qui renvoie une liste de taille `n` créée aléatoirement;
- une fonction `chrono` qui prend en paramètre un entier `n` et qui renvoie le temps d'éxécution de la fonction `tri_selection` pour la liste construite à partir de la fonction `alea`.
1. Compléter les fonctions dont les extraits sont fournis ci-dessous.
2. Construire une liste (en compréhension si possible) des temps obtenus pour les valeurs de `n` suivantes : 10, 100, 1000, 10000.
3. Quel semble être le lien entre `n` et le temps d'éxécution?

```python
import time
import random as rd

def alea(n):
    lst_alea = list(range(n))
    rd.shuffle(lst_alea)
    return lst_alea

def chrono(n):
    t0 = time.time()
    tri_selection(...)
    t1 = time.time()
    return 

tailles = [10, 100, 1000, 10000]
temps = [...]
```

---

1. On va visualiser tout ça...

```python
import matplotlib.pyplot as plt

plt.plot(tailles, temps)
plt.show()
```

---

# 3. Tri par sélection

Il s'agit d'étudier la complexité de cet algorithme de façon expérimentale.

Pour cela:

1. Reprendre les fonctions `chrono` et `pire_cas` de l'exercice 2 sur le tri par sélection et afficher le graphique des temps d'exécution.
2. Faire de même avec une liste déjà triée. Que remarquez-vous?

# Bonus : comparaison des algorithmes de tri

Une jolie animation permettant de comparer les tris :

*(on peut y constater que le tri par sélection met toujours autant de temps pour trier la liste, quelque soit son état initial)*

![image](https://glassus.github.io/premiere_nsi/T4_Algorithmique/4.3_Tri_par_insertion/data/comparaisons.gif)

Issue de ce [site](https://www.toptal.com/developers/sorting-algorithms).