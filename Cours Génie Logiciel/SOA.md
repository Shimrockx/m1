SOA
===

Service Oriented Architecture

## HistoriqueHistorique

Jusqu 90, les trucs étaient sur des gros serveurs (mainframe) en archi monolothiques

En 90 est apparu le client/serveur avec l'appartition / la démocratisation des PC
Puis distribué dans les années 2000

### Client / serveur

soit cnetré sur le client, soit centré su rle servur. Schéma sur PDF. Réseau entre es dux, l'un a plus de charge que l'autre.
Le problèm : dépendances, biblioth_ques, api à importer...

#### Application web

Très ouvertes / faciles à déployer

#### Cloud computing

Location d'ordi pour que les autres se dédouanent de la gestion

Ça a été très centralisé, puis moins avec client/serveur, puis on est passé au distribué

## Les architectures de service

### Principaux composants

Un service : un composant, une fonctionnalité d'un SI mis à disposition des clients.  
Il fonctionne en boîte noire : on se fout de savoir comment il fonctionne. On le veut performant, robuste, et indépendant de notre contexte (en tant que client)

### Solution métier

L'utilisateur ne s'intéresse pas au service mais à l'application qui utilise ce service. On en a deux : la backend et la frontend. Tout ça compose la "solution métier"

### SOA 1.0

Né dans les années 2000. Première génération
Né d'un besoin fort de se connecter au besoin. 

Avantage : ouverture du SI
Inconvénient : les dev ont pris le monolithe tel quel et mis des services autour : pas de robustesse et de performance

### SOA 2.0

Architecture microservice

Ce qui change, c'est la façon de voir son entreprise : chaque section devient un service. Vision "verticale"

Inconvénient : le microservice a une durée de vie courte. Ça change très vite, faut pouvoir suivre la cadence. Plein de services dans des technos différentes, 

### SOA 3.0

Devient un truc de mode : tout le monde en veut et veut un truc multi-partenaires
Avec l'essort des objets connectés on évolue vers des archis plus réactives et besoin de temps réel

On rajoute par rapport à la précédente une couche IoT, qui communiquera directement avec les objets connectés, et plusieurs gestionnaires, API pour interfacer les différents servies entre eux, ainsi qu'un gestionnaire d'API.

On a encore deux parties front/back

Architecture plus complexe car besoins ont évolué

## Idées reçues

SOA est liée à une techno ou un protocole particulier : **FAUX**
Lié à un outil : **FAUX** (si on utilise par exemple un esp, un répartisseur de message utilisé par quelqu'un d'autre en SOA, il ne sera pas forcément en SOA)
SOA n'est pas égal à webservice ou microservice
Un webservice n'est pas non plus un SOA 
SOA se réfléchi, c'est pas adapté à tout

## Conclusion

SOA c'est un esemble  de concepts et de pratiques qui permettent de mettre en place une architecture.
Nécessite de raisonner sur archi de l'application, la méthodologie mise en oeuvre. Et toute organisation n'est pas adaptée au SOA
