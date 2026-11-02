# Écriture d'un entier dans une base

> Le monde se divise en 10 catégories : ceux qui comprennent le binaire et ceux qui ne le comprennent pas.
> 

# 1 Le système décimal

Depuis la préhistoire, l'Homme a besoin de compter. Sa première idée:

![](https://cgouygou.github.io/1NSI/T01_TypesBase/images/entailles.png)

Pas très pratique... Heureusement, il en eut rapidemennt une autre, beaucoup plus efficace: regrouper les bâtons en paquets.

![](https://cgouygou.github.io/1NSI/T01_TypesBase/images/entailles_paquets.png)

Des paquets de 5 et surtout de 10. Pourquoi 10?

Pour écrire les nombres, regroupés en paquets de 10, il a donc fallu inventer 10 chiffres pour compter les unités (en-dessous du paquet): 0, 1, 2, 3, 4, 5, 6, 7, 8, 9.

Et le nombre 10 ne signifie ni plus ni moins que 1 paquet et 0 unité.

<aside markdown="1">
  
Ensuite, on fait un paquet de paquets, la centaine (100, c'est à dire $10 * 10 = 10^{2}$), puis un paquet de centaines, le millier (1000, c'est-à-dire $10 * 10 * 10 = 10^{3}$), et ainsi de suite.

Au final, si on écrit le nombre 2023, on sait que c'est:

- **2** mille, c'est-à-dire $$2*10^{3}$$;
- **0** centaine, c'est-à-dire $$0*10^{2}$$;
- **2** dizaines, c'est-à-dire $$2*10^{1}$$;
- **3** unités, c'est-à-dire $$3*10^{0}$$.

</aside>

![](https://cgouygou.github.io/1NSI/T01_TypesBase/images/homer2.png)

<aside markdown="1">
Et bien entendu, $$2026 = 2*10^{3} + 0*10^{2} + 2 *10^{1} + 6 *10^{0}$$

</aside>

> La position de chaque chiffre dans l'écriture du nombre correspond à la puissance de 10 par laquelle on le multiplie.
> 


<aside markdown="1">
  
<u>**Un autre exemple, la base octale**</u>

Pour Homer Simpson, qui n'a que 8 doigts, il aurait été certainement plus naturel de faire des paquets de 8... et donc de manipuler seulement 8 chiffres : 0, 1, 2, 3, 4, 5, 6 et 7.

C'est le **système octal**.

Ainsi, «son» 10 signifierait 1 paquet de 8 et 0 unité, soit «notre» 8... Et donc notre 10 (en décimal) s'écrirait 12 (en octal).

Enfin, 2026 (en décimal) s'écrit 3752 en octal puisque :

$$3752 = 3 *8^{3} + 7 *8^{2} + 5 *8^{1} + 2 *8^{0}$$

$$= 3*512 + 7*64 + 5 *8 + 2 *1$$
$$= 1536 + 448 +40 +2$$
$$= 2026$$

</aside>

# 2 Notion de base

**Écriture d'un entier en base**

- Choisir une base, c'est choisir la «taille» du paquet, et donc le nombre de chiffres dont on aura besoin: en base , il y a **$b$** chiffres.
- Dans notre système décimal, la base est $b = 10$ .
- La position de chaque chiffre correspond à la puissance de $b$ par laquelle on le multiplie.
- On précisera la base (si différente de 10) en indice en fin du nombre. Par exemple, le nombre $312_{5}$ est écrit en base 5.

**Homer compte**

| **Octal** | **Décimal** |
| --- | --- |
| 0 | 0 |
| 1 | 1 |
| 2 | 2 |
| 3 | 3 |
| 4 | 4 |
| 5 | 5 |
| 6 | 6 |
| 7 | 7 |
| 10 | 8 |
| 11 | 9 |
| 12 | 10 |
| 13 | 11 |
| 14 | 12 |
| 15 | 13 |
| 16 | 14 |
| 17 | 15 |
| 20 | 16 |
| 21 | 17 |
| ... | ... |


<aside markdown="1">

<u>**Exemples**</u>

$$312_{5} = 3 5^{2} + 1*  5^{1} + 2 * 5 ^{0}$$

$$= 3 * 25 + 1 * 5 + 2 * 1$$

$$= 82$ $

$$25072_{8} = 2 * 8^{4} + 5 * 8 ^{3} + 0 * 8^{2} + 7 * 8^{1} + 2 * 8^{0}$$

$$= 2 * 4096 + 5 512 + 78 + 2*1$$
$$= 10810$$

</aside>

# 3 Le système binaire (base 2)

### **Le binaire**

- Le système binaire est le système de numération de base $b = 2$.
- Il utilise donc seulement deux chiffres, 0 et 1, appelés **bits** (contraction de l'anglais binary digit).
- Il est particulièrement adapté à l'informatique car il permet d'unifier la logique (Vrai/Faux), le calcul et l'électronique (voir vidéo suivante).
- Un regroupement de 8 bits est appelé un **octet**.
- Avec bits, on écrit nombres entiers, de jusqu'à $2^{n} - 1$ .

### **Conversions**

#### **Binaire → Décimal**

Il est utile de connaître alors les puissances de 2 pour convertir rapidement de l'écriture binaire vers l'écriture décimale.

![](https://cgouygou.github.io/1NSI/T01_TypesBase/images/puissances2bis.png)

Par exemple $$ 10110101_{2} = 128 + 32 + 16 + 4+ 1 = 181$$ .

#### **Décimal → Binaire**

- On peut utiliser l'algorithme de soustraction: on soustrait du nombre la plus grande puissance de 2 possible, et on recommence...
- On utilise l'algorithme de divisions: on effectue les divisions successives du nombre par 2. L'écriture en binaire est donnée par les restes lus de bas en haut.

![](https://cgouygou.github.io/1NSI/T01_TypesBase/images/divisions.png)

#### **Décimal → Base quelconque**

Les deux algorithmes de soustraction et de divisions fonctionnent également pour la conversion du décimal vers n'importe quelle autre base.

# 4 Le système hexadécimal (base 16)

### **L'hexadécimal**

- Le système hexadécimal est le système de numération de base $b = 16$.
- Il utilise donc 16 chiffres : 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F.
- Bien qu'il nécessite plus de chiffres, ce système donne des écritures plus courtes et particulièrement pratique du fait que 16 est une puissance de 2 : la conversion entre les systèmes binaire et hexadécimal se fait sans calcul, uniquement par regroupement de 4 bits.

### **Couleurs**

Le système hexadécimal est en particulier un mode de code informatique des couleurs.

En effet une couleur (codage RGB) est composée de 3 valeurs correspondant aux composantes rouge, verte et bleue, et chacune de ces valeurs est un entier compris entre 0 et 255, c'est-à-dire entre 0 et FF en hexadécimal: on peut les écrire avec seulement deux chiffres.

Par exemple, la couleur rouge ci-contre a pour composantes (178, 26, 15), ce qui donne en hexadécimal : (B2, 1A, 0F), qu'on écrit en général de façon *concaténée* B21A0F et souvent précédée d'un #.

![](https://cgouygou.github.io/1NSI/T01_TypesBase/images/rouge_B21A0F.png)


<aside markdown="1">

<u>**Convertisseur**</u>

Un [convertisseur](http://www.proftnj.com/RGB3.htm) bien utile.

</aside>
