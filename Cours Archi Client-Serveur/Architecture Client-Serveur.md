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

On a aussi un daemon (daemon ORB = orb ), qui a le même fonctionnement qu'ailleurs : en tache de fond, il orchestre les communications.

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

## Démarrage

Ordre de démarrage :

- orbd

- serveur

- client

---

*30/04/18 - Cours 4*

## TP

Voir TP Banque

---

*22/05/18 - Cours 5*

# JEE

## Introduction

JEE est un serveur d'application (Apache TomCat) non pas un simple chef d'orchestre
On va se concentrer sur la partie EJB.

JEE est une architecture, pas un langage. C'est du design pattern, une manière de développer et de penser les choses (le langage rest du java)

## EJB

EJB = Java Bean

Il y a plusieurs formes d'EJB :

- Session Bean (partie business/traitement)

- Entity Bean (partie données)

### Session Bean

On a deux types de session Bean :

- Stateful (avec état)

- Stateless (sans état)

Qu'est ce que ça veut dire ? >> Si le client se connecte à notre logiciel, est-ce qu'il a une version du catalogue (stateful) ou accès au seul et unique catalogue, unique pour tous (stateless) ?
En gros la version avec état instancie les ressources là ou la sans état agit sur une entité commune et partagée.

### Entity Bean

C'est la couche persistance et celle qui va communiquer avec la base de données. On ne fait plus de SQL, on passe par la couche persistance (ORM)
On va utiliser JPA (qu'on peut considérer comme une API orm). 
Chaque entité sera une table en bdd

## Méthode de travail

### Annotations

Existent depuis la version 5

Les annotations s'écrivent avec un "@" devant . Ça permet de définir les trucs, par exemple sateful : @Stateful

### SessionBean

Chaque SessionBean doit définir deux interfaces et une classe
Les deux interfaces sont *remote* et *locale*. En général, la locale hérite de la remote. On a ensuite une classe qui implémente les deux interfaces à la fois.

Déclarer une interface :

```java
@Remote
public interface Icalc {  
    public double add ()(double a, double b);
    ...
    ...
}
```

Pour la classe :

```java
@Stateful
public class Calc implements ICalc {
    public double add(double a, double b) {
        return a+b;
}
....
...
}

```

## TP

New > Project > enterprise application project 
    choisir un nom (ne pas mettre ejp ça fait planter eclipse) 
Next (on est en train de créer une appli avec les différentes couches qu'on peut avoir dans le serveur) 
New module > on sélectionne les couches qui nous intéressent (ici tout sauf connector) 
Puis finish deux fois. 

Ca crée automatiquement 4 projets : le principal et les couches.

Dans Projet EJB, clic droit > New > SessionBean. Mettre un nom de package.

Il est possible de résumer ce TP comme un des plus mal expliqués de l'année (derrière le dev mobile quand même). Rien ne marchait, explications uniquement pour le premier rang, compréhension 0.
