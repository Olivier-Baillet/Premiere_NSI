# TD Logique

### **Exercice 1 — La porte du laboratoire**

Pour que la porte du laboratoire s’ouvre, il faut :

- que le **professeur** soit présent
- **et** que le **badge** soit valide
1. Quelles sont les deux conditions à réunir ?
2. Traduis cette situation sous forme d’une expression booléenne.
3. Que se passe-t-il si le badge est invalide ? si le professeur est absent ?

---

### **Exercice 2 — Le feu tricolore intelligent**

Le feu piéton passe au **vert** si :

- un **piéton appuie** sur le bouton,
- **et** qu’**aucune voiture** n’est détectée,
- **ou** si c’est la **nuit**.
1. Liste les trois conditions logiques en jeu.
2. Écris l’expression booléenne correspondante.
3. Donne deux situations où le feu sera vert.

---

### **Exercice 3 — Le club informatique**

Pour participer à la sortie du club :

- il faut être **adhérent**
- **et** avoir rendu l’**autorisation parentale**,
- **ou** être **majeur**.
1. Définis les trois variables booléennes.
2. Écris l’expression booléenne permettant de savoir si un élève peut participer.
3. Donne un exemple où un élève ne pourra **pas** participer.

---

### **Exercice 4 — Le système d’alarme**

L’alarme se déclenche si :

- la **porte** est ouverte **ou** la **fenêtre** est ouverte,
- **et** que l’**alarme est activée**,
- **et** qu’**aucune désactivation manuelle** n’a eu lieu.
1. Identifie les variables booléennes nécessaires.
2. Traduis la phrase en expression logique.
3. Quelle serait la valeur de l’expression si :
    - la porte est fermée, la fenêtre ouverte, alarme activée, pas de désactivation ?
    - la fenêtre fermée, porte fermée, alarme activée, désactivation = True ?

---

### **Exercice bonus — “Socrate est mortel”**

> Tous les hommes sont mortels.
> 
> 
> Socrate est un homme.
> 
> Donc Socrate est mortel.
> 
1. Traduis ce raisonnement en Python.
2. Quelle serait la valeur de vérité de `(homme and mortel)` si `mortel = False` ?