# Exercices

## **Exercice 1**

![](https://cgouygou.github.io/1NSI/T05_Architectures/images/systeme_fichiers.png)

1. Donner les chemins absolus:
    - du fichier `grub.cfg`
    - du répertoire `photos_vac`
2. Le répertoire courant est `grub`. Donner le chemin relatif du fichier `abi`.
3. Le répertoire courant est `documents`. Donner les chemins relatifs:
    - du fichier `rapport.odt`
    - du dossier `images`

## **Exercice 2**

Décrire (papier/crayon) l'effet de chacune des commandes suivantes en supposant qu'elle sont exécutées les unes à la suite des autres.

1. `cd ~`
2. `mkdir T5`
3. `mkdir T5/TP_shell`
4. `cd T5/TP_shell`
5. `touch toto.txt`
6. `ls -l`
7. `chmod g-rwx,o-rwx toto.txt`
8. `ls -l`
9. `cd ..`
10. `rm -r TP_shell`

## **Exercice 3**

On suppose que l'on se trouve dans un répertoire vide `TEST/` et qu'on exécute les commandes suivantes. Dessiner l'arborescence finale des fichiers et répertoires en utilisant `TEST/` comme racine de l'arborescence.

1. `mkdir series films mangas musique`
2. `touch films/sw.txt mangas/HxH.txt`
3. `cd series/`
4. `mkdir ../musique/rap/ got/ oitnb/`
5. `cd ..`
6. `cp */*.txt series/got/`
7. `rm -r mangas`

## **Exercice 4**

Consulter la page de manuel d'utilisation de la commande `head`. Trouver comment l'utiliser pour n'afficher que les 5 premières lignes d'un fichier `toto.txt`.

## **Exercice 5**

Commencer par télécharger [ce fichier](https://cgouygou.github.io/1NSI/T05_Architectures/data/pg6318.txt) dans votre répertoire `/home/nsi/Téléchargements/`.

1. Dans votre répertoire personnel, créez un répertoire `Shell/` puis un répertoire `Exo5/` dans ce répertoire `Shell/`.
2. Déplacez le fichier `pg6318.txt` dans le répertoire `Exo5/` que vous venez de créer.
3. Consultez les 25 premières lignes de ce fichier, puis renommez-le *judicieusement*.
4. Créez un fichier nommé `reponses.txt`.
5. Consulter le manuel de la commande `echo`.
6. Écrivez votre nom dans ce fichier à l'aide de la commande `echo`.
7. Cherchez les mots `rouge`, `bleu` et `jaune` dans le fichier texte et ajoutez au fichier `reponses.txt` celui qui n'y apparaît pas.
8. Vérifier en affichant le contenu du fichier `reponses.txt`.
9. Cherchez en quelle ligne apparaît pour la première fois le mot `traître`.
10. Ajouter cette réponse au fichier `reponses.txt`.

## **Exercice 6**

Ouvrir un terminal, puis **sans quitter le répertoire courant**:

1. créer un répertoire `Exo6/` puis les répertoires `Exo6/NSI/` et `Exo6/Divers/`.
2. créer un fichier `hello.py` dans le répertoire `Exo6/NSI/`.
3. écrire `print("hello world")` dans ce fichier.
4. se déplacer dans le répertoire `Exo6/NSI/`.
5. afficher le contenu de ce fichier `hello.py`.
6. accorder tous les droits à «tout le monde» sur le fichier `hello.py`.
7. exécuter ce fichier à l'aide du programme `python3`.

## **Exercice 7**

On imagine qu'un répertoire nommé `Bibliothèque` dans le répertoire `Travail` du répertoire personnel contient plusieurs fichiers textes (format `txt`) dont le fichier `brouillon.txt`. Le répertoire courant est `/home/nsi/Documents/Images`.

1. En une seule commande, se déplacer dans le répertoire `Bibliothèque`.
2. Afficher le contenu de ce répertoire.
3. Chercher toutes les occurences du mot "informatique" dans les fichiers texte de ce répertoire.
4. Supprimer le fichier `brouillon.txt`.