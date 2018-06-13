Cours Sécurité des réseaux
========================

# Rappels sur OSI

On va travailer essentiellement sur le modèle OSI :   
**Couches logicielles** :  
7 Transport  
6 Présentation  
5 Session  

**Couche charnière** :  
4 Transport

**Couches matérielles** :  
3 Réseau  
2 Liaison  
1 Physique  

1. Physique, signal, des 0 et des 1
2. Trames ethernet suivnat la norme IEEE802.3  

| P+D | @mac dest | @mac src | Type | Data | CRC |
|---|---|---|---|---|---|
| 7+1 octets | 6 octets | 6 octets | 2 octets | Data | CRC |
|  |  |  | Code indiquant protocole qui va prendre la suite de l'opération | Datagramme IP : il devrait nous fournir le schéma (au pire ça se trouve sur le web) | CRC |

Le datagramme IP (codé sur 32 bits) comporte un important entêt composé de plusieurs parties.  Dans la DATA du datagramme IP on retrouve le segment TCP (codé sur 32 bits). Il a aussi un entête puis la DATA.  
3. C'est le datagramme IP  
4. TCP ou UDP, regarde port src et port dst

### Exercice
Consignes : voir ressources cours 1

1- Adresses mac :   
src : 00 80 C8 7A 0A D8  
dst : 00 D0 59 82 2B 86  
2- Entête datagramme :  
45 00 00 40  
8B 12 40 00  
40 06 57 17  
AC 10 00 64  = IP source : 172.16.0.100  
AC 10 00 0A  = IP dest : 172.16.0.10  
3 - Version : ipdv4 (premier octet du datagramme)  
4- Longueur d'entête : 5 (IHL : deuxième octet datagramme)
5- 5 * 4 octets : 20 octets 
6- 06 : TCP  
7- 0800  
8- Port source : 110E : 4341
Port destination : 0015 : 21  
9- 6+6+2 = 14 (on compte en général pas P+D)

## L'entête TCP

Établissement de la connexion : mode consistant à n'autoriser à entrer sur un réseau uniquement le traffic internet répondnat aux requêtes émises depuis le réseua local. Le routeur firewall se charge de bloquer/autoriser le traffic.  
C'est l'échange connu avec les flags en TCP pour établir une connexion :  
- SYN (avec un n° de séquence : codé sur 32 bits)  
- ACK-SYN (répond + démande synchro), (numéro d'acquittement = numéro de séquence+1, nouveau numéro de séquence)  
- ACK (numéro de séquence +1, numéro d'acquittement = nouveau numéro de séquence +1 )

Il faut donc que le paquet ait un numéro de séquence+1 pour entrer dans le réseau


### Exercice

Trames capturées par monituer réseau. Il a ajouté des éléments qui ne nous intéressent pas.

L22 : adresse mac source  
L26 : Type   
... On entre dans datagramme IP    
L42 : Protocole  
L46 et 47 : IP sources et destination   
L54 : 0 pour les 4 premiers bits puis 0010 indiquent la levée de drapeau (SYN)  


Autre trame :  
L 90 : addresses  
..  
L124 125 : LEs numéros d'acquittance et de séquence  

## La RFC1918

Request For Command  
Elle détermine pour l'IPv4 les adresses IP publiques et celles privées. Il ya un système de classes. Les privées :

| Classe | ip/masque | plage |
| --- |--- |--- |
| A | 10.0.0.0/8 | 10.0.0.1 à 10.255.255.255 |
| B | 172.16.0.0/12 | 172.16.0.1 à 172.31.255.255 |
| C | 192.168.0.0/16 | 192.168.0.1 à 192.168.255.255 |

Si y a des adresses privées, c'est donc qu'on a de la NAT pour pouvoir permettre de communiquer avec Internet.  
Attention, SNAT en Cisco = Static NAT, ic c'est Source NAT.  
Construction d'une table NAT/PAT. IlocaleP:port de base, IP:port de destination, IPpublique:port personnalisée, IP:port destination  
DNAT n'est pas Dymanic NAT comme en Cisco mais Destination NAT.

### Exercice (4)

1.1 Parce que c'est un réseau privé

2.1 Parce uqe le 80 est utilisé pis faut différentier autre serveur http  
2.2 Au lieu de laisser par défaut 80 ils vont sélectioner le 4500

3.1 
