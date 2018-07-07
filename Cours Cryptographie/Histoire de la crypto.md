# Histoire de la crypto

Deux premiers cours : histoire de la crypto  
~~Calculatrice : on verra. Si oui, le mieux c'est la TI89~~  
~~Exam : environ 2h, en amphi. 3 exercices :~~  

- 1 sur théorème des restes chinois >> là pour attraper un max de points  / 4pts  
- 1 sur questions d'histoire  /  4pts  
- ~~Exercice de cryptage sur un système qu'on a jamais vu ensemble // 12pts~~  

On ne deviendra pas des experts en crypto juste avec ce module.  
 => Vision globale sur la cryptographie

RSA : cassable facilement, on a juste pas la puissance encore. On rallonge donc régulièrement la clé

## Lexique

**Cryptologie** : science des documents secrets

**Cryptanalyse** : art et science de décrypter les messages secrets

**Chiffrement** : processus de transformation d'un message en clair de façon à le rendre incomprehensible par toute personne non autorisée

**Cryptogramme** : résultat du processus de chiffrement

**Déchiffrement** : processus de reconstruction par une personne autorisée (avec clé)

**Décryptage** : processus de reconstruction par une personne non autorisée (sans clé)

**Clef de déchiffrement** : tout algorithme qui permet de chiffer ou déchiffrer un message

**Sténographie** :  dissimulation d'un message dans un ensemble de données d'apparence anodine

## Chronologie

**Polybe** - César - **Al Kindi** (900/1000) - **Vigenère**

Globalement : antiquité / orient / renaissance

Grandes étapes :  
Préhistoire  
Antiquité  
Moyen-Age (ça explose au Moyen Orient, en Chine et en Inde pendant ce temps)  
1492 (Christophe Colomb)  
Renaissance
1789  
Temps modernes  
1914  
Contemporaine  

*Il est exigant sur la chronologie, attention ! On doit être capable de faire une demi page sur chaque gars à la fin.*

## Les différentes stratégies

Cacher - Coder - Crypter

### Cacher

#### Steganographie

 Cacher le message dans un support qui semble anodin.

- noyer le message dans un autre
- écrire sur crâne et attendre que cheveux repousse (Histiée - Antiquité)
- écrire sur tablette en bois et recouvrir de cire pour faire croire à tablette vierge (Démarate - Antiquité)
- message sur fine soie enrobée dans cire, puis messager avale boule (Chine)
- message dans un oeuf dur : de l'alun avec beaucoup de vinaigre pénètre la surface et s'inscrit sur le blanc (Porta - XVIe)
- petits trous sous les lettres d'un texte, qui si on en prend que ces lettres donnent le message (Énée)
- micropoints : les allemands utilisaient ça dans la seconde guerre mondiale : taille d'un point de ponctuation, qu'il faut agrandir pour lire le message dedans.

Le micropoint est très utilisé aujourd'hui : billets de banque, chèques...

Intégration dans les gènes ! Création d'une clé d'encryption en créant un alphabet à partir de séquences de 3 lettres.  
On part un peu loin avec la modification génétique

Eugénisme : exemple Norvège qui veut faire race supérieure : 1860 à 1940 d'abord via des allocs pour grands blonds yeux bleux qui font enfants mais taxes pour les autres, puis interdiciton aux couples pas gbyb de faire des gosses, puis stériilisations des femmes qui n'ont pas les gènes gbyb.  

#### Encres sympathiques

Rabelais : médecin habitant de Lyon, officiait à l'hôtel Dieu. Romans très bons : Pantagruel.  
Wikileaks de l'époque : il balançait infos sensées rester secrètes.  
Dans Pantagruel il explique toutes les techniques pour cacher un message au moyen d'encres sympatiques :

- sel ammoniaque dans l'eau : près du feu
- suc de tithymalle  : dans l'eau
- jus oignon blanc : montrer à la chandelle
- extrait figuier : huile de noix
- ...

#### Grille de Cardan

Faire fenêtres dans un cache et placer ce cache sur un texte pour faire apparaitre le message à travers les fenêtres

#### Ave Maria de Tritheme

Chaque bout de phrase correspond à une lettre, et on construit un texte à partir de ces phrases. Un poil répétitif comme texte.

Tritheme était un abbé, il a donc écrit plein de formules qui peuvent coller et former ainsi un "Ave Maria" qui sera le message caché.

#### L'alphabet bilitère de Francis **Bacon** (**1561-1626**)

Joue avec l'imprimerie : les lettres sont normale ou en italique. Partant de là, une sorte de concept binaire s'applique : si normal : A, si italique : B (genre 0 et 1). Par groupe de 5 lettres, on retrouve donc la lettre selon un agencement particulier défini dans un tableau (genre AA AAA = A, AA AAB = B ...)
Problème : longueur du message (5 caractères pour 1 lettre) et différence de typo dure à voir

Ensuite évolution vers le trilitère (alphabet trifide) : normal, italique et taille de police supérieure. Via **Cardan** (**1557**)
Problème : déjà dur à distinguer à 2, hardore avec 3.
Jamais vraiment utilisé.

#### Sémagrammes

Le principe est de cacher le mesage via des éléments différents de chiffres ou de lettres via des dessins, images, schémas...

Utilisation des notes de musique : du do au la, pour blanche, noire, croche... : 39 possibilités = alphabet, 10 chiffres, ponctuation  
Dans un dessin, mettre des éléments codés (herbes longues ou courtes, mouches dont l'emplacement correspond à une lettre d'alphabet...)  

#### Lettres codés de Sand et de Musset

Lire une ligne sur deux // Acrostiche (pas de lettre, de mot)

#### Le "soi disant" code secret de la bible

Michael Drosnin a collé toutes les lettres de la Bible et fait des sauts entre les lettre pour capter des "messages secrets" 

On sait graĉe au Théorème de Borel que ça ne vauit pas grand chose : avec un grand nombre de lettres, on peut en effet faire plein de mots.

### Coder

#### Le code de Mary Stuart (1586)

Remplace lettres et certains mots par signes, avec des signes ne voulant rien dire.

Elle pensait que son code était solide mais elle s'est fait capter. Elle montait complot pour renverser Elisabeth reine d'Angleterr. Les cryptanalystes ont réussi à décoder et inséraient des faux Post scriptum dans les lettres pour récupérer les infos et démanteler le réseau.

#### Le code de Popham (1806)

Code avec des drapeaux pour communiquer à distance entre bateaux. 

Sémaphore : les deux drapeaux avec rouge/jaune en diago

Puis en 1806 signaux correspondant à mots, expressions et phrases entières (3000 signaux), amélioré par la suite  pour atteindre 30 000 mots.

#### Le morse

Bien connu. Pensé pour que les lettres les plus utilisées soient symboles courts  
Les caractères souvent utilisés sont généralement très courts. Ceux moins utilisés sont plus longs.

#### L'ASCII

...

#### Le code Navajo

Une langue indigène (indienne) très complexe. Ils ont utilisé cette langue (un millier d'utilisateurs au monde tout au plus). Cétait donc codé, et si le message était intercepté la langue était impossible à comprendre.
Difficulté : les mots de la langue sont pas adaptés au langage militaire, donc ils ont du trouver des équivalents.  
Fallait aussi pas qu'un Navajo trombe aux mains de l'ennemi.

### Crypter

#### Approche 01  : Le chiffre de transposition

L'idée est de construire des anagrammes. Peu efficace sur messages courts, mais dès que la longueur augmente il y a plus de possiblités, limitées par la clé indiquant les permutations.

On change l'ordre des lettres selon une clé indiquant comment on permute sur un lot de n lettres. (genre 4 lettres qu'on change en 2, 4, 1, 3)  
Ça a été utilisé par Galilée notamment, pour protéger ses recherches : il avait publié le truc en crypté pour prouver qu'il était le premier à avoir trouvé qqch.

##### Lecture globale

En lecture globale on peut trouver facielment (en bloquant la première et la dernière et on change l'ordre lettres dans le mot)

##### Scytale romaine - Ve avant J.C.

Bâton sur lequel on enroule un ruban et on écrit dessus, puis on déroule et complète les trous avec d'autres lettres. Il faut ensuite un bâton du bon diamètre pour pouvoir déchiffrer.

##### Rail Fence

Séparation du message en deux niveaux, une lettre dans chaque dans l'ordre.  Puis on écrit les deux lignes à la suite l'une de l'autre
On peut même le faire en trois niveaux ou plus

##### La grille tournante

Il s'agit d'une grille avec un cache devant qui, lorsqu'on le tourne, laisse aparraitre des cases différentes. On écrit alors le message en remplissant la grille à travers le cache et en le tournant d'un quart de tour à chaque fois. On a ensuit une grille remplie (compléter éventuellement les trous) que l'on peu transmettre. Pour déchiffrer, mettre le cache et tourner d'un quart de tour.

---

*Cours 2 : 23/05/2018*

##### Transposition rectangulaire

On ecrit le message en grille, et on change l'ordre des colonnes (par exemple en utilisant un mot clef aux lettres numérotées), ce qui mélange la grille. On forme ensuite le texte chiffré en lisant la grille mélangée.  
Il faut par contre pouvoir transmettre le mot clef et savoir comment lire les lignes

Comment renforcer ce système (un peu léger de base) ?  Faire deux transpositions : chiffre à double transposition.  
On peut aussi transposer d'abord les colonnes, puis les lignes, mais ça change rien vraiment : il faudrait plutôt avoir deux chiffres différents.

#### Approche 02 : chiffre de sustitution

Consiste à remplacer lettres ou mots par autres symboles.  
4 grandes familes :

* **Monoalphabétique**: 1 lettre = une lettre
* **Polyalphabétique** : 1 lettre  =deux lettres
* **Polygrammique** : 2 lettres  = une lettre
* **Tommogrammique** : 2 lettres = plusieurs lettres

##### Monoalphabétiques

###### Polybe (Carré de polybe) - 200/125 av. J.C.

Fonctionne avec des coordonnées pour les lettres dens un carré de 5x5 (25 cases, on vire une lettre genre W en français). On peut agrandir à 6x6 = 36 pour y insérer les chiffres.  
Pour chiffrer, on utilise les chiffres obtenus via les coordonnées des lettres dans le tableau.

Pour sécuriser un peu plus le truc, on peut faire un carré de Polybe  en désorganisant l'alphabet à l'intérieur. Par exemple, avec un mot clef : on commence par l'écrire (sans lettres qui se répètent) puis on met les lettres restantes de l'alphabet dans l'ordre.

###### Georges Perec

Auteur de "La disparition", et de "Les revenentes" (que avec la voyelle e). Il a aussi fait un grand palindrome.  

###### L'alphabet désordonné

Changer l'ordre de l'alphabet :

* De façon désordonnée, un peu dur à retenir
* Avec d'abord un mot-clef puis reste de l'aphabet dans l'ordre
* Chiffre de César : on décale les lettres de x (mais que 25 décalages)
* Alphabet hébraique : **Atbash**, on inverse l'ordre des lettres de l'alphabet; **Albam**, lettres décalées de 13 position (2 décalages = alphabet originel); **Atbah** les chiffres sont réversibles : A=i et i=A, b=h et h=b.., que 13 tandems à apprendre.

( Les romains étaient bons en guerre, en ingénierie et en administrations, mais très mauvais scientifiques. Bons scientifiques chez les grecs : Archimède, buté par un romain connement 

###### Pig pen & templiers

Associe des symboles aux lettres : Pig pen a été utilisé très longtemps, notamment par les pirates !  
-> Wikipedia  

Croix de malte des templiers

###### Décrypter un chiffre monoalphabétique : analyse de fréquence

Comment décrypter un texte utilisant chiffre de substitution ? Pendant mille ans on a galéré, jusqu'à l'invention de l'anaylse de fréquences.

**<u>Al-kindi</u> est l'inventeur de l'analyse de fréquences, au IXe siècle**

L'idée est de se baser sur la fréquence d'apparition des lettres.  
Lettres les plus fréquentes en Français : easint...  
Il y a des diagrammes pour toutes les langues. Les 4 européennes principales sont assez similaires.  
<u>Pour l'analyse de fréquence, il faut des messages relativement longs (ou plusieurs messages courts avec la même clef).</u>

Il est également possible d'analyser non pas les lettres mais les bigrammes voire les trigrammes, classés également pas fréquences dans les langues.

###### Décrypter un chiffre monoalphabétique : attaque par mot probable

Know Plaintext Attack en anglais. L'idée est de rechercher une fraction du message clair supposé pour établir une correspondance et trouver la clé. 

###### Substitution homophonique

Pour échapper à l'analyse de fréquence, on peut définir plusieurs symboles pour une même lettre : 

* chiffre de Sully, 
* chiffre de 15...
* disque de l'armée mexicaine
* moyenne de fréquences d'apparition pour donner autant de symbols que nécessaire à chauqe lettre pour "lisser" courbe, sacré progrès.
* tableau de coordonnées avec lettres

Le chiffrement monoalphabétique est un peu gênant à cause de l'analyse de fréquences. On a tenté de s'en dépatouiller avec la substitution homophonique. On appelle ça le **renversement des fréquences**.

Pour retenir les mots-clef des deux derniers exemples (trop compliqués à retenir comme ça), on s'entend sur un livre différent par jour, chaque jour on tourne une page et on prend mettons les premiers mots de 5 lettres de la page. C'est le **chiffre du livre**

##### Polyalphabétiques

###### Chiffre de Porta - 1563

Le premier à inventer un système littéral à double clef, c'est à dire pour lequel on change d'alphabet à chaque fois. Utilisé avec succès pendant 3 siècles (via Vigenère ?). Considéré par certains comme le père de la cryptologie moderne.

11 alphabets différents (pouvant être étendus à 13) tous réversibles (a=x, x=a), chaque alphabet correspond à deux lettres de l'alphabet, on décide d'un mot-clef qui indique quels alphabets on va utiliser pour chaque lettre.

###### Chiffre de Vigenère - 1586

Histoire de pas se faire chier la bite, le gars a fait 26 alphabets : déploiement de l'idée de porta qui les regroupait. C'est bien plus sécurisé ! Sauf la ligne A  qui n'est pas décalée. Le décalage 0 est bof en matière de crypto.  
Le chiffre de vigenère est méga efficace ! Pendant 300 ans les gens ont pus rien fait après, c'était suffisant.  
Le carré de Vigenère reste bien relou à utiliser. On utilise ensuite donc plutôt une réglette, en alignant la lettre du mot clef sur le A de l'alphabet. On obtient ensuite notre correspondance.

Si on regarde de près, c'est un système de chiffre de César mais décalé à chaque lettre. On sait aujourd'hui le casser, de plusieurs façons.  

Variantes : 

* Chiffre de Beaufort : au lieu d'ajouter la clef, il la soustrait.

* Chiffre de Gronsfield : remplace mot clef par chiffre clef > réduit les 26 possibilités à 9.

* _Masque jetable_ : **méthode INCASSABLE**. Seul algo de cryptage indécryptable. C'est un chiffre de Vigenère dont la clef de chiffrement est égale à la longueur du message. Il faut pour ça :
  * choisir une clef aussi longue
  * utiliser une clef formée de caractères aléatoires
  * protéger la clef
  * jamais réutiliser la clef
  * écrire textes clairs ne contenant que des lettres (pas de ponctuation ou espace)  

  Clés transmises via valise diplomatique !

* Cylindre de Jefferson (1743-1826) : plusieurs disques avec alphabet. C'est un Vignère automatisé

###### Casser Vigenère : Méthode de Bazeries

On prend un mot supposé être dans le message et on teste en décalant d'une lettre à chaque fois en déduisant ce qui doit etre le mot clef. On part du postulat que la clef est un mot existant.  
Basé sur idée de répétition de la clef étant un mot.

###### Casser Vigenère : Méthode de Babbage et Kasiski

Babbage a réussi à casser Vigenère en 1854 mais personne n'en a jamais rien su. C'est Kasiski qui, en 1863, a publié la même méthode.

Basée sur la recherche des redondances dans le message. Ces redondances vont donner une indication sur la taille de la clef. On peut avec la taille, revenir sur une méthode monoalphabétique.   
Besoin d'un message plutôt long pour réussir. On reporte les redondances en comptant les possibilités, puis on compare entre toutes les redondances pour trouver la longueur qui colle à toutes.  
À partir de ça, on fait une analyse de fréquences pour chaque décalage de la clef. 

---

*25/05/18*

###### Casser Vigenère : méthode de William Friedman (1891 - 1969)

Il a inventé le concept de l'**indice de coincidence** pour chaque langage, permettant de savoir quelle est la probabilité que deux lettres prises au hasard soient identiques et utilise cet indice pour savoir si le texte crypté est monoalphabétique ou non (si l'indice correspond à celui de la langue c'est le cas). 

Ça permet aussi de connaitre la longueur de la clef :   
Pour trouver longueur de la clef, on tente avec diverses longueurs de clefs, à partir de 1, et on refait l'indice en prenant une lettre sur n (du coup 1 sur n, n étant la longueur de la clef, on tombe sur un truc monoalphabétique), si on obtient un indice proche de l'indice du monoalphabétique (0,07), c'est gagné : on a la longueur de la clef.

Fonctionne bien avec mots-clefs pas trop longs sur texte long. 

###### Au delà de Vigenère : la machine allemande Enigma

Utilisé par le système allemand depuis le début des années 30. On a pu le casser à la guerre car des polonais l'avaient cassé avant. Ils ont ensuite changé la machine et on en a chié.

Basée sur des rotors qui tournent, y a en plus des brouilleurs, et pis le tableau de connexion (sorte de clef pour configurer la machine). Au début 3 rotors puis on est passé à 4 ou 5, dans la marine notamment (qui souhaitait un chiffrage plus fort). Donne une substituation polyalphabétique avec une longueur de clé gigantesque.

Le code est symétrique (grâce au réflecteur), pour décrypter il suffit de positionner correctement tout le bouzin et de taper le message crypté.

###### Au delà d'Enigma : Bletchley Park

Ils ont réussi à casser Enigma, équipe de 7000 personnes, fabrication de machines appelées bombes (en référence à celles déjà conçues par les polonais), équipe de choc dirigée par **Alan Turing**. Résolu par attaque de mots probables et bombes. 

Mais une fois le chiffre cassé, la question demeure : faut il le cacher à l'ennemi ?

##### Tomogrammiques

###### Auguste Collon (env. 1900)

Son truc c'est les systèmes à damiers. Son, plus simple utilise des coordonnées (deux lettres) pour chaque lettre : on met l'alphabet dans un carré de 5x5 (genre Polybe sans les chiffres pour coordonnées) et on utilise première lettre de la colonne et la ligne pour indiquer la lettre en clair. Ces coordonnées sont mises sur deux lignes, et on détermine une "clé" indiquant la longueur de blocs découpant chaque ligne. On alterne ensuite un bloc de chaque ligne pour obtenir le texte chiffré.

Pour décrypter, commencer par trouver longueur des blocs. (Comment ? on doit trouver au max 25 bigrammes, nombre max du damier, faut donc tester)  
Une fois qu'on a la longueur de bloc, on peut repérer les bigrammes fréquents, lancer une analyse de fréquence.  
Une fois analyse fréquence faite, on a genre au moins le e. Faut ensuite fonctionner par mot probable pour trouver les lettres correspondant aux autres bigrammes.

###### Chiffre Bifide de Delastelle (1840 - 1902)

Basé sur chiffre de Polybe, mais en mode chiadé : on décide d'une longueur de bloc n (clé), puis on chiffre le message avec les coordonnées du carré de Polybe sur deux lignes. On prend ensuite un bloc par ligne, on les met à la suite et on obtient de nouvelles coordonnées qui donnent le message chiffré.

###### Chiffre digraphide

Se base sur deux grilles alphabétiques avec une "clef" entre les deux, donc trois tableaux. Bien bien chiadé à décrypter, bien bien chiadé à chiffrer.

Le chiffrement se fait par bigrammes, et par trois bigrammes : 

- Grace aux coordonnées des grilles on obtient trois chiffres par bigramme (grille 1, clé, grille 2), qu'on note sur trois lignes
- On lit chaque ligne pour récupérer un nouveau chiffre de 3 nombres.
- On génère trois nouveaux bigrammes à partir de ces trois chiffres.

###### Chiffre ADFGVX

Inspiré carré Polybe aussi. Envoie les coordonnées en morse, c'est plus simple car pas d'alpabet morse entier à retenir. Plutôt que chiffres, on utilise 5 lettres très distinctes en morse : ADFGVX.On peut ainsi coder 36 lettres en n'en connaissant que 6 en morse. Le texte obtenu était ensuite placé dans un carré dont on permutait les colonnes grâce à un mot-clef (transposition rectangulaire).

Créé par l'Allemand **Fritz Nebel**

##### Polygrammiques

###### Chiffre PlayFair

Carré de 25 lettres, mélangées ce qui forme la clef. Chiffré par groupes de deux lettres en applicant trois règles, on fonction de l'empacement des deux lettres 

- ligne & colonne différentes : les utiliser comme coordonnées
- même ligne : lettre directement à droite
- même colonne : lettre directement en dessous

Pour le casser, on fait une analyse de fréquence des bigrammes et on tente de constituer la grille à partir de ces derniers

###### Chiffre SlideFaire

PlayFair en Vigenère.  
Il faut un mot-clef (pour le vigenère). En se basant sur la lettre du mot clef on récupère par binome de lettre : point 1 : sans décalage, point 2 : dans ligne décalée correspondant à lettre du mot clef. On utilise les même règles que PlayFair pour déduire le texte chiffré.

Cassable avec indice de coincidence, non plus pour 26 lettres, mais sur 650 bigrammes.

###### À deux carrés

On prend le playfair mais on prend deux grilles (en polybe), et on fait figure géométrique sur deux grilles.

Pas facile à casser. 

###### A trois carrés

Bon, évolution du délire de deux carrés, mais là en plus on peut faire des trigrammes.  
Ultra simple à utiliser ! Par binome de lettre on chope la lettre au croisement des deux grilles, pis on indique la ligne/colonne auquel ça correspond par n'importe quelle lettre présente dans la ligne/colonne.

Si on veut casser, on peut tenter d'identifier la lettre centrale. Mais c'est bien chaud.

###### Chiffre affine (intro chiffre de Hill)

On a besoin pour ça de deux outils modernes : arithmétique modulaire et fonction affine. 

Division euclidienne : on retrouve modulo  
Le modulo 26 permet de savoir de combien on décale (il rentre x alphabet dedans pis on décale du reste)

Chiffrement affine : y = a x + b  
a et b sont des constantes et constituent la clef.  

*possible d'en savoir plus en regardant le programme du BTS SIO*

###### Chiffre de Hill

Attention : calculatrice calcule dans R, on calcule dans Z (entier relatif) >> elle va donner résultats faux.  
Calcul de matrice >> à revoir

Pour déchiffrer, on peut pas faire de division de matrice. Heureusement il existe des matrices inverse !  

Voir notes manuscrites pour formules math.

#### La cryptographie moderne

Dès qu'on parle de moderne, c'est avant/après arrivée ordinateur

On va voir 3 grandes parties : 

* Les systèmes à clefs - clefs privées
* Les systèmes à clefs - clefs publiques
* Le chiffrement par blocs

###### Le chiffrement par blocs

On prend un bloc (mettons 4 bits), on le sépare en deux, on prend la partie de droite qu'on passe à gauche, on passe cette même partie dans une fonction clef puis on l'additionne en XOR à la partie gauche, on met le résultat à droite. On recommence ensuite l'opération et on ressort les deux parties collées. À chaque itération on peut utiliser une fonction différente, ou la même (mieux de changer).

Sur 4 bits dans l'exemple du cours, ça donne un **réseau de Feistel**.

###### Clefs publiques

Technique permettant de garder ses clefs si on cadenasse un truc et l'envoie à quelqu'un d'autre : Deux cadenas, un chez chacun. On envoie message sous cadenas, celui qui le reçoit cadenasse lui aussi et renvoie. Quand on le reçoit à nouveau on déverrouille et renvoie à la cible, qui à la réception déverrouille avec sa propre clef.  
Problème : quand on chiffre, et qu'on rechiffre par dessus, il n'est pas possible de déchiffrer ce qui a été rechiffré avant de renvoyer  
La solution à ceci est la commutativité des puissances :  (10^2)^3 = (10^3)^2. Donc si on chiffre avec des puissances, on pourra inverser les "couches" pour déchiffrer la couche intérieure.  
Comme c'est compliqué de travailler avec des très grand nombres, on utilise le modulo pour réduire ça et calculer

###### RSA

1978 - Rivest, Shamir, Adleman  
Explication bien chiadée mais bien fichue. On transmet deux nombres trouvés à partir de deux tenus secrets. On chiffre à partir des nombres transmis, et il est possible de déchiffrer uniquement grace aux nombres tenus secrets.

Il est possible de trouver les nombres secrets en factorisant un élément de la clé publique. Actuellement, si le nombre est très grand, ça prend trop de temps pour être réalisable.

###### L'avenir

Il existe aussi DES c'est peut être l'avenir. Ou la crypto quantique. 

* Courbe elliptique : les matheux ont pas de théorie la dessus, c'est des graphiques avec surcouche de chiffrement... on connait pas bien la théorie donc on peut coder dessus
* Crypto quantique: on sait pas faire mais on a la théorie !

### Récapitulatif

Bon à revoir >> base intéressante pour lui pour monter ses questions. C'est une genre de foire aux mots clef. 
