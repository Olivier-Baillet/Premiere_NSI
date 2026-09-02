# Aide-mémoire HTML & CSS

> Ce document sert de **référence rapide** pendant les TP.
> 

# 1. Balises HTML essentielles

## 1.1 Structure générale d’une page HTML

| Balise | Rôle |
| --- | --- |
| `<html>` | Contient toute la page |
| `<head>` | Informations pour le navigateur (titre, CSS, JS) |
| `<title>` | Titre affiché dans l’onglet |
| `<body>` | Contenu visible de la page |

---

## 1.2 Balises de structure (organisation de la page)

| Balise | Rôle |
| --- | --- |
| `<header>` | En-tête de page (titre, logo, menu) |
| `<nav>` | Zone de navigation (menu) |
| `<main>` | Contenu principal |
| `<section>` | Partie thématique du contenu |
| `<article>` | Contenu autonome (article, biographie) |
| `<footer>` | Pied de page |

---

## 1.3 Titres et texte

| Balise | Rôle |
| --- | --- |
| `<h1>` à `<h6>` | Titres (du plus important au moins important) |
| `<p>` | Paragraphe |
| `<strong>` | Texte important (souvent en gras) |
| `<em>` | Texte mis en valeur (souvent en italique) |
| `<br>` | Saut de ligne |

---

## 1.4 Liens et images

| Balise | Rôle |
| --- | --- |
| `<a href="...">` | Lien vers une autre page |
| `<img src="..." alt="...">` | Image |
| `<figure>` | Conteneur pour image + légende |
| `<figcaption>` | Légende d’une image |

---

## 1.5 Listes

| Balise | Rôle |
| --- | --- |
| `<ul>` | Liste non ordonnée |
| `<ol>` | Liste ordonnée |
| `<li>` | Élément de liste |

---

## 1.6 Tableaux

| Balise | Rôle |
| --- | --- |
| `<table>` | Tableau |
| `<thead>` | En-tête du tableau |
| `<tbody>` | Corps du tableau |
| `<tr>` | Ligne |
| `<th>` | Cellule d’en-tête |
| `<td>` | Cellule de données |

---

## 1.7 Éléments interactifs

| Balise | Rôle |
| --- | --- |
| `<button>` | Bouton cliquable |
| `<input>` | Champ de saisie |
| `<form>` | Formulaire |
| `<label>` | Étiquette d’un champ |

---

## 1.8 Attributs HTML

| Attribut | Rôle |
| --- | --- |
| `id` | Identifiant unique (très utilisé en JavaScript) |
| `class` | Groupe d’éléments (très utilisé en CSS) |
| `href` | Lien d’une balise `<a>` |
| `src` | Source d’une image ou d’un script |
| `alt` | Texte alternatif d’une image |
| `type` | Type d’un input ou d’un bouton |

---

# 2. Propriétés CSS

## 2.1 Texte et polices

| Propriété | Rôle |
| --- | --- |
| `font-family` | Police |
| `font-size` | Taille du texte |
| `font-weight` | Épaisseur (normal, bold) |
| `line-height` | Espacement entre les lignes |
| `text-align` | Alignement du texte |
| `color` | Couleur du texte |

---

## 2.2 Couleurs et arrière-plan

| Propriété | Rôle |
| --- | --- |
| `background-color` | Couleur de fond |
| `background-image` | Image de fond |

---

## 2.3 Modèle de boîte

| Propriété | Rôle |
| --- | --- |
| `margin` | Espace extérieur |
| `padding` | Espace intérieur |
| `border` | Bordure |
| `width` | Largeur |
| `height` | Hauteur |
| `box-sizing` | Gestion des dimensions |

---

## 2.4 Mise en page

| Propriété | Rôle |
| --- | --- |
| `display` | Type d’affichage (`block`, `inline`, `flex`) |
| `max-width` | Largeur maximale |
| `margin: auto` | Centrer un bloc |
| `text-align` | Centrage du contenu texte |

---

## 2.5 Flexbox (bases)

| Propriété | Rôle |
| --- | --- |
| `display: flex` | Active flexbox |
| `justify-content` | Alignement horizontal |
| `align-items` | Alignement vertical |
| `gap` | Espacement entre éléments |

---

## 2.6 Listes et menus

| Propriété | Rôle |
| --- | --- |
| `list-style` | Puces de liste |
| `text-decoration` | Soulignement des liens |

---

## 2.7 Tableaux

| Propriété | Rôle |
| --- | --- |
| `border-collapse` | Fusion des bordures |
| `border` | Bordure des cellules |
| `padding` | Espace dans les cellules |
| `nth-child()` | Lignes alternées |

---

## 2.8 Effets et interactions visuelles

| Propriété | Rôle |
| --- | --- |
| `:hover` | Effet au survol |
| `cursor` | Curseur de souris |
| `transition` | Animation douce |