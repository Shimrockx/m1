Éléments d'arithmétique
========================

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


La congruence est compatibl avec addition et multiplication dans Z. 

Si a congru à b(n), alors a^k congru à b^k(n)

Deux types d'arithmétique : la classique (dans R) et la modulaire (celle qu'on va utiliser)
Démonstrations sur papier

b)  1) Les deux méthodes expliquées sont **fondamentales**   
D'abord on utilise ce qu'on a vu : équivalence puissances, critère divisibilité par 11  

Puis **Exponentiation modulaire** à partir de 3^15 (11)  
L'objectif là dedans c'est d'arriver à tomber sur 1, là c'est la boucle qui redémarre. L'enjeu est de se poser la question : vais-je tomber sur 1 ? Et y a il un outil mathématique qui permet de calculer ça ? => on verra ça dans la suite du cours.


2 ) Tout nombre est congru à ses deux derniers chiffres modulo 100

## L'anneau machin : Z*n*

### Additions 

On va commencer à parler du Z*n* : on se base dans le modulo de *n*  dnas les entiers, ce sont des univers. On compte en modulo. Exmeple avc Z6 : 

| + | 1 | 2 | 3 | 4 | 5 |
| 1 | 2 | 3 | 4 | 5 | 0 |
| 2 | 3 | 4 | 5 | 0 | 1 |
| 3 | 4 | 5 | 0 | 1 | 2 |
| 4 | 5 | 0 | 1 | 2 | 3 |
| 5 | 0 | 1 | 2 | 3 | 4 |

Du coup l'opposé d'un chiffre est celui qui correspond au croisement avec 0 dans le tableau.  
La loi universelle qu'on ressort est : soit *n* un chiffre et *o* son opposé, dans l'univers *U*, o = U - n .

Voirs cours pour la suite/règles.

L'univers Z2 est le concept du OU exclusif : on a 0 si valeurs identiques, 1 si valeurs diffèrent.

### Multiplication

Voir cours. Il faudrait faire toutes les tabls de Z5, Z6, Z7, Z9, Z11  

Z6 à nouveau  :

| x | 1 | 2 | 3 | 4 | 5 |
| 1 | 1 | 2 | 3 | 4 | 5 |
| 2 | 2 | 4 | 0 | 2 | 4 |
| 3 | 3 | 0 | 3 | 0 | 3 |
| 4 | 4 | 2 | 0 | 4 | 2 |
| 5 | 5 | 4 | 3 | 2 | 1 |

Attention : on oublie le "si a * b = 0, a = 0 et/ou b = 0" est faux dans cet univers. (Ici 2 * 3=0)   
Si on prend 2, il a pas d'inverse (on cherche 2 * x = 1, ça n'existe pas dans cette table). En fait on a pas d'inverse à part 1 et n-1, c'est valable pour tous ls univers.  
Pour 2, 3, 4  y a pas d'inverse et c'est pas bijectif (il y a des répétitions, pas des valeurs uniques)

On se rend compte que ça "marche" partout pour chiffres premiers, mais que quand pas premier, les lignes des diviseurs et de leurs multiples sont foireux. Dans ces cas seules les lignes restantes auront des inverses et seront bijectives.


### Exercices

A) Les seuls éléments inversibles dans Z10 sont 1, 3, 7 et 9  
Donc Z10* = {1,3,7,9} (4 éléments)  
Z15* = {1,2,4,7,8,11,13,14} (8 éléments)  
Z12* = {1,5,7,11} (4 éléments)  
Z17* = {TOUS} (16 éléments)   



Prochain cour son va voir Bachel bézou >> à utiliser dans grands univers, dans petits autant faire la table.

Finir les exos b et c

