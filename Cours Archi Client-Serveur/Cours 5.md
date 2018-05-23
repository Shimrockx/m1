Cours 5
========================

Arrivé en retard, y a plein de trucs chelous marqués au tableau c'est flippant

## JEE

JEE est un srveur d'application (Apache TomCat) non pas un simple chef d'orchestre
On va se concentrer sur la partie EJB.

JEE est une architecture, pas un langage. C'est du design pattern, une manière de développer et de penser ls choses (le langage rest du java)

### EJB 

EJB = Java Bean

Plusieurs formes d'EJB : 

* Session Beand (partie business/traitement)
* Entity Bean (partie données)

#### Session Bean

Deux types de session Bean :

* Stateful (avec état)
* Stateless (sans état)

Qu'est ce que ça veut dire ?  Si le client se connecte à notre logiciel, est-ce qu'il a une version du catalogue (stateful) ou accès au seul et unique catalogue, unique pour tous (stateless)

#### Entity Bean 

C'est la couche persistance est celle qui va communiquer avec la base de données. On ne fait plus de SQL, on passe par la couche persistance (ORM)  
On trouve JPA (en ORM ?).  
Chaque = une table en bdd (entity, comme dans symfony)


### Méthode travail

#### Annotation

Existe depuis version 5

annotation avec un "@" devant (comme dans symfony). Ca permet de définir les trucs,par exemple sateful :  
@Stateful

#### SessionBean

Chaque SessionBean  doit définir deux interfaces et une classe  
Les deux interfacs sont remote et locale. En général, la locale hérite de la remote. On a ensuite une classe qui implémente les deux interfaces à la fois.

Déclarer une interface :  

	@Remote
	public interface Icalc {  
		public double add ()(double a, double b);
		...
		...
	}

Pour la classe :
  
	@Stateful
	public class Calc implements ICalc {
		public double add(double a, double b) {
			return a+b;
	}
	....
	...
	}

# TP

New > Project > enterprise application project  
choisir un nom (ne pas mettre ejp ça fait planter eclipse)  
Next  
(on est en train de créer une appli avec les différentes couches qu'on peut avoir dans le serveur)  
New module > on sélectionn les couches qui nous intéressent (ici tout sauf connector)  
Puis finish deux fois. Ca crée automatiquement 4 projets : le principal et les couches.  

Dans rpojet EJB, clic droit > New > SessionBean. Mettre un nom d epackage