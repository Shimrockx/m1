*#JeSaisPasPourquoiJAiMarquéÇa*

- iso 15408

- EBIOS

- ISO 274/271

# Introduction

Définition du Système d'Information : il n'est pas forcément éléectronique et peut être dans toute structure ou organisation qui traite/contrôle/stocke/partage/collecte de l'information.

Différencier :

- Data (Élément brut)

- Information (Référentiel permettant  d'interpréter la data)

- Connaissance (Extrapolation des informations)

Un SI se schématise autour du concept du traitement comme un bloc : les données y entrent (in), le traitement subit des perturbations et les données en sortent (out) avec de la perte. La sécurisation d'un SI revient à limiter les perturbations et les pertes. 

# L'iso 15408

ISO = International Standard Irganisation

La 15408 a été créée pour donner des normes de sécurité à respecter partout.  
Ainsi, 15 pays (UE, USA, Jpaon, Canada...) partagent des critères communs d'évaluation de sécurité de l'information.

(ISO 9000: qualité)

## PPST TOE

C'est un profil de protection

- **PP** : Vision de l'utilisateur du SI

  - Use cases - indépendant de toute implémentation

  - Définit les objectifs de sécurité à atteindre via :

    - l'environnement de travail

    - les exigences fonctionnelles

- **ToE** : Cibles de l'évaluation (ToE)

  - Tout composant du SI pouvant influer sur la sécurité (câbles, procédures...)

- **ST** : Cible de sécurité

  - Spécification technique de la sécurité

  - Vision des dev/admin/intégrateurs

  - Specifications fonctionnelles

  - Définition des risques et menaces

  - Définition des mesures de sécurité à employer

Pour faciliter l'implémentation de cet ISO à l'international, on définit des classes de sécurité.  
Chaque classe a des sous-classes et des sous-sous-classes

1. Audit Sécu

   Test/attaque du système (via des outils gratuits : Ness/OpenVas)

2. Communication

   Tous les moyens d'échanger l'information dans l'organisation (même non informatique)

3. Suppport cryptographique

   Gestion du codage (tout le monde peut décoder) ou du chiffrage (utilisation de clés, symétrie/asymétrie)

4. Protection de la user data

   Identification : déclarer l'identité != Authentification : vérifier l'identité

5. Protection de la vie privée

   Tout utilisateur doit être informé qu'on peut récupérer ses infos. Autrement toute la récupération de données est inutilisable légalement.

6. Protection des ToE

7. Authentification et Identificxation

8. Admin Sécu

9. Utilisation des ressources

10. Accès ToE

11. Chemins et canaux de confiance

**3 grands critères émergent de ces définitions**

- **Confidentialité** : Les bonnes personnes accèdent à l'information

- **Disponibilité** : L'accès à l'information est possible

- **Intégrité** : L'information n'est pas corrompue

- (en option) **Non répudiation** : Le fait d'avoir toujours une trace - ne pouvoir nier avoir fait quelque chose

# Implémentations de l'iso

## MARION

Méthode d'Analyse des Risques Informatiques et Optimisation par Niveau  
Fruit de la collaboration entre DGA & CLUSIF dans les années 80  
Dernière MàJ en 1998

Il s'agit de 27 indicateurs pour évaluer le niveau global de sécurité du SI, chacun a une note entre 0 et 4.

On y trouve les concepts de :

- vulnérabilité : point faible

- menace : potentiel d'exploitation/de déclenchement du point faible / de l'opportunité

- risque : impact, probabilité, occurence, proba occurence * score d'impact = score de risque

Déroulement en 4 phases :

1. Préparation : définir les limites de l'audit

   - Qu'est-ce qui est évalué ?

   - Dans quelles conditions ?

   - ToE, individus

2. Audit : on fait l'audit

3. Analyse : Dépouiller et attribuer des scores aux 27 indicateurs

   - Déterminer lesquels sont mauvais...

4. Plan d'action : Comment corriger

L'implémentation est relativement libre

## MEHARI

C'est l'évolution de MARION (un peu comme des pokémons)  
MÉthode Harmonisé d'Analyse des RIsques  
Issu du CLUSIF  
Méthode d'analyse quantitative des risques avec des questionnaires pré-définis et de règles de notation des critères

L'idée de base est qu'on ne fait pas disparaître un risque, on le diminue. Il faut donc

- accepter l'idée de risque résiduel

- se dire que le plan d'action n'a pas pour but de faire disparaitre tous les risques

C'est arrivé pile dans la grande époque de la gestion de projet avec le cycle en V



# EBIOS

Évaluation des Besoins et Identification des Objectifs de Sécurité  
Élaboré par la DGA et repris par le Ministère de l'Intérieur

5 modules :

1. Étude du contexte (lié à 2, 3 et 4)

2. Étude des évènements redoutés (lié à 1 et 4)

3. Étude des scénarii de menace (lié à 1 et 4)

4. Étude des risques (lié à 1, 2, 3 et 5)

5. Mesures de sécurité (lié à 4)



## Étude du contexte

Définir : 

1. Le périmètre

2. Les acteurs

3. Le niveau de sécurité

4. Les biens essentiels : éléments qu'on souhaite fournir (ex: service de messagerie)

5. Les biens supports : éléments permettant de concrétiser un bien support (ex: serveur Exchange)

6. Identifier les risques



Définir le cadre : 

- définir les limites

- vérifier la légitimité

- définir les paramètres à prendre en compte

- définir l'existant

- définir les sources de menace



Définir les acteurs. L'outil de définition est l'humain. On remplit un tableau selon la matrice RACI :

- Responsable

- Autorité

- Consulté

- Informé

Pour chaque fonctionnalité, on indique le rôle de chaque acteur du projet



Les fonctionnalités sont liées ensuite aux Biens Essentiels (BE), eux même liés à l'identifiation des acteurs liés, eux même liés aux Bien Supports (BS), eux-même liés à un "propriétaire".

Différents types de BS : Réseau, Logiciel, Matériel, Personnes, Organisation



Puis identification des contraintes aux fonctionnalités des BE. Elles peuvent être :

- techniques

- humaines

- conjoncturelles

- juridiques

- d'organisation

- stratégiques



Lister les éléments de sécurité en place et évaluer leur pertinence "à priori"



Étudier des sources de menace, il existe pour ça des listes pré-établies de sources. Les grandes catégories : 

- Humaines, naturelles, techniques

- Compétentes, Non-compétentes

- Hostiles, Non-hostiles

  

Préparer les métriques. pas entre 0&4 comme MARION et MEHARI : on peut choisir nous-même.  
EBIOS a des métriques par défaut, on peut les changer ou en prendre de nouvelles (pour les besoins métier par exemple). Cela permet :

- d'évaluer les risques liés à la sécurité

- de redéfinir la gravité et la vraisemblance d'un risque



Enfin, déterminer les bien via un listage et une matrice de dépendance entre BE et BS ("Si je touche à tel serveur, ques autres services vont être impactés ?").  
À chaque fois, on liste les mesures de sécurité mises en place



## Étude des évènements redoutés

- Déterminer les besoins en sécurité des biens essentiels (CDI)

- Impacts en cas de non respect (financiers, juridiques, sur l'image de marque, sur tiers...)

- Identifier les sources de menace

Tout cela permet de définir un évènement redouté (ex: utilisateur non-averti non hostile, rend indisponible le service de messagerie par flood de spam)



Déterminer et qualifier les évènements redoutés.  
Il existe des listes préétablies d'évènements redoutés, on peut aussi créer les siens.
Il faut étudier ce qui peut mal se passer **sans se foncaliser sur la source**

En entrée : 

- Liste des biens et éléments de sécurité

- Échelles de mesure

- Liste des sources de menace (pas de comment : juste les sources)

- Liste des évènements pré-établis

Le but est de déterminer la vraisemblance d'un évènement redouté, puis une classification des évènements du plus au moins grave.

Ex : 


On établit à partir de ça le **palmarès de la phobie des évènements**

| 3   | - <br/>-                                |
| --- | --------------------------------------- |
| 2   | - Impossibilié d'établir un devis<br/>- |
| 1   | - <br/>-                                |
| 0   | - <br/>-                                |



## Étude des scenarii de menace

- Estimer et identifier les scenarii pouvant amener aux évènements redoutés

  - Quelles sont les vulnérabilités exploitables et quels sont les moyens de les utiliser ?



Même logique que précédemment, centré sur "comment les choses pourraient mal tourner ?"

Le tableau est donc plutôt du genre :

| Scénario                             | Source                                                         | Vraisemblance |
| ------------------------------------ | -------------------------------------------------------------- | ------------- |
| Menace externe qui rend Wifi indispo | Employé indélicat<br/>Maintenance<br/>Virus<br/>Script-kiddies | 3 forte       |

**Attention** : un évènement redouté (est-ce que c'est grave ?) **!=** un scénario (est-ce qu'il y a des chances que ça arrive ?)

On établit aussi un palmarès



## Étude des risques

- Mise en évidence des risques

- Évaluation - Quantification

- Détermination des risques à corriger en premier



Ça consiste à croiser les flux :

- Quels sont les impacts si évènement arrive ?

- Quelle vraisemblance pour un scénario menant à cet évènement ?

- Est-ce grave pour notre entreprise, dnas le périmètre de l'étude ?

Risque = évènement (score impact) + scénario y amenant (score vraisemblance)

On a besoin de choisir l'option de traitement des risques :

- Traiter le risque :

  - Diminuer l'impact

  - Diminuer la vraisemblance

- Transférer le risque

- Accepter le risque

Les risques résiduels sont ensuite acceptables, ou acceptés.



## Mesures de sécurité

- Définition de ce qu'il faut mettre en place et de comment le contrôler

- Évalutation des risques résiduels

En gros, qu'est-ce qu'on met en place pour atteindre l'objectif de sécurité visé précédemment ?

Aboutit à terme sur le lancement du projet et l'évolution du SI.
