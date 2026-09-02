# Complexité : Tri par sélection

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