Cours 3
========================

RMI : client/serveur en java. C'est un peu vieux mais ça permet de comprendre comment ça fonctionne. Les autres (suivants) sont globalement basés sur la même philosophie.  

Se concentrer sur la communication plus que sur le traitement. 


# CORBA 

Même philosophie que RMI 

Architecture d'objets distribués (voir pdf) => architecture global. Principe de fonctionnement est celui de RMI : client /serveur - appelant / appelé . L'objectif est de pouvoir assurer cette communication, come pour RMI  

Architecture :  

* Notion de client et de serveur 
* Couche TCP IP 

Chacun fait ce qu'il veut avec les objets. L'idée est que chaque demande se fasse dans un langage générique. On implémente un BUS logiciel (ORB) dans lequel on fait passer demandes. Dedans on a un traducteur qui traduit demande en un format générique et véhicule au serveur qui retraduit. Les adaptateurs qui font la traduction sont les OA  
Y a toujours besoin d'une interface qui permet de savoir tout ce qu'on peut implémenter. Ici c'est IDL, un fichier texte dans un langage particulier qui implémente l'interface. Ce fichier est partagé par client et serveur.   
À partir IDL => projection pour récupérer (implémenter ?) interface, chacun à sa façon selon client ou serveur. IDL se compose de 6 fichiers  
On a aussi un daemon (daemon ORB = orb ), même fonctionnement qu'ailleurs, en tache de fond il orchestre communications 
 

On doit définir un module pour chaque "élément" (à préciser) on peut pas en envoyer seuls  
```
	Module { 
	   Interface {  
	      Attributs : type nom options;   
	      Méthodes : type retour, statut, nom, paramètres type de passage (in ou out ou inout en entré en sortie ou les deux) 
	   }  
	} 
```
Tout modification a niveau de l'objet implique une régénération complète : on évite donc ! 
 
Ordre de démarrage :

* orbd  
* serveur 
* client 