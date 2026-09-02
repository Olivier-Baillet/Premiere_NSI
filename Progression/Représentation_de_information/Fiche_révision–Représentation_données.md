# Fiche de révision – Représentation des données

> **Objectifs :**
> 
> 
> Les conversions entre bases (2, 10, 16)
> Les booléens et expressions booléennes
> 

## 1.  Les bases de numération

<aside>
💡

### Rappels

- **Base 2 (binaire)** : chiffres possibles → 0 et 1
- **Base 10 (décimale)** : chiffres possibles → 0 à 9
- **Base 16 (hexadécimale)** : chiffres possibles → 0–9 et A–F (A=10, B=11, …, F=15)

### Conversion binaire → décimal

Chaque bit représente une puissance de 2.

Ex :  $( 1101_2 = 1×8 + 1×4 + 0×2 + 1×1 = 13_{10} )$

### Conversion décimal → binaire

On divise successivement par 2 et on lit les restes à l’envers.

Ex :  $( 23_{10} = 10111_2 )$

### Conversion binaire ↔ hexadécimal

On groupe les bits **par 4** à partir de la droite.

Ex :  $( 1110\ 0111_2 = E7_{16} )$

</aside>

---

### Exercice 1 – conversions

1. Convertis en base 10 :
    1.   $( 1010_2 )$
    2.  $( 111111_2 )$
    3.  $( 2F_{16} )$
2. Convertis en binaire :
    1.  $( 45_{10} )$
    2.  $( 255_{10} )$
3. Convertis en hexadécimal :
    1.  $( 11011011_2 )$
    2.  $( 101010101_2 )$
    

---

## 2. Les booléens et les expressions booléennes

<aside>
💡

### Rappels

- Type booléen : valeurs possibles → `True` ou `False`
- En Python :
    
    ```python
    a = True
    b = False
    
    ```
    
- Opérateurs logiques :
    - `not` : négation
    - `and` : et logique
    - `or` : ou logique

| A | B | not A | A and B | A or B |
| --- | --- | --- | --- | --- |
| 0 | 0 | 1 | 0 | 0 |
| 0 | 1 | 1 | 0 | 1 |
| 1 | 0 | 0 | 0 | 1 |
| 1 | 1 | 0 | 1 | 1 |
</aside>

---

### Exercice 2 – expressions booléennes

1. Donne le résultat des expressions suivantes :
    1.  `True and False`
    2.  `not (True or False)`
    3.  `(3 < 5) and (5 == 5)`
    4.  `not (4 >= 2 or 7 != 7)`
2. Simplifie les expressions logiques suivantes :
    1.  `not(not A)`
    2.  `A and True`
    3.  `A or False`
    4.  `(A and B) or (A and not B)`
    
3. Si `A` vaut False et `B` vaut True, que vaut `NOT(A AND B)` ?
    1. 0
    2. False
    3. True
    4. None
    
4. On considère une formule booléenne `form`, des variables booléennes `A` et `B` dont voici la table de vérité. 
    
    
    | A | B | **form** |
    | --- | --- | --- |
    | True  | True  | False |
    | False | True  | False |
    | True | False | True  |
    | False | False | False |
    
    Quelle est cette formule booléenne `form` ?
    
    1. A and B
    2. A or B
    3. A and not(B)
    4. not(A) or B
    
5. Pour quelles valeurs booléennes des variables `A`, `B` et `C` l’expression `(A or B) and (not C)` a-t-elle pour valeur True ?
    
    1/     A = True     B = False    C = True
    
    2/    A = True     B = False    C = False
    
    3/    A = False    B = False    C = True
    
    4/    A = False    B = True     C = True
    
6. Soient `A` et `B` deux booléens. L’expression booléenne `NOT(A AND B) OR A` est équivalente à :
    1. False
    2. True
    3. NOT(B)
    4. NOT(A) OR NOT(B)

### Exercice 3 – Calculs booléens

Effectuer les opérations suivantes :

```python
    1011011
&   1010101     # ET
-----------

    1011011
|   1010101     # OU
-----------

    1011011
^   1010101     # NON
-----------
```

[Correction ](Fiche%20de%20r%C3%A9vision%20%E2%80%93%20Repr%C3%A9sentation%20des%20donn%C3%A9es/Correction%202a09d189413580cda088f945ef394137.md)