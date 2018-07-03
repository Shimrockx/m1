*23/11/2017 - Cours 1*

On va DL une machine virtuelle et faire un TP en anglais. Mais d'abord, présentation globale  appuyée sur cours en PDF.

Note : à partir d'un rapport fait sur TP + partiel écrit (à partir TP)

# Introduction

Connaître le modèle relationnel (prérequis pour le cours)
Documentation (EN) : [www.oracle.com](http://www.oracle.com)
Doc plus "essentielle" en FR fournie par le prof ("essentiel" en 110 pages)

## Pourquoi Oracle ?

- Très paramétrable (pas une boite noire)

- Performant en exécution de requête: on peut voir comment fonctionne le moteur de requête, comment il compile la requête



# Grands concepts

## La mémoire

Pour analyser, on a besoin de mémoire de stockage. La principale est la **SGA** (System Global Area)

- Partagée par tous utilisateurs 

- Allouée au départ >> doit être la plus grosse possible

- But : mémoire tampon / optimiser entrée/sortie



## Les processus de fond

Ils exécutent des actions asynchrones d'écriture et de contrôle



**CKPT – Checkpoint**

- assure la synchronisation et la cohérence des données



**SMON – System Monitor**

- Restaure après panne

- Nettoie segment temporaire

- Fusionne certains espaces (extents) libres



## Structure physique

Des fichiers sur le disque

- Contrôle >> spécifie nom & emplacement fichiers, nom base...

- Plusieurs fichiers de données pour stocker données

- Fichiers de reprise après panne (au moins 2)



## Structure logique

Ce sont des couches logiques rajoutées pour gérer plus finement la mémoire

- Bloc de données : unité de donnée la plus fine

- Extents : ensemble contigü de blocs

- Segment : ensemble d'extends dédiés à un même objet

- Tablespace : ensemble de segments. Un tablespace = un ou plusieurs fichiers de données

  -> c'est là où y sont très forts chez Oracle



## Contenu d'un schéma

Correspond à un utilisateur : tout l'environnement physique et logique est lié à user & espace

C'est l'ensemble des objets de l'utilisateur manipulables en SQL



## Stockage des tables

Tuple = ligne, enregistrement



## Le rôle DBA

**Jamais rien écrire sur compte SYS/CHANGE_ON_INSTALL !**



## Informations sur le dictionnaire

Ensemble de tables de l'utilisateur SYS, contient les infos principales



## Structure du dictionnaire

On y trouve toutes les vues des utilisateurs



# Taches élémentaires d'administration

## Créer un base de données

Planifier la base : réflexion en amont sur différents points stratégiques (tables et indexes, encodage, taille des blocs...)

Étapes de création :  Y a beaucoup de paramètres (voir PDF)  
Une alternative consiste à laisser Oracle gérer ce qui simplifie grandement les commandes lors de la création. On le spécifie dans les paramètres d'installation.

Paramètres de l'instance : On parle de pfile (parameter file ?), pas tout bien compris mais probablement le fichier où on définit ces paramètres  
Faire TOUJOURS une copie du fichier de contrôle (en avoir au moins 2)

## Démarrer une base de données

OEM (Oracle Enterprise Manager) : interface graphique  
SQL*Plus : ligne de commande



# Gestion des fichiers, tablespaces & espace libre

## Fichiers de contrôle

Décrit la structure physique de la base  
Extension .ctl

## Fichiers de reprise

Ce sont des sortes fichiers de log, qui notes tous les changements et sont utiles pour redémarrage après une panne



## Fichiers de données

Fichiers où sont stockées toutes les structures logiques, chaque fichier est associé à un tablespace  
Extension .dat
