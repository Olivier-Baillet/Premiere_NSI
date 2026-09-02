# Mini Projet - MiniWiki

## **Introduction du projet**

Chaque élève de la classe a déjà réalisé une page web présentant une personnalité importante de l’informatique.

À partir de ces productions individuelles, tu vas maintenant créer **ton propre site web complet** qui servira de **portail** vers les différentes biographies.

Ton objectif principal est de **créer un site harmonisé**, cohérent visuellement, en ne modifiant **que le CSS** (sauf pour l’accueil), même si les pages HTML originales ont été créées par des personnes différentes.

Le projet se compose de plusieurs parties, chacune avec **un but clair** et **des étapes détaillées** pour t’aider.

# **1. Construire la structure du site**

### **But de cette partie :**

Organiser proprement ton site dans un dossier unique, lier correctement les fichiers entre eux, et préparer l’environnement de travail avant de commencer le CSS.

### **Étapes à suivre :**

1. Crée un dossier nommé par exemple `projet-pionniers`.
2. Place dans ce dossier :
    - toutes les pages HTML réalisées par la classe (une page par personne),
    - ton fichier `index.html` (page d’accueil),
    - un fichier `style.css`,
    - un fichier `script.js` (pour la fin du projet),
    - un éventuel dossier `images/`.
3. Vérifie que chaque page HTML inclut le lien suivant dans son `<head>` :
    
    ```html
    <link rel="stylesheet" href="style.css">
    ```
    
4. Ne modifie **aucun autre contenu HTML** dans les pages biographiques : tu travailleras uniquement avec le CSS.

# **2. Créer ta page d’accueil (index.html)**

### **But de cette partie :**

Proposer une **entrée claire et structurée** vers ton site, avec un tableau récapitulatif des différentes personnalités.

### **Étapes à suivre :**

### A. Ajouter un titre et une introduction

1. Insère en haut de la page un titre principal `<h1>` (ex. : “Pionniers de l’informatique”).
2. Rédige un court texte d’introduction (2 à 4 lignes) expliquant le but du site.

### B. Créer un tableau récapitulatif

Le tableau permettra d’avoir une vue d’ensemble des personnalités étudiées.

1. Crée une balise `<table>`.
2. Ajoute une section  `<thead>` avec :
    - une ligne `<tr>`
    - des en-têtes `<th>` : Nom — Dates — Domaine — Lien vers la page
3. Ajoute une section `<tbody>` contenant une ligne  `<tr>` par personnalité.
4. Pour chaque ligne, place un lien vers la page de l’élève correspondant, par exemple :
    
    ```html
    <a href="alan_turing.html">Voir la page</a>
    ```
    

### C. Vérifier le fonctionnement

1. Ouvre `index.html` dans ton navigateur.
2. Teste chaque lien : il doit ouvrir la bonne page.
3. Vérifie la lisibilité du tableau avant stylisation.

# **3. Ajouter un menu de navigation**

### **But de cette partie :**

Permettre à n’importe quel visiteur de naviguer facilement entre les pages, grâce à un menu simple et répété sur toutes les pages.

### **Étapes à suivre :**

### A. Construire le menu dans index.html

1. Ajoute une balise `<nav>`.
2. Crée une liste :
    
    ```html
    <ul>
      <li><a href="index.html">Accueil</a></li>
      <li><a href="ton_personnage.html">Ma biographie</a></li>
    </ul>
    ```
    

### B. Copier le même menu dans chaque page biographique

1. Ajoute exactement la même structure `<nav>` en haut de chaque page HTML existante.
2. Vérifie que les liens fonctionnent partout.

### C. Préparer la mise en forme en CSS

1. Les puces devront disparaître.
2. Le menu devra devenir horizontal.
3. Les liens devront être espacés, colorés, décorés.

Cette mise en forme se fera dans la partie CSS.

# **4. Harmoniser toutes les pages avec le CSS**

### **But de cette partie :**

Rendre l’ensemble du site cohérent et agréable à lire sans modifier le HTML des biographies.

Tu devras donc **analyser les pages existantes** (titres, paragraphes, images) et les **styliser uniquement avec CSS**.

### **Étapes à suivre :**

Attention : les étapes qui suivent ne sont pas à respecter à la lettre, mais constituent plutôt des guides à prendre en compte pour parvenir au résultat attendu.

### A. Élaborer une identité visuelle commune

1. Choisis une police pour tout le site (`font-family`).
2. Choisis une palette de couleurs harmonieuse (fonds, titres, liens).
3. Définis des tailles de texte cohérentes.
4. Utilise une largeur maximale pour centrer tes pages (ex. `max-width: 900px; margin: auto;`).

### B. Styliser les titres, paragraphes et images

1. Harmonise la taille et la couleur des titres (`h1`, `h2`, etc.).
2. Améliore la lisibilité des paragraphes :
    - `line-height` (hauteur de ligne),
    - `margin-bottom`.
3. Gère les images :
    - largeur maximum,
    - centrage,
    - encadrement ou ombre si nécessaire.
    

### C. Mettre en forme le tableau de la page d’accueil

1. Ajoute des bordures fines (`border`).
2. Mets en couleur l’en-tête (`thead`).
3. Ajoute des lignes alternées (`nth-child(even)`).
4. Ajoute un effet au survol (`:hover`).

### D. Styliser le menu de navigation

1. Supprime les puces (`list-style: none`).
2. Aligne les éléments horizontalement (`display: flex`).
3. Ajoute un espace entre les liens.
4. Applique une couleur de fond au menu.
5. Ajoute un effet au survol (`:hover`).

# **6. Résultat final attendu**

À la fin du projet, ton site devra comporter :

- une page d’accueil structurée et lisible,
- un tableau récapitulatif propre,
- un menu simple et fonctionnel,
- un CSS cohérent et harmonisé pour **toutes** les pages,
- un code clair, soigné, et bien organisé.