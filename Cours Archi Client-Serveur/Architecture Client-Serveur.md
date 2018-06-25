# Intro

On va bosser avec Java.

Les différentes "versions" de Java :

- JME : Mobile

- JSE : Standard

  - JRE : JVM (Virtual Machine) + librairies de base

  - JDK : IDE

- JEE : Entreprise

Rapide rappel sur l'UML :

| NomClasse               | Nom de l'objet                   |
| ----------------------- | -------------------------------- |
| - Attr1<br/>-Attr2      | Données : ce qu'il est           |
| +Méthode1<br/>+Méthode2 | Traitement : ce qu'il sait faire |

Signe - : privé
Signe + : Public

Pour symboliser l'héritage, on fait une flèche de l'enfant vers le parent.

# RMI

## Présentation

Architecture (client/serveur, mais on s'en doutait) crée par Sun. C'est un package : ensemble de librairies.
RMI pour Remote Method Invocation
Centralise un service sur un serveur, les clients s'y connectent pour l'obtenir (on parle plutôt de données brutes).
Les clients viennent se connecter à un objet mis à disposition par le serveur, pour obtenir un service. 

On a besoin du jdk pour l'exploiter.
C'est basé sur RPC : Remote Procedure Call (Accès à une procédure à distance...)
On a besoin du même langage et de la même version sur le client ET le serveur.

## Structure

RMI a une structure en couches

| Côté client                                                                                        | Daemon                                                     | Côté serveur                                                   |
| -------------------------------------------------------------------------------------------------- | ---------------------------------------------------------- | -------------------------------------------------------------- |
| Interface                                                                                          | rmi registry<br/>(Contient annuaire des objets avec alias) | Interface                                                      |
|                                                                                                    |                                                            | Classe<br/> (hérite de l'interface)                            |
| Appli<br/>(va chercher objet dans rmi registry)<br/>Récupère l'alias (objet = alias) dans annuaire |                                                            | Appli<br/> (connectée au rmi registry)<br/>(utilise la classe) |
| Stub                                                                                               |                                                            | Skell                                                          |

À chaque appel à un objet distant, stub intercepte l'appel, et le communique au skell qui interroge l'objet, puis retransmet le résultat au stub qui le communique à l'appli.

---

*21/11/17 - Cours 2*

Rappels sur RMI : Stub / Skel, RMIResgistry... Répétition du schéma de la sctructure au tableau.

## Modèle de programmation

D'abord l'interface : pour que le client connaisse l'alias + ce que fait l'objet

Puis la classe qui implémente l'interface

---

*09/02/17 - Cours 3*

## Conclusion

RMI : client/serveur en java. C'est un peu vieux mais ça permet de comprendre comment ça fonctionne. 
Les autres architectures qu'on va voir ensuite sont globalement basées sur la même philosophie.

Se concentrer sur la communication plus que sur le traitement.



# CORBA

Même philosophie que RMI

Architecture d'objets distribués (voir pdf) => architecture globale. 

Le principe de fonctionnement est celui de RMI : client /serveur - appelant / appelé . 
L'objectif est de pouvoir assurer cette communication, comme pour RMI

## Architecture

- Notion de client et de serveur

- Couche TCP IP

Chacun fait ce qu'il veut avec les objets. L'idée est que chaque demande se fasse dans un langage générique. 

On implémente un BUS logiciel (ORB) dans lequel on fait passer les demandes. Dedans on a un traducteur qui traduit la demande en un format générique et la véhicule au serveur, qui retraduit. Les adaptateurs qui font la traduction sont les OA 

### IDL

Il y a toujours besoin d'une interface qui permet de savoir tout ce qu'on peut implémenter. Ici c'est IDL : un fichier texte dans un langage particulier qui implémente l'interface. Ce fichier est partagé par le client et le serveur.
À partir de IDL, il y a une projection pour implémenter l'interface, chacun à sa façon selon s'il s'agit du client ou du  serveur. À l'issue de cette projection, IDL se décompose en 6 fichiers.

On doit définir un module pour chaque "élément" (à préciser), on peut pas en envoyer seuls. 

```ini
    Module { 
       Interface {  
          Attributs : type nom options;   
          Méthodes : type retour, statut, nom, paramètres type de passage (in ou out ou inout en entré en sortie ou les deux) 
       }  
    }
```

Tout modification au niveau de l'objet implique une régénération complète : on évite donc !

### Suite

On a aussi un daemon (daemon ORB = orb ), qui a le même fonctionnement qu'ailleurs : en tache de fond, il orchestre les communications.

Ordre de démarrage :

- orbd

- serveur

- client
