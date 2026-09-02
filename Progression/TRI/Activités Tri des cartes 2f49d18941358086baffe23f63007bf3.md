# Activités Tri des cartes

### Durée

1 séance – 1 heure

- Activité 1 : 20 minutes
- Activité 2 : 20 minutes
- Mise en commun / transition : 20 minutes

### Place dans la progression

Introduction au chapitre sur les algorithmes de tri

Séance de **construction de sens** avant toute implémentation en Python.

## Matériel

- Jeux de cartes classiques.
- Un seul **symbole (couleur)** par groupe.
- 7 à 10 cartes par groupe

# ACTIVITÉ 1 — Trier sous contraintes

### Durée

20 minutes

### Objectif spécifique

Faire émerger la notion de **méthode de tri** sous contraintes fortes.

### Organisation

- Groupes de 3 élèves.
- Cartes posées en tas, faces cachées.

### Règles

1. Au maximum **deux cartes visibles** simultanément.
2. Seules les cartes visibles peuvent être déplacées.
3. Les cartes reposées doivent être retournées face cachée.

### Objectif

> Trouvez un algorithme permettant de trier le paquet dans l’ordre croissant en respectant strictement les règles.
> 

### Rôle de l’enseignant

- Observer sans guider.
- Noter les stratégies émergentes :
    - comparaisons deux à deux,
    - zones partiellement triées,
    - allers-retours fréquents.

### Questions de débriefing

- Comment décidez-vous quelle carte déplacer ?
- Avez-vous une partie du paquet que vous considérez comme “déjà triée” ?
- Comparez-vous parfois plusieurs fois les mêmes cartes ?

---

# ACTIVITÉ 2 — Amener le tri par sélection

### Durée

20 minutes

### Objectif spécifique

Faire découvrir la logique du **tri par sélection**.

### Organisation

- Même groupes.
- À gauche : **zone triée** vide.
- À droite : cartes non triées, faces cachées.

### Règles spécifiques

- Toujours deux cartes visibles maximum.
- Une carte placée dans la zone triée **ne peut plus être déplacée**.

### Consigne (clé)

> À chaque étape, trouvez la plus petite carte parmi celles qui ne sont pas encore triées, et placez-la dans la zone triée.
> 

### Déroulé

1. Recherche du minimum sur tout le paquet.
2. Placement définitif du minimum.
3. Reprise sur le reste des cartes.
4. Répétition jusqu’à épuisement.

### Questions de structuration

- Que cherchez-vous en priorité ?
- Combien de cartes faut-il regarder pour en placer une seule ?
- Le fait que le paquet soit presque trié change-t-il votre travail ?

### Institutionnalisation

Nommer explicitement :

- recherche du minimum,
- zone triée / zone non triée,
- répétition systématique.

Conclusion :

> Cette méthode s’appelle le tri par sélection.
>