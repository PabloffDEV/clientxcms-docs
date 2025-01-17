---
sidebar_position: 1
---

# Proxmox
Proxmox est un panel très répandu pour gérer des machines virtuel très rapidement et simplement. Ce module permet de créer les CT/VM de vos clients avec les performances choisis.

:::info Modules
Pour utiliser les fonctionnalités suivantes, il faut que le module Proxmox soit activé sur votre ClientXCMS. [cliquez ici pour l'activer](../)
:::
| Création 	| Suspension 	| Expiration 	| Unsuspend 	| Importation 	| Options 	|
|----------	|------------	|------------	|-----------	|-------------	|---------	|
|     ✅    	|      ✅     	|      ✅     	|     ✅     	|      ✅      	|    ✅    	|

## Support
- LXC
- KVM
- NoVNC
- xtermjs

:::info Modules
Pour utiliser les fonctionnalités suivantes, il faut que le module Proxmox soit activé sur votre ClientXCMS. [cliquez ici pour l'activer](../#activation-dun-module)
:::
## Authentification
Créez un serveur ClientXCMS dans `Espace d'administration ` > `Système` > `Serveurs` > `Nouveau` en sélectionnant le type de serveur en "Proxmox".

![img](https://media.discordapp.net/attachments/1033142197102592131/1033149359543570432/unknown.png)

**Adresse IP** : Sous domaine ou Adresse IP du Proxmox

**Username** : Nom d'utilisateur (par défaut : root)

**Password** : Mot de passe du compte

En cas de succès de la connexion, il vous répondra "Success"
En cas d'échec, il vous le notifiera par une erreur.
## Liste des configurations
Vous pouvez voir la liste de vos configurations Proxmox depuis `Espace Administration` > `Proxmox` > `Configuration`.

![img](https://media.discordapp.net/attachments/1033142197102592131/1033151542074818570/unknown.png)

Vous pouvez modifier directement la configuration d'un produit dans la colonne "Actions" en cliquant sur le bouton bleu.

## Système d'adresse IP
Pour créer les VM/CT ClientXCMS doit savoir quelles adresses IPs il faut utiliser pour connecter au reste d'internet.
Pour les administrer, rendez-vous sur `Espace Administration` > `Proxmox` > `Configuration des IP`, vous pourrez également savoir quelle adresse est déjà utilisée, supprimer, modifier ou dupliquer une adresse.
![img](https://media.discordapp.net/attachments/1033142197102592131/1033422401763024976/unknown.png?width=1440&height=393)

## Système d'oses
Pour des meilleures performances et visuel, vous pouvez ajouter des OS Proxmox qui seront disponibles à l'installation des VM/CT.
Ce système à deux buts : Possibilité de modifier un OS qu'une seule fois et cela prendra effet sur toutes les configurations produit ayant cet OS. Et permet d'ajouter un nom plus simple pour vos clients (Exemple Debian 11 au lieu de local:iso/debian-11.5.0-amd64-netinst.iso)
Pour administrer les oses, rendez-vous sur `Espace Administration` > `Proxmox` > `Oses`, vous pourrez supprimer, modifier ou en ajouter.
![img](https://media.discordapp.net/attachments/475073153509490689/1045480568747462686/image.png?width=1440&height=382)

## Système de templates
Pour des meilleures performances et visuel, vous pouvez ajouter des Templates Proxmox qui seront disponibles à l'installation des VM/CT.
Ce système à deux buts : Possibilité de modifier une template qu'une seule fois et cela prendra effet sur toutes les configurations produit ayant cette template. Et permet d'ajouter un nom plus simple pour vos clients (Exemple Debian 11 au lieu de local:iso/debian-11.5.0-amd64-netinst.iso)
Pour administrer les templates, rendez-vous sur `Espace Administration` > `Proxmox` > `Templates`, vous pourrez supprimer, modifier ou en ajouter.
![img](https://media.discordapp.net/attachments/475073153509490689/1045481242793103452/image.png?width=1440&height=331)

### Création
Ajouter une IP depuis `Espace Administration` > `Proxmox` > `Configuration des IP` > `Nouveau`

![img](https://media.discordapp.net/attachments/1033142197102592131/1033423896638144542/unknown.png)
- **DHCP Mode** : Permet de connecter la VM/CT en DHCP
- **Auto Adresse MAC** : Génère automatiquement l'adresse mac
- **Parefeu** : Active le pare feu

### Importer un block d'IP
Importer rapidement des blocks d'ip depuis la page de création
![img](https://media.discordapp.net/attachments/1033142197102592131/1033425424534999192/unknown.png)


## Configuration de l'offre

![img](https://media.discordapp.net/attachments/1033142197102592131/1033434360197689565/unknown.png?width=1440&height=512)
## Création manuellement
Pour créer un service proxmox dans CLIENTXCMS, rendez-vous sur `Espace Administration` > `Services` > `Tout` > `Nouveau`.

Sélectionnez votre produit Proxmox et l'utilisateur, cochez "**Ajouter service automatiquement**". Puis vous cliquez sur suivant.
Après ceci vous pourrez définir le mot de passe root, l'os et un nom d'hôte personnalisé
![img](https://media.discordapp.net/attachments/1033142197102592131/1033403768252932156/unknown.png)

Puis cliquez sur "Créer".

Pour plus d'informations sur la création manuelle d'un service [cliquez ici](../../store/services#création-de-service)
## Importation
Pour importer une VM/CT qui est déjà sur votre Proxmox sur CLIENTXCMS, rendez-vous sur `Espace Administration` > `Services` > `Tout` > `Nouveau`.

Sélectionnez votre produit Proxmox et l'utilisateur, cochez "**Ajouter manuellement le service**". Puis cliquez sur suivant
Après ceci vous pourrez choisir la node et l'identifiant de la VM à importer sur CLIENTXCMS
![img](https://media.discordapp.net/attachments/1033142197102592131/1033416186601418793/unknown.png)

Puis cliquez sur "Créer".
La machine est désormais gérable depuis CLIENTXCMS.
Pour plus d'informations sur l'importation d'un service [cliquez ici](../../store/services#importation-de-service)

## Panel de gestion
![img](https://media.discordapp.net/attachments/1033142197102592131/1033310938922754078/unknown.png?width=1440&height=617)

## NoVNC
Le NoVNC n'esséciste un utilisateur spécifique sur votre Proxmox, pour activer cette fonctionnalité, rendez-vous sur votre `panel Proxmox` puis, connecter-vous avec votre compte Administrateurs.
Dans votre `datacenter`, section `Permissions` ensuite `users`, ajoutez un utilisateur avec comme nom d'utilisateur `novnc` en Realm PAM avec un mot de passé sécurisé.
![img](https://media.discordapp.net/attachments/475073153509490689/1045648570184912896/image.png)

Puis, allez dans la section `Role` pour créer un rôle pour avoir accès à la console.

![img](https://media.discordapp.net/attachments/475073153509490689/1045651682631106631/image.png)

Après ceci, allez dans la section `Permissions` et cliquez sur `Add` > `User permissions`.

![img](https://media.discordapp.net/attachments/475073153509490689/1045652720280936508/image.png)

Pour terminer, allez dans votre hébergement et modifiez votre fichier `.env` en y rajouter ces 2 deux lignes (ou modifier si elles y sont déjà)
```

PROXMOX_NOVNC_PASSWORD1="novnc"
PROXMOX_NOVNC_USERNAME1="novnc"
```
En mettant les identifiants de connexion de l'utilisateur novnc.

:::info
le "1" est l'identifiant du serveur CLIENTXCMS relié à votre Proxmox pour savoir quel est l'identifiant de votre serveur il se trouve dans `Espace Administration` > `Serveurs`
![img](https://media.discordapp.net/attachments/475073153509490689/1045653896820965376/image.png)
:::


## Option Supportés
- Espace disque additionnel
- Mémoire additionnel
- Cœurs additionnels
- swap additionnel
- sockets additionnel

## Ne pas envoyer des identifiants par mail

Par défault, CLIENTXCMS envoie les identifiants à votre client, mais vous pouvez le faire en modifiant le modèle d'email Proxmox en retirer les variables `%username%` et `%password%`.
Pour ceci, allez  `Espace Administration` > `Modèles d'email` > `Proxmox` en supprimant ceci : 
![img](https://media.discordapp.net/attachments/475073153509490689/1046014651831435294/image.png)
