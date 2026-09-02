# Exercice

**Exercice de bac**

Parties 2 et 3 de l'exercice 2 du sujet [Nouvelle-Calédonie J1 2022](https://glassus.github.io/terminale_nsi/T6_Annales/data/2022/2022_Nouvelle-Caledonie_J1.pdf).

- **Correction P2.Q1.**
    
    Le réseau services a pour adresse IP `195.168.254.0`.
    
- **Correction P2.Q2.**
    
    Le réseau services a pour adresse `195.168.254.0`. Comme le masque de sous-réseau utilisé est `255.255.255.0`, 254 adresses sont initialement disponibles (`195.168.254.1` à `195.168.254.254`, puisque l'adresse `195.168.254.255` est réservée pour le *broadcast* sur le réseau). Comme deux adresses sont déjà prises par le routeur 1 et le routeur 2, il en reste 252.
    
- **Correction P2.Q3.**
    
    Le serveur web accède à internet via le routeur 2, dont l'adresse sur le réseau services est `192.168.254.2`. C'est donc cette adresse qui est l'adresse de passerelle pour le serveur web.
    
- **Correction P3.Q1.**
    
    La ligne 2 montre que l'adresse MAC du serveur DNS est `8A:FD:54:49:D0:CC`.
    
- **Correction P3.Q2.**
    
    La couche Transport montre que le protocole utilisé est le protocole UDP.
    
- **Correction P3.Q3.**
    
    Le commentaire de la couche Application indique que l'adresse IP du serveur web est `192.168.254.201`.