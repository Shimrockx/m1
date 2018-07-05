Architecture monolithique
===

*19/04/18*

## Principes du monolithique

"Qui est fait d'un seul bloc" => code dans un seul fichier.  
Créé à partir des premiers langages pour comminquer avec les machines (le B, le C). On scriptait tout dans un seul fichier.  
Ça a perduré avec le temps.  
=> ça a donné crise du logiciel par la suite

## Application monolithique

Ne fonctionne qu'avec une seule technologie parce que c'est conçu pour aller d'un point A à un point B  
Conçu pour remplir un but de la façon la plus simple possible.  
Ça bloque donc au niveau technologique => restreint dans techno utilisée de base.  
Le logiciel a une seule techno et donc c'est ce logiciel qui fait tout, quel que soit le niveau de l'action.  
Difficulté dans changement : on doit tout reprendre pour la moindre modification, il faudrait tout réécrire, sinon ça risque de pas s'emboiter avec le reste. De plus en plus compliqué de modifier quand le logiciel grossit.  
Excellentes possibilités d'optimisation du code par contre : on doit répondre à un besoin simple et on réfléchit à l'optimisation de son exécution.

### Déploiement

Il est assez simple, car on a un serveur, un processus.  
Encore une fois ça pousse à l'optimisation : bons temps de réponse, exécution rapide.  

### Gestion de projet

Methodo datant des années 70/80  
Pas de méthodes agiles, plutôt en cascade couplé avec cycle en V.  
Agile serait impossible à mettre en place. On part du principe qu'on a un CdC et qu'on doit tout mettre en place. Pas de modularité, on a un seul bloc !

Méthode en cascade héritée du BTP  : 

* recueil des besoins
* analyse détaillée
* conception détaillée
* Développement
* Test, recettes
* Livraison

Face à quelques difficultés, on améliore la cascade pour partir sur modèle en V !  
Il permet en effet plus facilement de revenir sur l'étape précédente.  Ça apporte plus de flexibilité  

## Avantages et inconvénients

Miam :

* Plutôt avec des langages bas niveau => grande maitrise logicielle et matérielle, logiciels très optimisés. On fait des géants très performants avec ça
* L'application va faire tous les traitements de A à Z => facile à conceptualiser, à concevoir.  Moins de complexité dans la gestion et la construction que microservice.
* Facilité de déploiement !

Berk : 

* Fort couplage des modules  => application difficile à revoir et à modifier sans avoir à tout revoir dans l'application
* le code devient vite difficile à comprendre => vriament dur à faire évoluer, en plus c'est prendre des risques si on mélange les équipes qui travaillent dessus. Le code devient n'importe quoi

## Monolithiques VS microservices

Joli tableau dans le prezi  

## Conclusion

La monolithique est encore très utilisée aujourd'hui, bien que microservices soient préconisés  
La majorité des logiciels aujourd'hui sur un PC par exemple est en monolithique.  
Les microservices sont surtout présents dans le web  
Entreprises s'y mettent mais logique et trucs présents sont encore en monolithique.  

On est vraiment bloqués sur une techno  
Forte possibilité d'amélioration du code  
Gestion de projet en cascade et V  
Un seul truc qui fait tout  

## Bouiche

J'ai pas écouté, le smiley Gui m'a déconcentré
