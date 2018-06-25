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
