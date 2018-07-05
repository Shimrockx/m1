Éléments d'arithmétique
===

## Introdution

Cours d'outils pour la crypto, ne pas chercher à fair eun lien avec crypto, ça viendra après

Rappels :  Ensembles (du premier au dernier, l'un appartient au suivant)  
N => Naturels  
Z => Entiers  
D => Décimal  
Q => Rationnel  
R => Réels  
C => Complexes  
Q => Quaternion

On va travailler avec des Entiers avec deux opérations : l'addition et la multiplication (pas de division, sauf Euclidienne)  
Pour dire qu'un nombre en divise un autre : n|a (n divise a)

E à l'envers = il existe  
! = unique

## La division euclidienne

### Divisibilité dans N

| est symbole de la relation de divisibilité. C'est une relation d'ordre partiel : quand on bosse avec les congruances des nombres, elles ne conservent pas leur ordre (exmple de 12 et 10 congruant 3).

### Définition

Globalement, on se fout de ce qui n'est pas l reste dans division euclidienne (le chiffre en dessous du diviseur)

Gauss, petit génie, a repris la théorie d'euclide, et a vu la théorie des horloges dedans : une division euclidienne consiste à compter avec une horloge avec comme nombre d'heures le divisuer et voir la nombre de tour du cadran qui rentre et prendre le reste.

Critères de divisilibité (nomre est-il divisible par ?)  
Ls connaitre (de tête) :  
2 : Si pair
3 : Si sommes des chiffres divisibles par 3   
4 : Deux derniers chiffres doivent être divisibles par 4  
5 : finit par 0 ou 5  
6  : Nombre pair avec somme des chiffres divisibles par 3  
8  : Trois derniers chiffres divisibles par 8  
9  : si somme des chiffres divisible par 9  
10 : finit par 0  
11 : Somme des rangs pairs moins somme des rangs impairs doit être divisible par 11  
25 : Deux derniers chiffres divisibles par 25 ( 00, 25, 50, 75)  

Le troisième soutra indien
il faut faire les calculs Verticalement et en diagonale  
|X|

La congruence est compatible avec addition et multiplication dans Z.

Si a congru à b(n), alors a^k congru à b^k(n)

Deux types d'arithmétique : la classique (dans R) et la modulaire (celle qu'on va utiliser)
Démonstrations sur papier

b)  1) Les deux méthodes expliquées sont **fondamentales**   
D'abord on utilise ce qu'on a vu : équivalence puissances, critère divisibilité par 11  

Puis **Exponentiation modulaire** à partir de 3^15 (11)  
L'objectif là dedans c'est d'arriver à tomber sur 1, là c'est la boucle qui redémarre. L'enjeu est de se poser la question : vais-je tomber sur 1 ? Et y a il un outil mathématique qui permet de calculer ça ? => on verra ça dans la suite du cours.

2 ) Tout nombre est congru à ses deux derniers chiffres modulo 100

## L'anneau des entiers : Z*n*

### Additions

On va commencer à parler du Z*n* : on se base dans le modulo de *n*  dans les entiers, ce sont des univers. On compte en modulo. Exemple avec Z6 :

| +   | 1   | 2   | 3   | 4   | 5   |
| --- | --- | --- | --- | --- | --- |
| 1   | 2   | 3   | 4   | 5   | 0   |
| 2   | 3   | 4   | 5   | 0   | 1   |
| 3   | 4   | 5   | 0   | 1   | 2   |
| 4   | 5   | 0   | 1   | 2   | 3   |
| 5   | 0   | 1   | 2   | 3   | 4   |

Du coup l'opposé d'un chiffre est celui qui correspond au croisement avec 0 dans le tableau.

La loi universelle qu'on ressort est : soit *n* un chiffre et *o* son opposé, dans l'univers *U*, o = U - n .

Voirs cours pour la suite/règles.

L'univers Z2 est le concept du OU exclusif : on a 0 si valeurs identiques, 1 si valeurs diffèrent.

### Multiplication

Voir cours. Il faudrait faire toutes les tables de Z5, Z6, Z7, Z9, Z11  

Z6 à nouveau  :

| $$\times$$ | 1   | 2   | 3   | 4   | 5   |
| ---------- | --- | --- | --- | --- | --- |
| 1          | 1   | 2   | 3   | 4   | 5   |
| 2          | 2   | 4   | 0   | 2   | 4   |
| 3          | 3   | 0   | 3   | 0   | 3   |
| 4          | 4   | 2   | 0   | 4   | 2   |
| 5          | 5   | 4   | 3   | 2   | 1   |

Attention : on oublie le "si a * b = 0, a = 0 et/ou b = 0" : c'est faux dans cet univers. (Ici 2 * 3=0)   
Si on prend 2, il a pas d'inverse (on cherche 2 * x = 1, ça n'existe pas dans cette table). En fait on a pas d'inverse à part 1 et n-1, c'est valable pour tous ls univers.  
Pour 2, 3, 4  y a pas d'inverse et c'est pas bijectif (il y a des répétitions, pas des valeurs uniques)

On se rend compte que ça "marche" partout pour chiffres premiers, mais que quand pas premier, les lignes des diviseurs et de leurs multiples sont foireux. Dans ces cas seules les lignes restantes auront des inverses et seront bijectives.

### Exercices

A) Les seuls éléments inversibles dans Z10 sont 1, 3, 7 et 9  
Donc Z10* = {1,3,7,9} (4 éléments)  
Z15* = {1,2,4,7,8,11,13,14} (8 éléments)  
Z12* = {1,5,7,11} (4 éléments)  
Z17* = {TOUS} (16 éléments)   

Prochain cour son va voir Bachet bézout >> à utiliser dans grands univers, dans petits autant faire la table.

b -
x = 7 (9)  
insolvable (9)
x = {0;3;6} (9)
x = 5

c - 247^349 : Faire division euclidienne pour reste, puis exponentiation modulaire, et on calcule à partir de 247³48+1

## Nombres premiers, pgcd et ppcm

### Nb prmiers

On va redéfinir pgcd et ppcm à partir algorithme Euclide.

L'ensemble des nombres premiers est infini. Démonstration faite par Euclide.  
on se le démontre par l'absurde : on part du principe que ce nombre est fini et comme ça se contredit, c'est donc que c'est infini.  
On part donc de : l'ensemble des nombres premier est fini : {2, ..., n}  
La factorielle = multiplication de tous ls nombrs jusqu'à n. Factorielle de n = n!  
n! est donc divisible par tous les nombres. Mais n! + 1 n'est divisible que par lui même et 1. Or n! > n.

Tout nombre se décompose en produits de facteurs premiers.  
Pour les trouver, on cherche les nombres premiers qui le composent, se baser sur racine carrée approximative et tester tous les nombres premiers jusque là, puis recommencer avec ce qui reste jusqu'à ce qu'il soit premier.

Crible d'Ératostène : on met tous les nombre jusqu'à 100 dans un carré de 10*10 et on élimine tous les multiples de 2, puis de 3.... Ça permet de trouver les nombres premiers.  
C'est un sacré bibliothécaire et il a un peu calculé la circonférence de la terre, le gars.  

**Nombre de Mersenne**

Règle disant que 2^n-1 est premier si n est premier. Ça marche très bien au début, puis à 2¹¹ ça foire. On calcule donc ls nombres de Mersenne qui sont ceux premiers selon cette règle.

**Grands noms des travaux sur nombres premiers**

Legendre  
Hadamard  
Charles de La Vallee Poussin
Bernhard Riemann  

Plusieurs formules permettent de savoir si il y a un nombre permier dans un écart

### PGCD

on peut utiliser le chapeau ( ^ ) pour l'indiquer. Il y a une technique . Si PGCD est 1, les nombres sont étrangers.   
Pour trouver on décompose en nombre premier et on voit. Mais on va préférer l'algorithme d'euclide : on divise a par b et on note le reste. Puis b devient a et r devient b et on recommence jusqu'à trouver 0 ou 1

### PPCM

Noté a v b

a v b * a ^ b = ab; donc si a ^ b = 1, a v b = ab;

### Bachet Bezoud

**Ultra important : outil principal**

Dans Z,

Trouver PGCD 1800 ^ 1296  
=> 72.   
On en déduit que 1800 u * 1296 v = 72  

On va résoudre cette équation à deux inconnues, dans Z c'est possible pas comme dnas R

Démonstration sur feuille

donc on a au + bv = 1 si les nombres sont étrangers. À partir de ça, on se place dans un modulo pour "supprimer" une des parties.  
Modulo b :  bv congruent 0 dont au = 1  (b) donc u = a^-1 (b)
Modulo a : au congruent 0 donc bv =

Cette démonstration permet de :

- déterminer u et v dans une équation diophantiene
- trouver facilement les éléments inversibles !

### Indicatrice d'Euler

Z9* = {1,2,4,5,7,8} (6 éléments)  
Z15* = {1,2,4,7,8,11,13,14} (8 éléments)  
Z12* = {1,5,7,11} (4 éléments)  
Z13* = {TOUS} (12 éléments)  
Z17* = {TOUS} (16 éléments)   

=> Dans Z*p, il y a p-1 éléments inversibles  
=> Dans Z*n... on va utiliser la formule d'Eulère  
Elle permet de trouver nombre d'élémnts inversibles à partir de la factorisation d'un nombre.

On va relier ça à **Fermat :**

On note phi (n) le nombre d'éléments inversibles dans n

Définir Indicatrice d'Euler et justifier son utilisation dans un cryptosystème :

- ça sert à déterminer clef privée

- donne l'interface de bouclage

- nombre d'éléments inversibles dans modulo *n*

### Théorème d'Euler

il nous dit que si a^n, alors a^phi(n) congruent 1(n)

devient ensuite

### Petit théorème de Fermat

Dans un univers Z*p, n^p-1 congruent à 1 (p)

Dans un univers Z*n, la puissance correspond à l'indicatif d'Euler

### Théorème des restes chinois

On l'utilise pas le théorème chinois en tant que tel, on va utiliser son corollaire : théorème des restes chinois ou lemme chinois.

On a vu théorème avec un système de deux, maintenant on voit la règle générale (avec plus de conditions dans le système)

$$
\begin{cases}
x_1 \equiv a \pmod p \\
x_2 \equiv b \pmod q \\
x_3 \equiv c \pmod r 
\end{cases}
$$

On obtient

$$
x = a \times y_1 \times M_1 + b \times y_2 \times M_2 + a \times y_3 \times M_3 \pmod M
$$

Où

$$
M = p \times q \times r \\
M_i = \frac MM_i \\
y_1 = M_1^{-1} \pmod p
$$

### Exercices

Sur feuille

## Exam

On aura 6 questions :

Q1 : Éléments d'arithmétique - 2pts - Sera dur, le prof pense que beaucoup vont échouer, faire preuve de **logique**

Q2: Problème 1 - 6pts - C'est plutôt des maths

Q3: Histoire - 3pts - Des connaissances du cours

Q4: Éléments d'arithmétique - 3pts - Basé sur méthodologie (fortes chances pour restes chinois)

Q5: Problème 2 - 6pts - Basé sur la compréhension, faisable



Un exercice où il faudra trouver les éléments inversibles

## Algorithme de Diffie-Hellman

Protocole de génération de clé par canal public. Il ne s'agit pas d'un système de cryptage. 

Repose sur le principe :

$$
g^{a^b} = g^{ab} = g^{b^a}
$$

Il est décidé de deux nombres g et n transmis publiquement. De chaque côté, quelqu'un fait l'opération à partir de g modulo n avec un a ou b tenu secret et transmet le résultat r. Ensuite chacun élève ce résultat r à la puissance de son a ou b, modulo n et obtient la même clé de chaque côté.

## El-Gamal

Il s'agit ici non plus d'une simple transmission de clef, mais carrément d'un message chiffré, avec le concept de clé publique qui apparait. Assez proche de Diffie-Hellman dans l'idée, puisqu'on utilise encore une fois le délire des puissances et la transmission de chiffres publics, sauf que cette fois-ci l'expéditeur utilise le bouzin pour définir une clé, puis utilise cette clef pour chiffrer le message , et renvoie le tout.

Exercice sur feuille



## Équation ax + by = c où a et b premiers entre eux

Soit d le PGCD de a et B

Si d est un multiple de c, on peut trouver un ensemble de solution (au moins une), **sinon il n'y en a pas**






