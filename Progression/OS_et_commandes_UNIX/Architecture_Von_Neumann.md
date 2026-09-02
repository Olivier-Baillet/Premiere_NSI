# Architecture Von Neumann

![image](https://glassus.github.io/premiere_nsi/T3_Architecture_materielle/3.2_Architecture_Von_Neumann/data/BO.png)

![image](https://glassus.github.io/premiere_nsi/T3_Architecture_materielle/3.2_Architecture_Von_Neumann/data/JVN.jpg)

[*John Von Neumann](https://fr.wikipedia.org/wiki/John_von_Neumann) (1903-1957) est un mathématicien et physicien (et bien d'autres choses) américano-hongrois. Il a le premier théorisé l'architecture des processeurs, tels qu'ils fonctionnent encore aujourd'hui.*

# Architecture von Neumann

![image](https://glassus.github.io/premiere_nsi/T3_Architecture_materielle/3.2_Architecture_Von_Neumann/data/arch.png)

On distingue 4 zones essentielles :

- l'**Unité Arithmétique et Logique** (UAL) dans laquelle sont effectuées les opérations de base (addition, multiplication...) Cette zone comporte notamment les **registres** (peu nombreux, de l'ordre de la dizaine) qui sont les espaces de travail ultra-rapides dans lesquels l'UAL va effectuer ses calculs. Une fois ceux-ci effectués, les valeurs des registres repartent dans la mémoire.
- l'**Unité de contrôle** (UC), qui va séquencer les opérations. Lorsqu'on parle d'un processeur à 3 GHz, cela signifie (approximativement) que Unité de Contrôle va envoyer l'ordre d'une nouvelle opération à l'UAL 3 milliards de fois par seconde.
- la **mémoire**, qui contient **à la fois** les données à traiter **ET** les instructions du programme. Cette idée de stocker **au même endroit données et programme** est l'idée centrale de l'architecture von Neumann.
- les **Entrées/Sorties**, permettant de gérer les informations avec l'extérieur.

Les **bus** de communication (des fils électriques) assurent le transport des données entre les différents composants.

Le **CPU** (Central Processing Unit) regroupe l'UAL et l'UC.

# Activité 1 : simulation d'un programme en assembleur

![image](https://glassus.github.io/premiere_nsi/T3_Architecture_materielle/3.2_Architecture_Von_Neumann/data/meme.png)

## Le programme que nous étudierons

```html
a = 3
b = 5
c = a + b
```

Ce programme est ici écrit en langage Python. Le processeur ne comprend pas ce langage : les instructions doivent lui être passées en langage-machine. C'est le rôle des interpréteurs (pour le Python, par exemple) ou des compilateurs (pour le C, par exemple) que de faire le lien entre le langage pratiqué par les humains (Python, C...) et le langage-machine, qui n'est qu'une succession de chiffres binaires.

Par exemple, notre code ci-dessus s'écrit

```html
01010000 00001111 00011000 00000000
00000000 00000000 01010000 00111111
00011100 00000000 00000000 00000000
01100000 00000011 01000000 00111111
00100000 00000000 00000000 00000000
00000000 00000000 00000000 00000000
00000011 00000000 00000000 00000000
00000101 00000000 00000000 00000000
```

en langage-machine.

Comment a lieu cette transformation ?

## Au plus proche de la machine mais encore humainement compréhensible : le langage assembleur

Il existe un langage dit de "bas-niveau" (au sens qu'il est plus proche du langage machine qu'un langage de haut-niveau comme le Python) qui permet de passer des instructions directement au processeur : c'est le langage assembleur (ou ASM).

En assembleur, notre programme s'écrirait (par exemple) :

```html
.pos 0
    mrmovl a, %eax
    mrmovl b, %ebx
    addl %eax, %ebx
    rmmovl %ebx, c
    halt

.align 4
a:  .long 3
b:  .long 5
c:  .long 0
```

- Le [simulateur Y86](https://dept-info.labri.fr/ENSEIGNEMENT/archi/y86js_v2/index.html) permet de simuler la manière dont le processeur va exécuter ce programme.
- Nous verrons un deuxième simulateur dans une autre activité.

![image](https://glassus.github.io/premiere_nsi/T3_Architecture_materielle/3.2_Architecture_Von_Neumann/data/cap_Y86_2.png)

### **Code en langage-machine :**

Sur la partie droite du simulateur, la zone Mémoire contient, après assemblage, la traduction de notre code en langage-machine :

```html
500f1800
0000503f
1c000000
6003403f
20000000
00000000
03000000
05000000
```

Une fois transformé en binaire, on retrouve le code donné au début du paragraphe précédent.

- **Ressources sur les instructions Y86**
    
    ![image](https://glassus.github.io/premiere_nsi/T3_Architecture_materielle/3.2_Architecture_Von_Neumann/data/instrY86.png)
    
    ![image](https://glassus.github.io/premiere_nsi/T3_Architecture_materielle/3.2_Architecture_Von_Neumann/data/encodage.png)
    

#### **Exercice 1**

Coder en assembleur la séquence d'instruction suivante :

```html
w = 10
x = 3
y = 5
z = w - (x + y)
```

Vous aurez pour cela besoin de l'instruction `subl rA rB` qui effectue l'opération `rB-rA` et la stocke dans `rB`. (`rA` et `rB` sont les noms des registres).

- **Correction**
    
    ```html
    .pos 0
    mrmovl x, %eax
    mrmovl y, %ebx
    mrmovl w, %ecx
    addl %eax, %ebx
    subl %ebx, %ecx
    rmmovl %ecx, z
    halt
    
    .align 4
    w:  .long 10
    x:  .long 3
    y:  .long 5
    z:  .long 0
    ```
    

## Résumé des notions essentielles

- Les registres sont à percevoir comme des zones de travail temporaires, à l'accès très rapide. Les données font l'aller-retour entre la mémoire et le registre : elles sont stockées en mémoire, passent dans le registre pour y être modifiées, et reviennent en mémoire.
- les données ET les instructions sont stockées ensemble dans la mémoire : c'est le principe fondateur de l'architecture Von Neumann. Ici, l'octet `03` situé à l'adresse `0x000d` signifie qu'il va falloir ajouter (on le sait grâce au `60` qui précède) le registre numéroté `0` (donc `%eax`) au registre numéroté `3` (donc `%ebx`). On retrouve un octet de même valeur `03` à l'adresse `0x0018`. Mais dans ce cas, cet octet n'est pas une instruction mais une simple donnée : c'est la valeur 3 qu'on a donnée à la variable `a` dans notre programme.

## Conclusion

Le simulateur Y86 nous a permis d'observer comment un processeur réalise des opérations élémentaires. Nous avons découvert le langage assembleur, qui est un langage beaucoup moins agréable qu'un langage de haut-niveau, mais qui reste néanmoins compréhensible par un être humain. Certains informaticiens codent (encore de nos jours) directement en langage assembleur, pour "coller" au mieux au processeur et optimiser les ressources.