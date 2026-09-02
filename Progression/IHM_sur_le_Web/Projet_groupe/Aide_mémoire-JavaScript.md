# Aide-mémoire JavaScript

# 1. Les balises HTML importantes pour JavaScript

> JavaScript ne crée pas la page :
  Il **agit sur des balises HTML déjà présentes**.
> 

## 1.1 Balises ciblées par JavaScript

| Balise | Pourquoi elle est importante |
| --- | --- |
| `<button>` | Déclenche une action (clic) |
| `<p>` | Texte à afficher / masquer |
| `<div>` | Conteneur que JavaScript peut modifier |
| `<section>` | Zone de contenu |
| `<nav>` | Menu |
| `<ul>`, `<li>` | Listes (menus, résultats, onglets) |
| `<input>` | Champ de saisie (recherche) |

---

## 1.2 Attributs essentiels

Ces attributs permettent à JavaScript de retrouver un élément précis.

| Attribut | Rôle |
| --- | --- |
| `id` | Identifiant unique (très utilisé en JS) |
| `class` | Groupe d’éléments (CSS + JS) |

Exemple :

```html
<button id="toggle-btn">Afficher</button>
<p class="details">Texte caché</p>

```

# 2. Comment JavaScript retrouve un élément HTML

Dans un script, tu verras souvent des lignes comme :

```jsx
document.getElementById("toggle-btn");
```

ou

```jsx
document.querySelector(".details");
```

Cela signifie :

> JavaScript cherche un élément précis dans le HTML.
> 

## Méthodes les plus utilisées

| Code JavaScript | Élément ciblé |
| --- | --- |
| `getElementById("id")` | élément avec cet `id` |
| `querySelector("p")` | premier `<p>` |
| `querySelector(".classe")` | élément avec cette classe |
| `querySelectorAll(".classe")` | tous les éléments de cette classe |

Souvent, l’élément est stocké dans une variable :

```jsx
let bouton = document.getElementById("toggle-btn");
```

# 3. L’événement principal : le clic

JavaScript attend une **action de l’utilisateur**.

```jsx
addEventListener("click", ...)
```

Exemple :

```jsx
bouton.addEventListener("click", function() {
    // actions
});
```

Cela signifie :

> Quand l’utilisateur clique sur le bouton, le code s’exécute.
> 

# 4. Ce que JavaScript modifie dans la page

JavaScript peut modifier :

- l’affichage,
- les classes CSS,
- parfois le texte.

## 4.1 Modifier l’affichage directement

```jsx
element.style.display = "none";
```

→ cache l’élément

```jsx
element.style.display = "block";
```

→ affiche l’élément

Utilisé pour :

- afficher / masquer un texte,
- montrer / cacher une section.

---

## 4.2 Modifier le style via les classes CSS

```jsx
element.classList.add("active");
element.classList.remove("active");
element.classList.toggle("active");
```

JavaScript :

- ajoute ou retire une classe

CSS :

- définit le style correspondant

Exemple :

```jsx
document.body.classList.toggle("dark");
```

```css
.dark {
    background-color: #222;
    color: white;
}
```

# 5. Propriétés CSS importantes pour l’interaction

Voici les propriétés CSS **souvent modifiées ou utilisées avec JavaScript**.

## 5.1 Visibilité et affichage

| Propriété | Rôle |
| --- | --- |
| `display` | afficher / cacher |
| `visibility` | visible ou invisible |
| `opacity` | transparence |

---

## 5.2 Apparence globale

| Propriété | Rôle |
| --- | --- |
| `background-color` | couleur de fond |
| `color` | couleur du texte |
| `transition` | animation douce |

---

## 5.3 Classes souvent utilisées

| Classe CSS | Usage courant |
| --- | --- |
| `.hidden` | élément caché |
| `.active` | élément sélectionné |
| `.dark` | mode sombre |
| `.visible` | élément affiché |