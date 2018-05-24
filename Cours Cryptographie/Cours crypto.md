# Cours crypto

Deux premiers cours : histoire de la crypto  
Calculatrice : on verra. Si oui, le mieux c'est la TI89  
Exam : environ 2h, en amphi. 3 exercices :  
- 1 sur théorème des restes chinois >> là pour attraper un max de points  / 4pts  
- 1 sur questions d'histoire  /  4pts  
- Exercice de cryptage sur un système qu'on a jamais vu ensemble // 12pts  

On ne deviendra pas des experts en crypto juste avec ce module.  
 => Vision globale

RSA : cassabl facilemeent, on a just epas la puissance enciore. On rallonge donc régulièrement la clé

# Lexique

Cryptologie : science des documents secrets

cryptanalyse : art et science de décrypter messages secrets

chiffrement : processus de transformation d'un message en clair de façon à le rendre incomprehensible par toute personne non autorisée

cryptogramme : résultat du processus de chiffrement

déchiffrement : processus de reconstruction par personnes autorisées

décryptage : processus de reconstruction par perosnne non autorisée

clef de déchiffrement : tout algorithme qui permet de chiffr ou déchiffrer un message

sténographie :  dissimulation d'un message dans un ensemble de données d'apparence anodine

# Histoire

## Chronologie 

**Polype** - César - **Al Kindi** (900/1000) - **Vigenère**

Globalement : antiquité / orient / renaissance

Grandes étapes :  
Préhistoire  
Antiquité  
Moyen-Age (ça explose au Moyen Orient, en chine et en Inde pendant ce temps)  
1492 (Christophe Colomb)  
Renaissance
1789  
Temps modernes  
1914  
Contemporaine  

Il est exigant sur la chronologie, attention ! On doit être capable de faire une demi pag sur chaque gars à la fin.

## Différentes stratégies 

Cacher - coder - crypter

### Cacher

#### Steganographie
 cacher le message  dans un support qui semble anodin.
 
- noyer le message dans un autre
- écrire sur crâne et attendre que cheveux repousse
- écrire sur tablette en bois et recouvrir de cire pour faire croire à tablette vierge
- message sur fine soie enrobée dans cire, puis messager avale boule
- message dans un oeuf dur : de l'alun avec bcp de vinaigre pénètre la surface et s'inscrit sur le blanc
- petits trous sous les lettres d'un texte, qui si on en prend que ces lettres donnent le message
- micropoints : les allemands utilisaient ça dans la seconde guerre mondiale : taille d'un point de ponctuation, qu'il fuat agrandir pour lire le message dedans.

Le micropoint est très utilisé aujourd'hui : billets de banque, chèques...

Intégration dans les gènes ! Création d'une clé d'encryption en créant un allphabet à partir séquenc de 3 lettres.  
On part un peu loin avec modification génétique

Eugénisme : exemple Norvège qui veut faire race supérieure : 1860 à 1940 d'abord via des allocs pour grands blonds yeux bleux qui font enfants et taxe spour autres, puis interdiciton couples pas gbyb de faire gosses, puis stériilisations femmes qui ont pas gènes gbyb.  

#### Encres sympathiques

Rabelais : médecin habitant de Lyon, officiait à l'hotel Dieu. Romans très bons : Pantagruel.  
Wikileaks de l'époque : il balançait infos sensées rester secrètes.  
Dans pantagruel il expliques toutes techniques pour encres sympatiques :

- sel ammoniauqe dans l'eau : près du feu
- suc de tithymalle  : dans l'eau
- jus oignon blanc : montrer à la chandelle
- extrait figuier : huile de noix
- ...

#### Grille de Cardan

Faire fenetres dans un cache et placer cache sur un texte pour faire apparaitre message à travers fenetres

#### Ave Maria de Tritheme

Chaque bout de phrase correspond à une lettre, et on construit un texte à partir de ces phrases.

#### L'alphabet bilitère de Francis Bacon

joue avec iprimrie : normal ou en italique. si normal : A, si italique : B. Groupe de 5 lettres, et selon agencement donne un caractère (genre AAAAA = A)
Problème : longueur et différence de typo dure à voir

2volution vers le trilitère : normal, italique et plus grosse.
problèm : déjà dur à voir à 2, hardore avec 3.
Jamais utilisé vraiment

#### Semagrammes

utilisation des ntes de musique : du do au la, pour blanche, noire, croche... : 39 possibilités = alphabet, 10 chiffres, ponctuation  
dans un dessin, mettre éléments codés (herbes longues ou courtes, mouches dont emplacement correspond à lettre alphabet...)  

#### Lettres codés de Sand et de Musset

Lire une ligne sur deux // Acrostiche (pas de lettre, de mot)

#### Le "soi disant" code secret de la bible

le gars a collé toutes les lettres de la bible et fait des sauts entre les lettre pour capter des "messages secret"  
Théorème de Borel : avc un grand nombre de lettrs, on peut faire plein de mots.

### Coder 

#### Le code de Mary Stuart

elle pensait qu son code était solide mais elle s'est fait capter. elle montait complot pour renverser elisabeth reine. les cryptanalystes ont réussi à décoder et inséraient des faux Post scriptum dans les lettres pour récupérer infos et démanteler le réseau.

#### Le code de Popham

Code avec des drapeaux pour communiquer à distance entre bateaux. 
Sémaphore : les deux drapeaux avec rouge/jaune en diago

#### Le morse

bien connu. Pensé pour que les lettres les plus utilisées soient symboles courts  
Les caractères souvent utilisés sont généralement très courts. Ceux moins tuilisés sont plus longs.

#### L'ASCII

...

#### Le code Navajo 

Une langue indigène (indienne) très complexe. Ils ont utilisé cette langue (un millier d'utilisateurs au monde tout au plus). Cétait donc codé et si décodé en plus la langue était impossibl à comprendre.
difficulté : les mots de la langue sont pas adaptés donc ils trouvent des équivalents. Fallait aussi pas qu'un Navajo trombe aux mains de l'ennemi.

### Crypter

#### Approche 01  : Le chiffre de transposition

On change l'ordre des lettres selon un clé indiquant comment on permute sur un lot de n lettres. (genre 4 lettres qu'on change en 2, 4, 1, 3)  
Ca a été utilisé par Galilée notamment, pour protéger ses recherches : il avait publié le truc en crypté pour prouver qu'il était le premier à avoir trouvé qqch.

##### Lecture globale              

En lecture globale on peut trouver facielment (ne bloquant la première et la dernière et on change l'ordre lettres dnas mot)


##### Scytale romaine 

bâton sur lequel on enroule ruban et on écrit dessus, puis complète avec autres lettres, il faut ensuit baton du bon diamètre pour déchiffrer

##### Rail Fence

Séparation en deux du message en deux niveaux, une lettre dans chaque dans l'ordre.  
On peut faire en trois niveaux ou plus

##### La grille tournante

grille avec cache devant qui lorsqu'on le tourne laisse aparraitre des cases différentes. on écrit message en remplissant la grille à travers cache  et en le tournant d'un quart de tour à chaque fois. on a ensuit une grille remplie dont on transmet les lettres. Pour déchiffrer, remontrer la grille et mettre le cache.

*Cours 2 : 23/05/2018*

##### Transposition rectangulaire

on ecrit message en grille, et utilise un mot clef aux lettres numérotés pour changer ordre ds colonnes et donc mélanger la grille. On lit ensuite la grille dnas un certain ordre en format des mots de x lettre (taille de chaque ligne du tableau).  
Il faut par contre pouvoir transmettre le mot clef et savoir comment lire les lignes

Comment renforcer ce système (un peu léger de base) ?  Faire deux transpositions. On peut aussi transposer d'abord les colonnes, puis les lignes, mais ça change rien vraiment, il faudrait plutôt avoir deux chiffres différents.

#### Approche 02 : chiffre de sustitution 

Consiste à remplacer lettres ou mots par autres symboles.  
4 grandes familes :

* Monoalphabétiue: 1 lettre une lettre
* Polyalphabétique : 1 lettre deux lettres
* Polygrammique : 2 lettres une lettre
* Tommogrammiques : 2 lettre plusieurs lettres

##### Monoalphabetique

###### Polybe (Carré de polybe)

Fonctionne avec des coordonnées pour les lettres dnas un carré de 5x5 (25 cases).  
On peut agrandir à 6x6 = 36 poury insérer les chiffres

Pour sécuriser le truc, on peut faire un carré de Polybe  en désorganisant l'alphabet à l'intérieur. Par exemple, avec un mot clef : on commenc epar l'écrire puis on met les lettres restantes dans l'ordre.

###### Georges Perec

Auteur de "La disparition", et de "Les revenentes" (que avec la voyelle e). Il a aussi fait un grand palindrome.  


###### L'alphabet désordonné

Changer l'ordre de l'alphabet :

* Chiffre de César : on décale les lettre de x
* Alphabet hébraique : Atbash, on inverse ordre lettrs alphabet; albam, décalé de 13 position (2 décalages = originel); atbah les chiffres sont réversisble : A=i et i=A, b=h et h=b.., que 13 tandems à apprendre.

( Les romains étaient bons en guerre, en ingénierie et en administrations, mais très mauvais scientifiques. Bons scientifiques chez les grecs : Archimède, buté par un romain connement 

###### Pig pen & templiers

Associer des symboles aux lettres : Pig pen utilisé très longtemps, notamment par pirates !  
-> Wikipedia  
Croix de malte des templiers

###### Analyse de fréquence

Comment décrypter un texte utilisant chiffre de substitution ?

Al khindi

Se baser sur fréquence d'aparition des lettres.  
fréquence des lettres en Français : ea...  
Il y a des diagrammes pour toutes les langues. Les 4 europpéennes principales sont assez similaires.  
Pour analyse de fréquence, il faut des messages relativement longs (ou plusieurs messages courts avec la même clef).

###### Substitution homophonique
Pour échapper à l'analyse de fréquence, on peut définir plusieurs symboles pour une même lettre : 

* chiffre de Sully, 
* chiffre de 15...
* disque de l'armée mexicaine
* moyenne de fréquences d'apparition pour donner autant de symbols que nécessaire à chauqe lettre pour "lisser" courbe
* tableau de coordonnées avec lettres

Monoalphabétique est un peu gênant à cause analyse fréquence. On a tenté de s'en dépatouiller avec la substitution homophonique

##### Polyalphabétiques

pour  choisir les mots-clef, on s'netend sur un livre différent par jour, chaque jour on tourne une page, on prend mettons les premier mot de 5 lettres de la page.

###### Chiffre de Porta

Truc un peu chiadé avec des alphabets, un mot clef... en tout cas ça empêche l'analyse de fréquence. 13 alphabets en tout

###### Chiffre de Vigenere

Histoire de pas se faire chier la bite, le gars a fait 26 alphabets, pour ne pas regrouper. C'est bien plus sécu ! Sauf la ligne A  qui n'est pas décalée. Le décalage 0 est bof en matière de crypto.  
Le chiffre de vigenère est méga efficace ! Pendant 300 ans les gens ont pus rien fait après, c'était suffisant.  
Le carré de Vigenère reste bien relou à utiliser. On utilise ensuite donc plutôt une réglette, en alignat la lettre du mot clef sur le A de l'alphabet. On obtient ensuite notre correspondance.

Si on regarde de près, c'est un système de chiffre de César mais décalé à chaque lettre. On sait aujourd'hui le casser, de plusieurs façon (deux je crois).  

Variantes : 

* chiffre de Beaufort : au lieu d'ajouter la clef, il la soustrait.
* Chiffre de Gronsfield : remplace mot clef par chiffre clef > réduit les 26 possibilités à 9.
* _Masque jetable_ : **methode INCASSABLE**. Seul algo de cryptage indécryptable. C'est un chiffre de vigenère dont la clef de chiffrement est égale à la longueur du message. Il faut pour ça :
 * choisir une clef aussi longue
    * utiliser une clef formée de caractères aléatoires
    * protéger la clef
    * jamais réutiliser la clef
    * écrire textes clairs ne contenant que des lettres (pas de ponctuation ou espace)  
 -> Message transmis via valise diplomatique !
* Cylinre de Jefferson : plusieurs disques avec alpabet. C'est un Vignère automatisé

####### Casser Vigenère : Méthode de Bazeries

On prend un mot supposé être dans le message et on teste en décalant d'une lettre à chaque fois en déduisant ce qui doit etre le mot clef. On part du postulat que la clef est un mot existant.  
Basé sur idée de répétition de la clef étant un mot.

###### Casser Vigenère : Méthode de Babbage et Kasiski

Basé sur la recherche des redondances dans le message. Ces redondances vont donner une indication sur la taille de la clef. On peut avec la taille, revenir sur une méthode monoalphabétique   
Besoin d'un message plutôt long. On reporte les redondances en comptant les possibilité, puis on compare entre toutes les redondances pour trouver la longueur qui colle à toutes.  
À partir de ça, on fait des analyse de fréquence pour chaque déclaage de la clef. 