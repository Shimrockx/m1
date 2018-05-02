SOA
========================

Service Oriented Architecture

## HistoriqueHistorique 

jusqu 90, les trucs étaient sur des gros serveurs (mainframe) en arhci monolothiques

en 90 est apparu le client/serveur avec l'appartition / la démocratisation des PC
Puis distribué années 2000

### Client / serveur

soit cnetré sur le client, soit centré su rle servur. Schéma sur PDF. Réseau entre es dux, l'un a plus de charge que l'autre.
Le problèm : dépendances, biblioth_ques, api à importer...


#### Application web

Très ouvertes/ fcails à déplyer

#### cloud computing 
 
Location d'ordi pour que les autres se dédouanent de la gestion



Ca a été très centralisé, puis moins avec client/serveur, puis on es tpassé au distribué

## Les architectures de service

### Principaux composants

Un service : un composant, une fonctionnalité d'un SI mis à disposition ds clients.
Il fonctionne ne boite noire : on se fout de savoir comment il fonctionne. On le vuet performant, robuste, et indépendant de notre contexte (n tant que client)

### solution métier
L'utilisateur ne s'intéresse pas au service mais à l'applicatio qui utilise ce service. On en a deux la backend et la frontend. Tout ça compose la "solution métier"

### SOA 1.0

né dnas les années 2000. Première génération
Né d'un besoin fort de se connecter ua beosin. 

avantage : ouverture du SI
inconvénient : les dev ont pris le monoplithe tel quel et mis des servics autour : pas de robustesse et de performance

### SOA 2.0

architecture microservice

ce qui change, c'est la façon de voir son entreprise : 
chaque section devient un service. Vision "verticale"

inconvénient : le microservice a une durée de vie courte. Ca change très vite, faut pouvoir suivre la cadence. plein de services dans des technos différentes, 

### SOA 3.0

devient un truc de mode : tout le monde en veut et veut un truc multi partenaires
Avec l'essort des objets connectés on évolue vers des archis plus reactives et besoin de temps réel

on rajoute par rapport à la précédent eune couche IoT, qui communiquera directement avec les obj connectés, et plusieurs gestionnaires, APÏ pour interface rles différents servies entre eux, ainsi qu'un gestionnaire d'PAI.

on a encore deux parties front/back

Archi plus complexe car besoins ont évolué

## Idées reçues

SOA liée à techno ou protocole particuliers : ** FAUX**
Lié à un outil : **FAUX** (si on utilise par exemple un esp, un répartisseur de mssage utilisé par quelqu'un d'autre en SOA, il ne sera pas forcément en SOA)
SOA n'est pas égal à web service ou micro service
Un web service n'est pas non plus un SOA 
SOA se réfléchi, c'est pas adapté à tout


## Conclusion

SOA c'est un esemble  de concepts et de pratqiues qui permettent de mettre en place une architecture.
Nécessite d eraisonner sur archi de l'application, la méthodologie mise ne oeuvre. Et tout organisation n'est pas adapté au SOA
