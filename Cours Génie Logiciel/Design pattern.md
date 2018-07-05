Design pattern
===

## Exposé

### Intro

Ca aide les dev à bien organiser leur code

### Catégories

Création : manière de créer un objet ou un ensemble d'objets
Comportement : manière d'interprétation du code et des objets
Structure :

### Avantages

- Modularité : modules bien précis, on sait ou chercher

- Cohésion

- Couplage : modules s'instancient les uns dans les autres pour être réutilisés

- Réutilisabilité : bibliothèques, frameworks utiles à d'autres

### Incovénient

Complexité : c'est dur à apprendre (long)
Effort abstraction/synthèse : gros travail préalable et faut le prendre en main

### Les frameworks qui l'utilisent

.net en implémentation
JavaServer Faces
MVC
Spring

### Conclusion

C'est quand même utile

### Bouiche

C'est orienté objet, langage objet.   
Il a pas assez parlé des API  
API : bibliothèque qui pourront être réutilisés dans d'autres codes  
il est important en design pattern de réutiliser ce qui a déjà été fait



## Cours

### Historique

Création au début des années 70, à l'origine issu de l'architecture puis appliqué au monde logiciel dans les années 90

### Définition

Solution éprouvée à un problème récurrent dans la conception d'applications orientées objet (optimisation, évolutivité, clarté...)

Se définit en amont du développement et est indépendant du langage. 

Chaque design pattern se caractérise par 

- Un nom

- Une problématique

- Une solution

- Une conséquence

### Objectif

Rendre le code plus efficace

### Catégories

En tout 23 design patterns regroupés en 3 catégories : 

- Création : instantiation et configuration des classes et objets

- Structure : Organisation des classes d'une application

- Comportement : Organisation des objets pour qu'ils collaborent entre eux.

#### Création

L'idée est de créer des objets de manière appropriée à la situation. Les modèles les plus utilisés :

- Factory method : instancier plusieurs objets d'une même classe, aux paramètres différents

- Singleton : instancier un seul objet d'une classe donnée

#### Structure

Facilitent la conception via un moyen simple de réaliser des relations entre entités.

Le plus utilisé : Decorator.  
Permet de redéfinir certaines méthodes d'une classe pour certaines instances uniquement



#### Comportement

Identifient les modèles de communication entre les objets et les reproduisent

Le plus utilisé : Observer  
Une classe aux valeurs changeante contacte directement celle chagrée de l'affichage lorsque sa valeur change



### Avantages / Inconvénients

| Avantages                                                               | Inconvénients                                        |
| ----------------------------------------------------------------------- | ---------------------------------------------------- |
| Gain de rapidité, de qualité et baisse des coûts                        | Difficile d'accès, nécessite d'être expérimenté      |
| Réutilisabilité et bonnes pratiques                                     | Difficile de savoir lequel des 23 est le plus adapté |
| Bonne doc et aide à la communication entre développeurs car bien connus | Utile uniquement sur POO                             |






