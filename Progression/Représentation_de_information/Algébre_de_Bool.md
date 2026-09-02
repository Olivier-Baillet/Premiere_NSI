# Algébre de Bool

## 1. Mise en contexte historique et philosophique

> 🎙️ Introduction orale possible (2 à 3 min)
> 
> 
> « Bien avant l’informatique, les philosophes se sont interrogés sur la validité du raisonnement logique.
> 
> Aristote, au IVᵉ siècle avant J.-C., a formalisé la logique à travers ce qu’on appelle les **syllogismes** : des raisonnements déductifs qui permettent de tirer une conclusion à partir de deux propositions.
> 
> Plus de deux mille ans plus tard, **George Boole** (XIXᵉ siècle) a transformé cette logique en un **système mathématique binaire**, manipulable avec des symboles.
> 
> Cette “algèbre de Boole” est à la base du fonctionnement de tous les ordinateurs : elle permet de traduire la logique en circuits électroniques. »
> 

---

## 2. Exemple concret d’Aristote → Boole

### Logique aristotélicienne (syllogisme)

> Tous les hommes sont mortels.
> 
> 
> Socrate est un homme.
> 
> Donc Socrate est mortel.
> 

Structure logique :

- Prémisse 1 : Si **Homme(x)** → **Mortel(x)**
- Prémisse 2 : **Homme(Socrate)**
- Conclusion : **Mortel(Socrate)**

> Ici, Aristote raisonne sur la valeur de vérité des propositions : chaque affirmation est soit vraie, soit fausse.
> 

---

### Logique booléenne (XIXᵉ siècle)

Boole remplace les propositions par des **variables logiques** :

- ( A ) : “Socrate est un homme”
- ( B ) : “Socrate est mortel”
- Règle : ( A ⇒ B ) (si A alors B)

On peut alors manipuler ces valeurs comme des nombres binaires :

- **Vrai = 1**, **Faux = 0**
- L’implication ( A ⇒ B ) est fausse uniquement si A est vrai et B est faux.

| A | B | A ⇒ B |
| --- | --- | --- |
| 0 | 0 | 1 |
| 0 | 1 | 1 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

---

### Passage à l’informatique

Aujourd’hui, cette logique est **implémentée dans le matériel** (portes logiques ET, OU, NON) et dans le **langage Python** via `and`, `or`, `not`.

Exemple :

```python
homme = True
mortel = True
if homme and mortel:
    print("Socrate est mortel")

```

→ Affiche : *Socrate est mortel*

---

## 3. Message à faire passer aux élèves

- **Aristote** a posé les bases du raisonnement logique (philosophie → vérité/falsité).
- **Boole** a mathématisé ces raisonnements (logique symbolique → algèbre binaire).
- **L’informatique** les a traduits en circuits et en instructions logiques (`and`, `or`, `not`).

> Tu peux dire :
> 
> 
> « Chaque fois qu’un ordinateur prend une décision — “si cette condition est vraie, alors fais cela” — il applique en réalité la logique d’Aristote, mais traduite en binaire grâce à Boole. »
> 

---

## 4. Petit exercice débranché pour ancrer la notion

> Activité : “Aristote dans la salle de classe”
> 
> 
> Distribue trois cartes à chaque groupe :
> 
> - une carte “Tous les X sont Y”
> - une carte “Z est un X”
> - une carte “Z est un Y”
> 
> Exemple :
> 
> - “Tous les chats sont des animaux.”
> - “Mimi est un chat.”
> - “Mimi est un animal.”
> 
> ✅ Les élèves doivent déterminer si la conclusion est logique (vraie) ou non.
> 
> 🔄 Ensuite, tu fais le parallèle avec le codage :
> 
> ```python
> chat = True
> animal = True
> if chat and animal:
>     print("Mimi est un animal")
> 
> ```
> 

## **FICHE ÉLÈVE — Logique booléenne et expressions logiques**

### Objectifs :

- Comprendre la logique sous-jacente aux conditions informatiques
- Traduire une situation du quotidien en **expression booléenne**
- Manipuler les connecteurs `and`, `or`, `not`

---

## **FICHE PROFESSEUR — Correction et commentaires**

### Exercice 1 — Porte du labo

Variables :

`prof` = True si professeur présent

`badge` = True si badge valide

Expression :

```python
porte_ouverte = prof and badge

```

Remarques :

- simple ET logique ; permet d’introduire la notion de “condition nécessaire et suffisante”
- bon lien vers la structure `if` de Python.

---

### Exercice 2 — Feu intelligent

Variables : `pieton`, `voiture`, `nuit`

Expression :

```python
feu_vert = (pieton and not voiture) or nuit

```

Exemples où feu vert = True :

- `pieton=True, voiture=False, nuit=False`
- `nuit=True` (quelle que soit la présence de voiture)

---

### Exercice 3 — Club informatique

Variables : `adherent`, `autorisation`, `majeur`

Expression :

```python
sortie_ok = (adherent and autorisation) or majeur

```

Cas non autorisé : élève non adhérent ou sans autorisation **et** non majeur.

---

### Exercice 4 — Système d’alarme

Variables : `porte`, `fenetre`, `active`, `desactivation`

Expression :

```python
alarme = (porte or fenetre) and active and not desactivation

```

Cas test 1 : `porte=False, fenetre=True, active=True, desactivation=False` → True

Cas test 2 : `porte=False, fenetre=False, active=True, desactivation=True` → False

---

### Bonus Socrate

```python
homme = True
mortel = True
if homme and mortel:
    print("Socrate est mortel")

```

Si `mortel = False` → `True and False` → False → rien ne s’affiche.