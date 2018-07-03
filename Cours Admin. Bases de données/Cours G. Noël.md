*04/05/2018*

# Oracle

## Types de données

* Caractères
  * Varchar2
  * NVarchar2 (Unicode)
* Numérique
  * Number
  * `Binary_float / Binary_double`
* Date
  * Date
  * Timestamp
* RowID
  * RowID (adresse d'un tuple)

## Compression de données

On peut pas mettre tous les textes dans les tables, ce serait énorme

* Compression standard :  
  Sorte de zip  
  Transparent pour les applis

* Compression avancée  
  `ALTER TABLE toto ROW STORE COMPRESS ADVANCED` 

## Cluster de tables

Tables distinctes qui partagent une colonne commune.  Elles stockent alors les données dans les mêmes blocs.  
Ça vient du fait qu'il faut éviter la redondance mais pourtant elle peut être utile pour éviter de faire des jointures.  
=> **Cluster de table** : au lieu de stocker deux fois la data on la stocke une fois physiquement dans une colonne qui sera utilisée par plusieurs tables.

### Avantages / inconviénients

Les + 

* I/O réduits pour les disques

...j'ai raté le reste

### Cluster indexé

Cluster qui utilise un B-Tree

## SYS et SYSTEM

Deux schémas spécifiques  

SYS = compte administratif contient dictionnaire de données (données statiques utilisées dans les tâches administratives)  
Ne doit pas être modifié par l'utilisateur !  

SYSTEM = compte système (moins important que SYS). Contient les tables d'information, utiles aux options et plugins Oracle. On passe plutôt par ce compte pour les outils du genre pour éviter de tout fusiller

## Les index

Index : Structure de données qui permet de retrouver la bonne donnée dans une table  
Évite de devoir faire un full scan  

Principal index : B-Tree (et ses cousins du même genre de nom)  

### B-Tree

Arbre le plus souvent utilisé  
B veut dire quelque chose qu'il a expliqué au niveau structure, les liens se font vraiment en bout d'arbre

### Autres structures

#### Le bitmap

Un grand champ avec des 1 et 0 pour dire y a ou y a pas.  
Indique où se trouve la donnée, proche du système de hashage

#### Basé sur fonction

Très rare, problème: trouver la bonne fonction  

#### Tables organisées par index

Les données sont directement dans l'index.

## Dictionnaires de données

Tables en lectures seule avec des infos :

* Objets schémas de BD
* Volume utilisé par les objets schémas
* nom, rôle, set, privilèges des utilisateurs
* modifications lors de DDL

On va avoir plusieurs tables dont les noms vont commencer par :

* DBA_ : tous les objets
* ALL_ : objets pour lesquels l'utilisateur a le privilège
* USER_ : Objets dont l'utilisateur est le propriétaire

## Vues de performances Dynamiques

Changent avec état / activité de la base (genre nombre de requêtes balancées dans la dernière heure, nb de personnes actuellement connectées...)  
On a avec ça l'utilisation actuelle de la base. Utile à admin, pas à user

## Instance et stockage physique

On travaille en mémoire (instance) mais on stocke sur disque (data storage)  
=> Le boulot d'Oracle est justement de gérer le passage de l'un à l'autre.

### Stockages physiques

Plusieurs types de fichiers : on note les data à l'intérieur  

- Data files (.dbf)   
  Lié aux tablespace  
  Contient les données

- Control files (.ctl) : qui où quoi comment ?  
  Fichiers de configuration de la base  
  Fichiers de contrôle d'intégrité au lancement

- Online redo Log  
  Historique des modifications effectuées  
  Journal des transactions

### SP - où sont stockés les fichiers ?

Oracle c'est limite un OS.  
Oracle ASM : il devient un Logical Volume Manager, on donne des volumes à Oracle qui va les gérer, ça permet notamment de faire du raid logiciel, duplic....  

On peut aussi laisser l'OS (Unix/Linux) gérer

Dernière option : Cluser File System.  
Dans ce cas : Oracle RAC. Il émule un SGF partagé sur un réseau, qui permettra par exemple l'accès concurrent à un fichier sur le disque.  
Offre possibilité de redondance...

### Oracle ASM

C'est comme du LVM (techniquement: un LVM géré par Oracle)  
Automatic Storage Mode  
Permet de distribuer les données sur plusieurs volumes,  les fusionner, dupliquer...  
Ré-équilibrage automatique de la distribution entre les différents volumes

## Data file sous Oracle

Ne jamais perdre le control file.   

Tablespace = plusieurs datafiles : dedans plusieurs tables : dedans plusieurs index.  
Deux principaux types de données qu'on va trouver dans un tablespace

Quand on crée un data file on spécifie : 

* Tablespace associé
* Taille (initialisé par défaut à cette taille)
* Auto extent (que faire quand fichier ititial plein ?)  

## Control file sous Oracle

Ils sont à minima dupliqués. Il faut les mettre sur fichier distant.  
Ne jamais les paumer. Ils sont essentiels au bon fonctionnement d'Oracle. Spécifient ou trouver les autres fichiers. Liés à une base de données

Infos dans control file : 

* Nom et ID base de données
* Timestamp de la création de base
* Localisation des fichiers (Data, Redo...)
* Information sur les Tablespaces
* Information de backup RMAN (recov Manager)
* SCN des data files pour valider leur pertinence au démarrage.

### Online redo log

Conserve les traces des modifications sur la base, ce sont les journaux (d'où le log...)  
Une fois configurés, on y touche plus.  
Peuvent être archivés sur long terme : Archived Redo log

## Structure de l'instance

SGA (System Gobal Area)  
Pis dedans d'autres trucs

### Parameter file

Y a SPFILe et PFILE.  
En gros y a 30 paramètres obligatoires et basiques, et pis plein de trucs optionnels.  
Fichiers en .ora  

### UGA : User Global Area

Tous les paramètres qui permettent de gérer la vie de la session sur le serveur.  
Si serveurs partagés, en cluster ou autre, l'UGA doit être disponible partout  

### PGA  : Process Global Area

Buffer mémoire lié à un process et à un utilisateur. Zone de mémoire partagée permettant de récupérer paramètres de la requête, plus ou moins synchronisé avec SGA.

### SGA : System Gobal Area

Zone de travail principale d'Oracle  :

* une instance, un SGA  
* décomposée en plusieurs pools de mémoire : shared pool, large pool, java pool, stream pool...
