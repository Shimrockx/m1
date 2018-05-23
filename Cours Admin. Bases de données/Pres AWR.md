Pres AWR
========================

AWR, c'est quoi ?

## Une radio :  Adventist World Radio  

Mais qu'estce que l'adventisme ?  
L'adventisme est un mouvement chrétien lancé au XIXe siècle dans le contexte du Second grand réveil aux États-Unis. L'expression se réfère à la doctrine de la deuxième venue de Jésus-Christ, aussi appelée « le retour du Christ ».    

Pour des raisons éthiques autant que théologiques, les adventistes pratiquent un style de vie sain, avec un régime alimentaire équilibré (souvent végétarien) et l'abstention de toute drogue, alcool et tabac. Les adventistes sont de ce fait devenus des promoteurs de la santé publique.

http://awr.org/program/fraco_awr/?regional=1  
=> écouter un extrait. 

https://fr.wikipedia.org/wiki/Adventisme

## Un aérodrôme : Awar

En papouasie Nouvelle Guinnée, selon code AITA des aéroports 

Mais qu'est-ce que le code AITA ?  
Un code IATA de l'aéroport, est un code à trois lettres désignant de nombreux aéroports à travers le monde, défini par l'Association internationale du transport aérien (AITA). Les caractères nettement visibles sur les étiquettes à bagages attachées aux comptoirs d'enregistrement de l'aéroport sont un exemple d'utilisation de ces codes.  

Le besoin d'identification des aéroports est né avec l'apparition des premières lignes commerciales (dans la période 1914-1930). Le système existant du National Weather Service est alors repris aux États-Unis : chaque ville équipée d'une station est décrite par deux lettres, par exemple LA pour Los Angeles ou PH pour Phoenix.  
Néanmoins, dès les années 1930, ce système s'est révélé insuffisant et les compagnies aériennes ont alors opté pour un système à trois lettres (offrant 263 = 17 576 combinaisons possibles).
Parmi ces codes peu intuitifs, celui de Kill Devil Hills (Caroline du Nord) mérite d'être signalé : FFA pour First Flight Airport (en), le lieu où les frères Wright effectuèrent le premier vol motorisé contrôlé d'un avion5 le 17 décembre 1903.
https://fr.wikipedia.org/wiki/Liste_des_codes_AITA_des_a%C3%A9roports/

## Un outil Oracle : Automatic Workload Repository

### Présentation

L’une des grandes forces d’Oracle est la panoplie d’outils qu’il propose, notamment l’Automatic Worload Repository.   
Comme son nom l’indique, il collecte et stocke les données sur l’utilisation de la base, autant sur les requêtes effectuées que les ressources utilisées.  
C’est évidemment un outil très utile dans le cas d’étude de performance et d’optimisation de base de données.

http://blog.sedona.fr/2013/10/rapports-oracle-awr/

### AWR Features

The AWR is used to collect performance statistics including:

*  Wait events used to identify performance problems.
*  Time model statistics indicating the amount of DB time associated with a process from the `V$SESS_TIME_MODEL` and `V$SYS_TIME_MODEL` views.
*   Active Session History (ASH) statistics from the `V$ACTIVE_SESSION_HISTORY` view.
*  Some system and session statistics from the `V$SYSSTAT` and `V$SESSTAT` views.
* Object usage statistics.
* Resource intensive SQL statements.

The repository is a source of information for several other Oracle 10g features including:

* Automatic Database Diagnostic Monitor
* SQL Tuning Advisor
* Undo Advisor
* Segment Advisor
