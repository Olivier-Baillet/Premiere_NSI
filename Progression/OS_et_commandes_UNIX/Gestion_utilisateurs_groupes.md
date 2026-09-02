# Gestion des utilisateurs et des groupes

Les systèmes de type UNIX sont des systèmes **multi-utilisateurs** : plusieurs personnes peuvent utiliser le même ordinateur avec leurs propres fichiers et dossiers.

Chaque utilisateur possède des **droits** définissant ce qu’il peut faire. Un utilisateur spécial appelé **`administrateur`** ou **`root`** peut modifier tous les droits.

Pour simplifier la gestion, les utilisateurs peuvent être regroupés dans des **groupes**. Les droits peuvent alors être attribués à tout un groupe.

## Types de droits

Les fichiers et dossiers possèdent 3 types de droits :

- **r** (*read*) : lire le fichier
- **w** (*write*) : modifier le fichier
- **x** (*execute*) : exécuter le fichier

Il existe 3 catégories d’utilisateurs :

- **u** (*user*) : le propriétaire du fichier
- **g** (*group*) : les utilisateurs du groupe associé
- **o** (*others*) : tous les autres utilisateurs

La commande :

```bash
ls -l
```

permet d’afficher les droits associés aux fichiers et dossiers.

### Exemple I

Prenons la ligne suivante obtenue avec la commande `ls -l` :

```bash
-rw-r--r-- 1 user user 0 Apr 26 09:51 fich.txt
```

Lecture de gauche à droite :

- : il s’agit d’un **fichier** (`d` indique un répertoire)
- `rw-` : droits du propriétaire
    - `r` : lecture autorisée
    - `w` : écriture autorisée
    - : exécution interdite
- `r--` : droits du groupe
    - lecture autorisée uniquement
- `r--` : droits des autres utilisateurs
    - lecture autorisée uniquement
- `1` : nombre de liens
- `user` : nom du propriétaire
- `user` : nom du groupe
- `0` : taille du fichier en octets
- `Apr 26 09:51` : date de dernière modification
- `fich.txt` : nom du fichier

---

### Exemple II

Prenons maintenant cette ligne :

```bash
drwxr-xr-x 2 user user 0 Apr 26 09:53 test_2
```

Lecture de gauche à droite :

- `d` : il s’agit d’un **répertoire**
- `rwx` : droits du propriétaire
    - lecture autorisée
    - écriture autorisée
    - accès au répertoire autorisé
- `r-x` : droits du groupe
    - lecture et accès autorisés
    - écriture interdite
- `r-x` : mêmes droits pour les autres utilisateurs
- `2` : nombre de liens
- `user` : propriétaire
- `user` : groupe associé
- `0` : taille du répertoire
- `Apr 26 09:53` : date de dernière modification
- `test_2` : nom du répertoire

## La commande `chmod`

L’utilisateur **root** peut modifier les droits de tous les fichiers et dossiers.

Le propriétaire d’un fichier peut modifier ses permissions avec la commande :

```bash
chmod [utilisateur] [action] [permission] nom_du_fichier
```

### Symboles utilisés

### Utilisateurs

- `u` : propriétaire (*user*)
- `g` : groupe (*group*)
- `o` : autres utilisateurs (*others*)
- `a` : tout le monde (*all*)

### Actions

- `+` : ajouter une permission
- : retirer une permission
- `=` : réinitialiser les permissions

### Permissions

- `r` : lecture
- `w` : écriture
- `x` : exécution

---

### Exemples

Ajouter le droit d’écriture aux autres utilisateurs :

```bash
chmod o+w toto.txt
```

Retirer les droits d’écriture et d’exécution au groupe :

```bash
chmod g-wx toto.txt
```

Le super-utilisateur `root` peut utiliser `chmod` sur tous les fichiers et dossiers du système.