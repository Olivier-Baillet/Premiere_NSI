# TP – Le protocole HTTP sur le Web

## **NSI – Première | Interactions homme–machine**

---

## **Objectifs du TP**

À l’issue de ce TP, tu devras être capable de :

- expliquer le rôle du protocole HTTP,
- décrire le modèle client–serveur,
- identifier les éléments d’une requête HTTP,
- identifier les éléments d’une réponse HTTP,
- observer des échanges HTTP réels à l’aide du navigateur.

---

## **Contexte**

Lorsqu’un utilisateur navigue sur le Web, son navigateur communique en permanence avec des serveurs.

Ces échanges suivent des règles précises : c’est le **protocole HTTP**.

Dans ce TP, tu vas observer concrètement ces échanges afin de comprendre ce qu’il se passe « derrière » une page web.

---

# **Partie 1 – Comprendre le modèle client–serveur**

### **Travail demandé**

1. Complète les phrases suivantes :
- Le **client** est la machine qui _______________________.
- Le **serveur** est la machine qui _______________________.
- Sur le Web, le client est généralement _______________________.
1. Complète le schéma suivant :

```
Utilisateur →__________ →__________
Utilisateur ←__________ ←__________

```

---

## **Conclusion intermédiaire**

HTTP est un protocole qui permet la communication entre un **client** et un **serveur**.

---

# **Partie 2 – Observer une requête HTTP**

### **Manipulation**

1. Ouvre un navigateur web.
2. Va sur un site connu (ex. : https://www.wikipedia.org).
3. Ouvre les outils de développement.
4. Clique sur l’onglet **Réseau / Network**.
5. Recharge la page.

---

### **Travail demandé**

1. Combien de requêtes HTTP sont envoyées lors du chargement de la page ?
2. Observe la première requête :
    - Quelle est la **méthode HTTP** utilisée ?
    - Quelle est la **ressource demandée** ?
3. À quoi correspondent les autres requêtes visibles ?

---

## **Conclusion intermédiaire**

Une seule page web nécessite souvent **plusieurs requêtes HTTP** (HTML, CSS, images, etc.).

---

# **Partie 3 – Anatomie d’une requête HTTP**

Observe une requête dans l’onglet Réseau.

### **Travail demandé**

1. Repère les éléments suivants :
    - la méthode (GET ou POST),
    - l’URL,
    - le nom du serveur (Host).
2. Complète la phrase suivante :

> Une requête HTTP permet au client de _______________________ une ressource au serveur.
> 

---

### **Exemple simplifié**

```
GET /index.html HTTP/1.1
Host: www.example.com

```

---

# **Partie 4 – Observer la réponse HTTP**

### **Manipulation**

1. Clique sur une requête dans l’onglet Réseau.
2. Observe la partie « Response » ou « Headers ».

---

### **Travail demandé**

1. Quel est le **code de statut HTTP** de la réponse ?
2. Que signifie ce code ?
3. Quel type de contenu est renvoyé par le serveur (HTML, image, autre) ?

---

## **Codes à connaître**

Complète le tableau suivant :

| Code | Signification |
| --- | --- |
| 200 |  |
| 404 |  |
| 403 |  |
| 301 / 302 |  |

---

# **Partie 5 – Action utilisateur et requête HTTP**

### **Manipulation**

1. Clique sur un lien à l’intérieur du site.
2. Observe l’onglet Réseau.

---

### **Travail demandé**

1. Une nouvelle requête HTTP est-elle envoyée ?
2. Quelle méthode est utilisée ?
3. Quelle ressource est demandée ?

---

## **Lien avec les séances précédentes**

Complète les phrases :

- Cliquer sur un lien provoque l’envoi d’une _______________________.
- Envoyer un formulaire provoque l’envoi d’une _______________________.
- Le protocole utilisé pour ces échanges est _______________________.

---

# **Partie 6 – Synthèse**

Complète le texte suivant :

> Le protocole HTTP permet au navigateur, qui joue le rôle de __________, d’envoyer des __________ à un serveur afin d’obtenir des __________.
> 
> 
> Le serveur renvoie alors une __________ accompagnée d’un __________ indiquant le résultat de la demande.
> 

---

## **Bilan du TP**

À la fin de ce TP, tu dois retenir que :

- HTTP est un protocole de communication du Web,
- le navigateur agit comme client,
- le serveur fournit des ressources,
- chaque action de navigation peut déclencher une requête HTTP,
- les codes HTTP permettent de comprendre la réponse du serveur.

---

## **Pour aller plus loin (facultatif)**

- Tester un lien volontairement faux pour provoquer une erreur 404.
- Comparer une requête HTTP avec et sans rechargement de page.
- Observer la différence entre une requête GET et une requête POST.