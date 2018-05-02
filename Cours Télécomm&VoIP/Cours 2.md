Cours 2
========================

(On DL VulnVoIP sur Vulnhub)

Quand on fiat une connexion entre deux téléphone, on a d'abord une connexion SIP  
puis une négo pour établissement RTP  
puis choix codecs

À chaque fois qu'un téléphoine reçoit un messgae init, il va initier un truc mais j'ai zappé quoi.


**DOS**  
quand message init (SIP) :  
-> syn  
-> synack  
=> pas de ack (on commence un truc qui termine pas en sorte)  
==> monopolise les ressources, bloqu le système  

Les flux RTP dsécurisés permettent de s prémunir du man in the middle.  
SIP fait circuler en clair, on peut donc encaspuler pour la sécurité (c'est ça ls fulx rtp sécurisés ?)  
Le Man in the middle est possible sur des connexions cablées via du sppof MAC  

## au niveau du serveur
...


# Install et pratique sur vulnVoip avec un kali linux

logs kali : root // toor

outils utiles : 
n map (zen map)  
=> check 

- du réseau 
- d'une machine

nmap -sV -os ..... IPcible/24  

armitage front-end sur metasploit  
=> "hail macy" (??)  

Configurer les exploits à utiliser  
RHost  R : remote (cible)  
LHost  L : Local (assaillant)



Fichiers sympa : 

- /etc/passwd
- /et/shadow

Pour casser mots de passe :

- Hydra 
- John the Ripper

Foncitonnent avec bases de mdp connues (rockyou.txt ???)

Pour rechercher arborescence sur petit serveur web ou autre : 

- dirb -> sur serveur web, fait des petits tests pour  voir ce qui est accessible

Pour scanner réseau : `netdiscover`  
Après avoir chopé l'ip de l'ordi cible, Guillaume sent le caca, on scane le sports ouverts :  
`nmap -sV IPcible`  
Je vais voir ensuite du côté du serveur web, puisqu'il y a un port 80 ouvert  
Y adeux liens, je scanne tout ce tintouin avec wapiti : `wapiti http://192.168.56.102:80/`  
wapiti ca marche pas, je tente John the ripper mais je comprend rien  
je tente ensuite hydra, j'arrive à jouer avec mais rien ne marche  
je désespère et abandonne  