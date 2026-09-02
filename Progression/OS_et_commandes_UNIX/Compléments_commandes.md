# Compléments sur les commandes

Prenons l'exemple de l'arborescence du dossier `/home/jeanmichel/` de l'ordinateur personnel de Jean-Michel B.:

```html
.
+-- Travail
|   +-- reforme
        +-- projet_flou.odt
|   +-- HTML
|   |   +-- images
|   |   |   +-- toto.png
|   |   |   +-- tata.png
|   |   |   +-- tutu.png
|   |   +-- styles
|   |   |   +-- style.css
|   |   +-- scripts
|   |   |   +-- script.js
|   |   +-- index.html
|   |   +-- page1.html
|   |   +-- page2.html
+-- Photos
|   +-- Ibiza
|   |   +-- reveillon.png
```

## **Chemins**

On a vu la commande `cd` qui permet de changer de répertoire (dossier). Par exemple, pour aller dans le répertoire `images` depuis la racine, on peut taper successivement:

```html
~$ cd Travail/
~/Travail$ cd HTML/
~/Travail/HTML$ cd images/
~/Travail/HTML/images$
```

On peut plus rapidement préciser le chemin relatif:

```html
~$ cd Travail/HTML/images/
~/Travail/HTML/images$
```

Pour revenir à la racine `/home/jeanmichel/`, on peut taper successivement 3 fois la commande `cd ..`, ou bien plus rapidement:

```html
~/Travail/HTML/images$ cd ../../../
~$
```

Et pour aller du répertoire `images` au répertoire `scripts`, on utilisera le chemin relatif:

```html
~/Travail/HTML/images$ cd ../scripts/
~/Travail/HTML/scripts$
```

Ou bien le chemin absolu (mais c'est plus long...):

```html
~/Travail/HTML/images$ cd /home/jeanmichel/Travail/HTML/scripts/
~/Travail/HTML/scripts$
```

## **Options et arguments**

<aside>

### Options

On peut ajouter aux commandes UNIX une ou plusieurs options, qui s'écrivent soit:

- avec une lettre précédée d'un tiret;
- avec un mot-clé précédé de 2 tirets.

<aside>
<img src="notion://custom_emoji/deb345f7-4d2a-442f-a4e9-275aa40b3aeb/34f9d189-4135-8065-8b69-007addbb9605" alt="notion://custom_emoji/deb345f7-4d2a-442f-a4e9-275aa40b3aeb/34f9d189-4135-8065-8b69-007addbb9605" width="40px" />

#### **Exemple avec `ls`**

Tester par exemple dans un de vos répertoires les commandes suivantes:

```html
$ ls
$ ls -l
$ ls -l -h
```

</aside>

<aside>
<img src="notion://custom_emoji/deb345f7-4d2a-442f-a4e9-275aa40b3aeb/34f9d189-4135-8065-8b69-007addbb9605" alt="notion://custom_emoji/deb345f7-4d2a-442f-a4e9-275aa40b3aeb/34f9d189-4135-8065-8b69-007addbb9605" width="40px" />

#### **Exemple avec `rm`**

**Attention, l'usage de `rm` est dangereux, soyez attentif !**

La commande `rm` permet de supprimer **définitivement** un fichier, il n'y a pas de corbeille dans le shell! Mais pas un répertoire non vide.

Pour effacer tous les fichiers d'un répertoire:

```html
$ rm *
```

Et pour supprimer tout le contenu d'un répertoire, y compris les sous-répertoires, on utilise l'option `-r`:

```html
$ rm -r *
```

</aside>

</aside>

### **Arguments**

On peut parfois préciser plusieurs arguments à une commande pour ne pas répéter plusieurs fois son utilisation. Par exemple pour créer deux répertoires `images/` et `data/` en même temps dans le répertoire courant:

```html
$ mkdir images/ data/
```

Et trois fichiers toto.txt, tata.txt et tutu.txt :

```html
$ touch toto.txt tata.txt tutu.txt
```

## **À propos de `grep`**

Comme vu dans l'activité «Terminus», la commance `grep` permet de rechercher une chaîne de caractéres dans un fichier. La syntaxe générale est:

```html
$ grep options "recherche" chemin
```

Voici quelques options utiles:

- `-ignore-case` ou `i` : pour ignorer la casse (minuscules/majuscules indifférentes);
- `c` : pour afficher seulement le nombre d'occurences de la recherche;
- `l` : pour afficher le nom des fichiers contenant la recherche (`chemin` est alors un répertoire);
- `r` : pour rechercher dans tous les fichiers et sous-répertoires de `chemin`, qui est un répertoire.

Pour rechercher dans plusieurs fichiers (comme dans l'activité Terminus) on peut utiliser `*` qui remplace n'importe quel mot. Par exemple, pour rechercher `'password'` dans tous les fichiers `txt` de l'activité, on aurait pu taper:

```html
$ grep 'password' *.txt
```