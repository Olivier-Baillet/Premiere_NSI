# Exercices – Droits UNIX et commande chmod

## Exercice 1 – Lire des permissions

On considère la ligne suivante :

```bash
-rw-r--r-- 1 user user 120 notes.txt
```

Répondre aux questions :

1. S’agit-il d’un fichier ou d’un répertoire ?
2. Le propriétaire peut-il modifier le fichier ?
3. Le groupe peut-il écrire dans le fichier ?
4. Les autres utilisateurs peuvent-ils lire le fichier ?
5. Quel est le nom du fichier ?

---

## Exercice 2 – Comprendre les droits

On considère :

```bash
drwxr-x--- 2 prof profs 4096 cours
```

1. S’agit-il d’un fichier ou d’un répertoire ?
2. Le propriétaire peut-il accéder au répertoire ?
3. Les membres du groupe peuvent-ils modifier le contenu ?
4. Les autres utilisateurs peuvent-ils accéder au répertoire ?

---

## Exercice 3 – Traduire les permissions

Compléter le tableau :

| Permissions | Signification |
| --- | --- |
| r-- |  |
| rw- |  |
| rwx |  |
| --x |  |

---

## Exercice 4 – Identifier les utilisateurs

Associer :

| Symbole | Signification |
| --- | --- |
| u |  |
| g |  |
| o |  |
| a |  |

---

## Exercice 5 – Comprendre `chmod`

Que font les commandes suivantes ?

```bash
chmod o+w fichier.txt
```

```bash
chmod g-x script.sh
```

```bash
chmod a+r document.txt
```

---

## Exercice 6 – Écrire une commande `chmod`

Écrire la commande permettant :

1. d’ajouter le droit d’écriture au propriétaire sur `notes.txt`
2. de retirer le droit de lecture aux autres utilisateurs sur `secret.txt`
3. d’ajouter le droit d’exécution à tout le monde sur `programme.py`

---

## Exercice 7 – Vrai ou Faux

Indiquer si les affirmations suivantes sont vraies ou fausses.

1. Le symbole `d` indique un répertoire.
2. `r` signifie exécution.
3. `chmod` permet de modifier les droits d’un fichier.
4. `root` possède tous les droits sur le système.
5. `rwx` signifie lecture, écriture et exécution.

---

## Exercice 8 – Situation problème

On considère :

```bash
-rw-r----- 1 alice profs devoir.txt
```

1. Alice peut-elle modifier le fichier ?
2. Les membres du groupe `profs` peuvent-ils lire le fichier ?
3. Un autre utilisateur peut-il lire ce fichier ?
4. Quelle commande permettrait d’autoriser tous les utilisateurs à lire le fichier ?