Exposé MicroServices & Webservices
===

## Présentation

C'est quoi ? > Méthode de développement logiciel basé sur conception de plusieurs tout petits services indépendants et autonomes.
Opposé au monolithique.
Système minimaliste, souple : si on intervient ou conçoit un service, on a en soit pas à se soucier des autres, ni à redéployer l'application en entier.

4 points principaux : **componentization**

1 > Cohérence et logique système : KISS, ou you has one job

2 > Spécificité des fonctionnalités : ils sont tous indépendants les uns des uns, si un tombe les autres non. 

3 > Autonomie des services

4 > 

Opposition monolithique et microservices : monolithique = une grosse BDD partagée
micros : plein de petites, parfois partagées pour quelques microservices

## Communication des microservices entre eux

Deux grosses manières : REST et BUS de message 

### REST : par http(s)

#### Avantages :

- Tous les services se comprennent (grande interopérabilité entre systèmes et applications)

- Assez simple à mettre en place

#### Inconvénient :

- Débordement de messages http(s), chacun envoyant les siens, surcharge réseau

### BUS de messages

Un serveur réceptionne tous les messages et le transmet aux autres services
Il ne les traite pas ! Renvoie juste, plutôt rapide

#### Inconvénient :

 Fragile, si le serveur tombe c'est la merde.





Les microservices impliquent de repenser l'équipe de dev, qui s'oriente autour des fonctionnalités et non des compétences métier. On a aussi des petites équipes et une orientation un service = un produit

## Avantages et inconvénients

### Avantages

- Développements et déploiement indépendants

- Petites équipes, différents langages pour chaque service. 
