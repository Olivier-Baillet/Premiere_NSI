# Complexité : Tri Dichotomie (1)

# **1. Terminaison et complexité de la méthode**

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

La fonction mathématique *logarithme de base 2* permet de trouver le nombre de puissances de que contient un nombre N. On note  .

La complexité de l'algorithme de dichotomie est donc **logarithmique**, en .

![](https://cgouygou.github.io/1NSI/T07_Algorithmes/images/ex_dicho.png)

## **1.2 Exercice : mesure du temps d'exécution**

### Énoncé

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