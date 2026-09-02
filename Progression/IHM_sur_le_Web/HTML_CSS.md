# HTML & CSS

![image.png](HTML%20&%20CSS/c47ca3ad-a8ea-4110-bbea-679964233830.png)

![](https://cgouygou.github.io/1NSI/T04_IHMWeb/images/htmlcssjs_meme.jpg)

On commence par s'intéresser au cas le plus simple, celui où le serveur renvoie une page unique, identique pour tous les utilisateurs. De plus, l'utilisateur ne pourra pas agir sur sa page : il n'y a aucune interactivité.

![](https://cgouygou.github.io/1NSI/T04_IHMWeb/images/page_statique.png)

# 1 Les bases de HTML

Nous allons nous intéresser à un acteur fondamental du développement web, le couple HTML+CSS (Hyper Text Markup Langage et Cascading Style Sheets).

![](https://cgouygou.github.io/1NSI/T04_IHMWeb/images/logo_HTML_CSS.png)

Dans un premier temps, nous allons exclusivement nous intéresser au HTML. Qu'est-ce que le HTML, voici la définition que nous en donne Wikipedia :

> L’Hypertext Markup Language, généralement abrégé HTML, est le format de données conçu pour représenter les pages web. C’est un langage de balisage permettant d’écrire de l’hypertexte, d’où son nom. HTML permet également de structurer sémantiquement et de mettre en forme le contenu des pages, d’inclure des ressources multimédias, dont des images, des formulaires de saisie, et des programmes informatiques. Il permet de créer des documents interopérables avec des équipements très variés de manière conforme aux exigences de l’accessibilité du web. Il est souvent utilisé conjointement avec des langages de programmation (JavaScript) et des formats de présentation (feuilles de style en cascade).
> 

On retiendra que HTML est un langage dit « à balises ». Ce n'est pas à proprement parler un langage de programmation, mais un langage de **description** de contenu. Il a été inventé en 1992 par [Tim Berners-Lee](https://fr.wikipedia.org/wiki/Tim_Berners-Lee). La version actuellement utilisée est le `html5`.

## **Balises**

<aside>
💡

### **Exemple complet minimal**

Ouvrir l'éditeur de texte `gedit` et y coller le code suivant. Enregistrer le document sous le nom `exemple_minimal.html` par exemple, dans un dossier `HTML`. Puis l'ouvrir avec un navigateur (Firefox).

```python
<!DOCTYPE html> 
<html>
    <head>                                      <!--  -->
        <meta charset="utf-8">
        <title>Titre très original</title>
    </head>
    <body>
        <h1>Une belle page web</h1>
        <p>
            Un texte très <strong>intéressant</strong>.
        </p>
        <br>
        <a href="http://lyceevalois.com/lmdv">Un lien</a>
        <!-- Un commentaire... -->
    </body>
</html>
```

</aside>

### **Exercice 1**

Répondre à l'aide de recherches sur le web.

1. Quelle est la signification des balises de ce code minimal?
2. Quelles sont les balises contenant un *attribut*?
3. L'indentation est-elle obligatoire?
4. Quelle est l'erreur dans l'extrait de code suivant?
    
    ```python
    <balise1>
        <balise2>
        </balise1>
    </balise2>
    ```
    
5. Quelle est la balise permettant d'insérer une image dans une page web? Combien d'attributs obligatoires comporte-t-elle?

### **Exercice 2**

Web intro : [https://capytale2.ac-paris.fr/web/c/af40-8351662](https://capytale2.ac-paris.fr/web/c/af40-8351662)

[https://capytale2.ac-paris.fr/web/c/a501-8544517](https://capytale2.ac-paris.fr/web/c/a501-8544517)

### **Exercice 3**

Balises et éléments : [https://capytale2.ac-paris.fr/web/c/5ca9-8351665](https://capytale2.ac-paris.fr/web/c/5ca9-8351665)

On peut donner des attributs pour mettre en forme les différents éléments.

Modifier par exemple dans l'exemple précédent:

```python
<h1 style="color: #FF0000;">Une belle page web</h1>
<p style="text-align: center;">
    Un texte très <strong>intéressant</strong>.
</p>
```

Pour l'instant, cela fera l'affaire, mais c'est une très mauvaise pratique, qu'on abandonnera dès la section suivante...

### **Exercice 4**

Créer une page web, présentant la biographie de la personnalité qui vous a été attribuée:

| **Élève** | **Personnalité** |
| --- | --- |
| Endrit | John Von Neumann |
| Albin | Ada Lovelace |
| Océane | Dorothy Johnson Vaughan |
| Islem | George Boole |
| Théo | Tim Berners-Lee |
| Noé | Linus Torvalds |
| Emma | Aaron Swartz |
| Clément | Margaret Hamilton |
| Elouan  | Whitfield Diffie & Martin Hellman |
| Nathël | Hedy Lamarr |
| Akif | Guido Van Rossum |
| Yséa | Steve Jobs |
| Velid  | Donald Knuth |
| Hassan  | Grace Hopper |
| Quentin  | Larry Page & Sergueï Brin |
| Shelby | **Katherine Johnson** |
| Faustine | **Alice Recoque** |
| Mael | **Stephanie Shirley** |
| Noam | Alan Turing / * |

La page web devra comporter (*a minima*):

- le nom de la personne en titre (centré);
- une image (centrée);
- la biographie sous forme d'une liste non numérotée (unordered list);
- un lien vers vos sources, qui doit s'ouvrir dans un nouvel onglet.

**Exemple de rendu:**

![](https://cgouygou.github.io/1NSI/T04_IHMWeb/images/exemple_turing.png)

# 2 Avec CSS

L'acronyme CSS signifie Cascading Style Sheets. L'idée est de regrouper dans un seul fichier toutes les informations relatives à la mise en forme des éléments de la page html.

De manière très simplifiée, on peut dire que le fichier `html` s'occupe du fond tandis que le fichier `css` s'occupe de la forme.

Le fichier CSS (souvent nommé `style.css`) doit être référencé au début du fichier `html` , au sein de la balise `<head>` en y ajoutant cette ligne:

```python
<link href="style.css" rel="stylesheet" type="text/css" />
```

### **Un exemple**

Voici un extrait du fichier css utilisé pour l'escape game d'introduction:

```python
body                                /* On définit le style par défaut des pages (balise <body>): couleurs du texte et du fond, police de caractère).*/
{
    color : #FFFFFF;
    background-color : #000000;
    font-family : monospace;
}

h1                                  /* On définit le sstyle des titres de niveau 1 (balise <h1>).*/
{
    text-align: center;
    font-style : bold;
    width : 60%;
    font-size : 5em;
    margin-left: auto;
    margin-right: auto;
}

a                                   /* On définit le style des liens (balise <a>).*/
{
    font-style : bold;
    color : #C80903;
}

.cesar                              /* On définit le style de la classe cesar.*/
{
    margin-left: auto;
    margin-right: auto;
    width : 50%;
    font-size: 4em;
}
```

## **Classes**

Dans l'exemple de code `css` précédent, j'ai définit un style pour la `class` que j'ai appelée `cesar`.

En fait, `class` est un attribut que l'on peut attribuer à une balise (`div`, `p`, `span`) pour lui appliquer le style correspondant.

Ce que je fait dans la page `/true/level5.html`:

```python
<p class="cesar">
    Mh vxlv frqqxh srxu dyrlu uhdolvh oh suhplhu yhulwdeoh surjudpph lqirupdwltxh hw xq odqjdjh gh surjudppdwlrq sruwh prq suhqrp.
</p>
```

### **Exercice 5**

Écrire un fichier `css` contenant la mise en forme de votre page web. Celle-ci ne doit plus contenir de mise en forme en attributs de balises.

Style avec CSS : [https://capytale2.ac-paris.fr/web/c/3f95-8351671](https://capytale2.ac-paris.fr/web/c/3f95-8351671)

### **Exercice 6**

Hyperlien : [https://capytale2.ac-paris.fr/web/c/304a-8351676](https://capytale2.ac-paris.fr/web/c/304a-8351676)

[https://www.w3schools.com/html/tryit.asp?filename=tryhtml_default](https://www.w3schools.com/html/tryit.asp?filename=tryhtml_comment)

[Mini Projet - MiniWiki](HTML%20&%20CSS/Mini%20Projet%20-%20MiniWiki%202c49d1894135807e97e5c2be28e9f9b8.md)