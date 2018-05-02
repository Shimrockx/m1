Exposé MicroServices & Webservices
========================

Alexandre et Morgan

## Présentation

C'est quoi ? > Méthod de devloppement logiciel basé sur conception de plusieurs tout petits services indépendants et autonomes.
Opposé au monolithique.
Système minimaliste, souple : si on intervient ou conçoit un service, on a en soit pas à se soucier des autres, ni de redéployer l'application en entier.

4 points principaux :** componentization**

1 > Cohérence et logique et logique système : KISS, ou you has one job

2 > spécificité des fonctionnalités : ils sont tous indépendants l suns des uns, is un tombe les autres non. 

3 > Autonomie des services

4 > 

Opposition monolithique et microservices : monolithique = une grosse BDD partagée
micros : plein de petites, parfois partagées pour quelques microservices

## Communication des ms entre eux

Deux grosses manières : REST et bus de message 

### REST : par http(s)
#### Avantage : 
tous les services se comprennent (grand interopérabilité entre systèmes et applications)
assez simple à mettre en place

#### Inconvénient : 
débordment de messages http(s), chacun envoyant les siens, surcharge réseau

### Bus de messages
un serveur réceptionne tous les messages et le tranmet aux autres services
il ne les traite pas ! renvoie juste, plutot rapide

#### Inconvénient :
 fragile, si le serveur tombe c'est la merde.



Les ms impliquent de repenser l'équipe de dev, qui s'oriente autour des fonctionnalités et non des compétence smétier. on a aussi des petites équipes et une orientation servis = un produit

## Avantages et inconvénients

### avantages

dévelopements et déploiement indépendant : Petites équipes, différents langages pour chaque service. 

## Démonstration technique

