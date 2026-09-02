# Correction

# Correction — Exercice 1 (conversions)

### 1) Convertis en base 10

1.  $(1010_2 = 1\cdot 2^3 +0\cdot2^2 +1\cdot2^1 +0\cdot2^0 = 8+0+2+0 = \mathbf{10_{10}})$.
2.  $(111111_2 = 2^5+2^4+2^3+2^2+2^1+2^0 = 32+16+8+4+2+1 = \mathbf{63_{10}})$.
3.  $(2F_{16} = 2\cdot16 + 15 = 32 + 15 = \mathbf{47_{10}}).$

---

### 2) Convertis en binaire

1.  $(45_{10} = \mathbf{101101_2}). (car (45 = 32 + 8 + 4 + 1))$
2.  $(255_{10} = \mathbf{11111111_2})$. (c’est la valeur maximale sur 8 bits non signés)

---

### 3) Convertis en hexadécimal

1.  $(11011011_2)$ → grouper par 4 depuis la droite : $(1101\ 1011)$ → $(D\ B)$ → $(\mathbf{DB_{16}}).$
2.  $(101010101_2) →$ ajouter des zéros à gauche pour grouper : 
 $(0001\ 0101\ 0101) → (1\ 5\ 5) → (\mathbf{155_{16}}).$

---

# Correction — Exercice 2 (booléens)

### 1) Valeurs des expressions

a) `True and False` → **False**.

b) `not (True or False)` → `not True` → **False**.

c) `(3 < 5) and (5 == 5)` → `True and True` → **True**.

d) `not (4 >= 2 or 7 != 7)` → `not (True or False)` → `not True` → **False**.

---

### 2) Simplifications

a) `not(not A)` → **A** (double négation).

b) `A and True` → **A**.

c) `A or False` → **A**.

d) `(A and B) or (A and not B)` → factoriser par A → `A and (B or not B)` → `A and True` → **A**.

(Remarque : `B or not B` est une tautologie = True.)

---