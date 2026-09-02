# Exercices (Soluce)

# **Interconnexion de deux réseaux.**

![deux_res.png](Exercices%20(Soluce)/deux_res.png)

Pour chaque réseau, on choisit :

- Pour les adresses IP des routeurs : les dernières possibles.
- Pour l’adresse IP du serveur DHCP : la dernière possible, une fois celle des routeurs attribuées.

## **Compléter les adresses IP ci-dessous**

**a) Pour le réseau 192.168.1.0**

- Passerelle :
- Serveur DHCP :

- Passerelle : 192.168.1.254
- Serveur DHCP : 192.168.1.253

**b) Pour le réseau 10.0.0.0**

- Passerelle « Routeur 0 » :
- Passerelle « Routeur 1 » :

- Passerelle « Routeur 0 » : 10.255.255.254
- Passerelle « Routeur 1 » : 10.255.255.253

**c) Pour le réseau 192.168.2.0**

- Passerelle :
- Serveur DHCP :

- Passerelle : 192.168.2.254
- Serveur DHCP : 192.168.2.253

# **Interconnexion de quatre réseaux.**

![3 routeurs](https://mcoilhac.forge.apps.education.fr/site-nsi/reseau/images/quatre_res.png)

## **Compléter ci-dessous pour le réseau 192.168.1.0 :**

Passerelle « Routeur 0 » :
Serveur DHCP :

**Solution**
Passerelle « Routeur 0 » : 192.168.1.254
Serveur DHCP : 192.168.1.253

## **Compléter ci-dessous pour le réseau 10.0.0.0**

Passerelle « Routeur 0 » :
Passerelle « Routeur 2 » :

**Solution**
Passerelle « Routeur 0 » : 10.255.255.254
Passerelle « Routeur 2 » : 10.255.255.253

## **Compléter ci-dessous pour le réseau 172.16.0.0**

Passerelle « Routeur 2 » :
Passerelle « Routeur 1 » :

**Solution**
Passerelle « Routeur 2 » : 172.16.255.254
Passerelle « Routeur 1 » : 172.16.255.253

## **Compléter ci-dessous pour le réseau 192.168.2.0**

Passerelle « Routeur 1 » :
Serveur DHCP :

**Solution**
Passerelle « Routeur 1 » : 192.168.2.254
Serveur DHCP : 192.168.2.253

## **Tables de routage :**

<aside>

### **Compléter ci-dessous pour le routeur 0**

| **Réseau de destination** | **Masque** | **Passerelle** | **Via l’interface** |
| --- | --- | --- | --- |
| 192.168.2.0 | 255.255.255.0 |  |  |
| 172.16.0.0 | 255.255.0.0 |  |  |

Solution 

| **Réseau de destination** | **Masque** | **Passerelle** | **Via l’interface** |
| --- | --- | --- | --- |
| 192.168.2.0 | 255.255.255.0 | 10.255.255.253 | 10.255.255.254 |
| 172.16.0.0 | 255.255.0.0 | 10.255.255.253 | 10.255.255.254 |
</aside>

<aside>

### Compléter ci-dessous pour le routeur 1 :

| **Réseau de destination** | **Masque** | **Passerelle** | **Via l’interface** |
| --- | --- | --- | --- |
| 192.168.1.0 | 255.255.255.0 |  |  |
| 10.0.0.0 | 255.0.0.0 |  |  |

Solution 

| **Réseau de destination** | **Masque** | **Passerelle** | **Via l’interface** |
| --- | --- | --- | --- |
| 192.168.1.0 | 255.255.255.0 | 172.16.255.254 | 172.16.255.253 |
| 10.0.0.0 | 255.0.0.0 | 172.16.255.254 | 172.16.255.253 |
</aside>

<aside>

### Compléter ci-dessous pour le routeur 2 :

| **Réseau de destination** | **Masque** | **Passerelle** | **Via l’interface** |
| --- | --- | --- | --- |
| 192.168.1.0 | 255.255.255.0 |  |  |
| 192.168.2.0 | 255.255.255.0 |  |  |

Solution

| **Réseau de destination** | **Masque** | **Passerelle** | **Via l’interface** |
| --- | --- | --- | --- |
| 192.168.1.0 | 255.255.255.0 | 10.255.255.254 | 10.255.255.253 |
| 192.168.2.0 | 255.255.255.0 | 172.16.255.253 | 172.16.255.254 |
</aside>

[Exercices](Exercices%20(Soluce)/Exercices%2034f9d189413580edace7d301da0ad7f8.md)