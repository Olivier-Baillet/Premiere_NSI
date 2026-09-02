# Utilisateurs et droits

Un système UNIX est un système multi-utilisateur. Toute personne physique ou tout programme interagissant avec le système est un **utilisateur** (user). Cet utilisateur est authentifié sur le système par un nom unique et un identifiant unique (UID). Chaque utilisateur possède certains droits lui permettant d'effectuer certaines opérations et pas d'autres (avoir accès aux répertoires et fichiers, aux périphériques, installer des logiciels...).

Pour connaître les utilisateurs de votre système, on consulte le fichier `/etc/passwd` (faites-le) où on trouve tous les utilisateurs au format:

```html
nom:motdepasse:UID:GID:informations:repertoire:shell
```

Chaque utilisateur appartient à un ou plusieurs groupes, qui servent à ressembler plusieurs utilisateurs pour leur attribuer des droits (permissions d'accès) communs aux fichiers ou applications.

Pour connaître les utilisateurs de votre système, on consulte le fichier `/etc/group` (faites-le).

![](https://cgouygou.github.io/1NSI/T05_Architectures/images/meme_root.jpeg)

Parmi les utilisateurs, il y a un **super-utilisateur** appelé `root` qui a tous les pouvoirs sur le système. Son UID est 0. Pour exécuter une commande réservée au super-utilisateur, un utilisateur doit utiliser la commande `sudo` (super user do) qui nécessite de connaître le **mot de passe root** qui en général n'est connu que de l'administrateur du système.

En particulier le super-utilisateur peut modifier les droits (en attribuer ou en retirer) des utilisateurs et des groupes.

<aside>

### **Les types de droits `r-w-x`**

- les droits en **lecture** (symbolisés par la lettre `r`) : il est possible de lire le contenu de ce fichier
- les droits en **écriture** (symbolisés par la lettre `w`) : il est possible de modifier le contenu de ce fichier
- les droits en **exécution** (symbolisés par la lettre `x`) : il est possible d'exécuter le contenu de ce fichier (quand le fichier est du code exécutable)
</aside>

<aside>

### **Les types d'utilisateurs `u-g-o`**

Tout fichier UNIX:

- possède un propriétaire (par défaut l'utilisateur qui l'a créé) : **u** comme *user*;
- est associé à un groupe dont on définit les actions sur ce fichier: **g** comme *group*;
- peut être éventuellement manipulé par tous les autres utilisateurs : **o** comme *others*.
</aside>

# **Lecture des droits**

Voici ce que me donne la commande `ls` avec l'option `-l` pour obtenir des informations sur le contenu du répertoire `/Travail/1NSI/Archi/`:

![](https://cgouygou.github.io/1NSI/T05_Architectures/images/capture_terminal.png)

- Le premier caractère  ou `d` indique s'il s'agit d'un fichier ou d'un répertoire;
- les 9 caractères suivants représentent dans l'ordre les droits pour les 3 types d'utilisateurs (par paquets de 3 caractères), dans l'ordre **ugo**. Par exemple pour le premier fichier, le propriétaire **u** a les droits `rw-`, c'est-à-dire lecture, écriture, pas d'éxécution (il ne s'agit pas d'un fichier exécutable), les utilisateurs du groupe ont les mêmes droits `rw-` et les autres utilisateurs **o** ont les droits `r--`, c'est-à-dire seulement lecture. Pour les dossiers, tous les utilisateurs ont le droit d'éxécution `x`, qui consiste à explorer le répertoire.
- ensuite on lit le nombre de liens (notion non étudiée cette année);
- on trouve ensuite le nom du propriétaire du fichier, le nom du groupe, la taille du fichier en octets, la date et l'heure de la dernière modification et enfin le nom du fichier ou répertoire.

![](https://cgouygou.github.io/1NSI/T05_Architectures/images/permissions.png)

# **Modification des droits**

Il est important de ne pas perdre de vu que l'utilisateur "root" a la possibilité de modifier les droits de tous les utilisateurs.

Le propriétaire d'un fichier peut également modifier les permissions d'un fichier ou d'un répertoire à l'aide de la commande `chmod`.

Elle s'utilise ainsi, en précisant l'utilisateur (**a** pour tous), l'ajout **+** ou la suppression **-** ou la réinitialisation **=** de la permission et enfin le type de permission :

```html
chmod [u g o a] [+ - =] [r w x] nom_du_fichier
```

Par exemple :

```html
chmod g+w toto.txt
```

Attribuera la permission "écriture" au groupe associé au fichier `toto.txt`.