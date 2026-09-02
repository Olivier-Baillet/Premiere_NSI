# TP – Formulaires HTML et requêtes GET / POST

## **Objectifs du TP**

À l’issue de ce TP, tu devras être capable de :

- comprendre le rôle d’un formulaire HTML,
- construire un formulaire simple et fonctionnel,
- comprendre comment les données sont envoyées au serveur,
- distinguer les méthodes **GET** et **POST**,
- observer une requête HTTP issue d’un formulaire.

---

## **Contexte**

Un formulaire est un des principaux moyens d’interaction entre un utilisateur et un site web.

Lorsqu’un utilisateur remplit un formulaire et clique sur *Envoyer*, des **données sont transmises au serveur** via une requête HTTP.

Dans ce TP, tu vas :

1. analyser un formulaire existant,
2. construire ton propre formulaire,
3. expérimenter les méthodes GET et POST,
4. observer concrètement ce qu’il se passe lors de l’envoi.

---

# **Partie 1 – Découverte et analyse d’un formulaire**

On te fournit le code HTML suivant :

```html
<form action="https://httpbin.org/get" method="get">
  <label for="nom">Nom :</label>
  <input type="text" id="nom" name="nom">

  <label for="prenom">Prénom :</label>
  <input type="text" id="prenom" name="prenom">

  <button type="submit">Envoyer</button>
</form>

```

### **Travail demandé**

1. Repère la balise qui définit le formulaire.
2. Quels sont les champs de saisie présents ?
3. Quelle est la valeur de l’attribut `action` ?
4. Quelle est la méthode utilisée pour envoyer les données ?
5. À quoi servent les attributs `name` dans les champs `input` ?

---

# **Partie 2 – Construction d’un formulaire simple**

Tu vas maintenant créer ton propre formulaire.

### **Consigne**

Crée un fichier `formulaire.html` contenant :

- un titre de page,
- un formulaire permettant de saisir :
    - un nom,
    - un prénom,
    - une adresse e-mail,
- un bouton *Envoyer*.

Le formulaire devra envoyer les données vers :

```
https://httpbin.org/get
```

### **Aide (structure minimale)**

```html
<form action="https://httpbin.org/get" method="get">
  <!-- champs -->
</form>
```

### **À vérifier avant de continuer**

- Chaque champ possède un `name`.
- Le bouton envoie bien le formulaire.
- La page s’affiche correctement dans le navigateur.

---

# **Partie 3 – Expérimentation avec la méthode GET**

### **Manipulation**

1. Ouvre ton fichier HTML dans le navigateur.
2. Remplis le formulaire avec des valeurs.
3. Clique sur *Envoyer*.

### **Observations**

1. Que se passe-t-il dans la barre d’adresse du navigateur ?
2. Où apparaissent les données saisies ?
3. Que se passe-t-il si tu modifies directement l’URL ?

### **Conclusion intermédiaire**

Complète la phrase suivante :

> Avec la méthode GET, les données du formulaire sont transmises au serveur via __________.
> 

---

# **Partie 4 – Modifier le formulaire pour utiliser POST**

Tu vas maintenant utiliser la méthode **POST**.

### **Consigne**

1. Modifie uniquement l’attribut `method` de ton formulaire.
2. Remplace `get` par `post`.
3. Change l’URL de destination par :

```
https://httpbin.org/post
```

### **Manipulation**

1. Recharge la page.
2. Remplis à nouveau le formulaire.
3. Clique sur *Envoyer*.

### **Observations**

1. Les données apparaissent-elles dans l’URL ?
2. Où sont visibles les données dans la page de réponse ?
3. Quelle différence constates-tu avec la méthode GET ?

---

# **Partie 5 – Observation d’une requête HTTP**

### **Manipulation**

1. Ouvre les outils de développement du navigateur.
2. Onglet **Réseau / Network**.
3. Recharge la page.
4. Envoie le formulaire.

### **Travail demandé**

1. Repère la requête correspondant à l’envoi du formulaire.
2. Note :
    - la méthode utilisée (GET ou POST),
    - le code de réponse HTTP,
    - l’URL de la requête.

---

# **Partie 6 – Comparaison GET / POST**

Complète le tableau suivant :

| Critère | GET | POST |
| --- | --- | --- |
| Données visibles dans l’URL |  |  |
| Utilisé pour |  |  |
| Sécurité |  |  |

---

# **Partie 7 – Bilan et synthèse**

Réponds aux questions suivantes :

1. À quoi sert un formulaire HTML ?
2. Quel est le rôle de l’attribut `action` ?
3. Quelle est la différence principale entre GET et POST ?
4. Dans quel cas POST est-il préférable ?

---

### **Pour aller plus loin (facultatif)**

- Ajouter un champ de type `password`.
- Ajouter un champ `radio` ou `select`.
- Tester ce qu’il se passe si un champ n’a pas d’attribut `name`.

## **Conclusion**

Un formulaire HTML permet à un utilisateur d’envoyer des données à un serveur.

Selon la méthode utilisée (GET ou POST), les données sont transmises de manière différente.

Le protocole HTTP permet d’organiser ces échanges entre le navigateur et le serveur.

---