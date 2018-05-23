Cours 1
========================
*05/03/2018*

Différence entre VOIP et TOIP  
TOIP = couches basses OSI, donc VOIP spécialisée sur téléphone  
VOIP = couches hautes OSI  
  
Spec téléphone (standard, fixe) :  
48V  
Bande passante : Passe Hz entre 300 et 3400 (seuil audition 200/20 000 ). Important car sert d'unité de base à tout ce qui est télécom  
  
## ADSL – Fonctionnement dans réseau  
  
![Capture de 2018-05-03 10:40:54](file://media/2011196011.png)


Le débit ADSL est de 64kilobits par seconde (ou 56 aux USA).  
  
Tous les 125 microsecondes, il envoie un signal, donnant une valeur sur un octet (entre 0 et 255) indiquant l'intensité du signal. Ensuite, le récepteur n'a plus qu'à "relier les points" pour obtenir l'onde à retransmettre. On a donc 8 bits envoyé sur 8kHz : 64kb/s.  
Il faut 64kb dans chaque sens à priori. On a donc 2 câbles équipés pour ça.  
  
## Généralités  
  
La VOIP, c'est vieux. MArché de 2.2 milliards de dollards n 2006  
  
Sur totalité des coms, environ 60% en ntionaux, 30% en local et 10% n internationaux  
  
### Structure  
  
RTP = real time protocol  
RTCP   
SIP met en place un canal, RTP/RTCP l'interface ?  
  
### H323  
Norme UIT-T de 1996  
* Communication multimédia  
* Fonctionne en transfert de paquets  
* Sans garantie de QoS  
* Protocole le plus répandu (à l'époque de sa création)  
Issu du monde télécom, utilisant les techno du réseau.  
  
#### Entités   
  
Fonctionn avec des EndPoints

*  Téléphones (IP phones)
* Visiophones
* Softphone (logiciel pour telephone depuis ordinateur)
  
Fait des passerelles vers autre types de réseau (type RTC, real time communication)  
  
Multipoint Control Unit 

* Genre pieuvre dans sale de conf
  
Gatekeepers  

* Optionnel : permet le fonctionnement en monde centrex ( = réseau centré autour d'un serveur)
* Il est au centre d'une zone : un domaine peut contenir plusieurs zones
* Fait de la résolution d'adresses : maintient un annuaire ouvert (les terminaux se déclarent quand ils sont co)
* Ces serveurs permettent d'établir des règles : machin n'a le droit d'appeler que vers une zone, ou bien ne peut recevoir des appels que de telle à telle heure, autrement c'est direct sur messagerie. Le gatekeeper centralise toutes ces règles : plus pratique !
  
Border Elements 
 
* Placés en bordure de zones ou de domaines, ont un rôle de routeur
* Règle les problèmes d'adressage
  
### Pile protocolaire de H323  
  
Tout est au-dessus de la couche IP, of course.  
Trois stack : données, média et signalisation  
  
#### Signalisation  
  
D'abord UDP/TCP ou juste UDP  
  
 H225 signalisation des appels (machin veut joindre machin)

* RAS permet de s'enregistrer auprès d'un serveur
* Q931 ou CS permet de mettre directement en relation des terminaux
  
D'abord le temrinal se déclare et demande permission de communiquer (RAS) puis vient se mettre en relation via terminal ou gatekeeper (CS)  
  
H245 : savoir dans qu  
  
#### Données  

T38

* Fax
  
T120  

* Partage de documents  
V150
* Signaux modems  
  
AT commands are commands that you can send with a modem. There a lot of AT commands.  
  
#### Media  

RTP 

* Transport des paquets audio/video
* Fonctionnement en temps réel (avec numération et datation des paquets)
* La voix passe par RTP à travers le réseau 
  
RTCP  

* RTP Control Protocol 
* Statitstiques de transmission
* Slow down RTP to control 
  
#### RTP
  
Real Time Transport  

* Transfert de media
* Multicast ou unicast  
  
Ne garantit pas la réservation de ressources ni la QoS pour les services en temps réel  
Réservation: RSVP (reservation protocol, a two-layers protocol. At first, a paquet is send to reserve resources needed for communication). RTP doesn't use this  
  
Utilise RTCP pour la surveillance du transport  
  
RTP c'est une émulation de temps réel. Il a pour but d'émuler un temps réel souple.  
  
Intériur du RTP (frame ? )  
En-tête  

* V version, P padding, X extension (octet 1)
* M marqueur selon l eprofil utilisé, Payload type de données (
* SSRC identifie la source de synchronisation (random)
* CRSC identifie les sources de données du paquet  
  
RTP Control Protocol  

* Emission périodique de paquets d contrôle aux participants d'une session  
  
### Digression SRTP  
  
RTP pas assez sécurisé :  

* Mise en place de SRTP(Secure RTP)
* Fonctionne avc SRTCP
* Créé par Cisco et Ericson
  
Uilisation optionnelle des modules  

* Module authentification
* Module encryption
* Seule l'authentification des messages est obligatoire
  
#### Encryption des données  
*  Basée sur AES :
    * Besoin de transformer AES en encryption par flot
    * Deux types de chiffres
        * Segmented Integer Counter Mode, permet de gérer la perte de paquets dans un réseau sans perte de flot
        *  f8-mode, même fonctionnalités, choisi par l'UMTS  
* NULL cipher
    * Désactive l'encryption
    *  Présence obligatoire sur tout le matériel SRTP  
  
Encryption par bloc : page par page / par flot : à la volée.  
  
  
### H323 : RAS  
  
Enregistrement d'un EP(endpoint)  à un GK (gatekeeper)  

* Découverte de GK par un Gateway Request : soit broadcast (port 1718) soit unicast (port 1719) puis réponse par Gateway confirm (ou Gateway reject)
* Enregistement, avec registrement confirm/request
* Encore une pahse pas vu
  
Participe à la négociation d'un appel (contrôle admission)  

* Admission request 
* Admission confirmation
  
Envoi d'information sur le mode de routage dans l'ACF  
Dialogue entre GK si besoin  
  
H323 : CS (call signaling) Q931  
  
Fonctionnalité:  
* Établissmeent de communication  
* Mise en relation  
* Sonnerie  
* Fin d'apple  
  
Messages minimum pour passer un appel  
* Setup  
* Connect  
* Release complete  
  
Call signaling permet de gérer bien plus que ça (comme le type de connerie, etc)  
  
H323 : H245  
  
On a ouvert un canal entre deux: on doit maintenant choisir la langue dans laquelle discuter : choix des codecs audio/video. par défaut: G711  
  
Échange des adresses IP et ports utilisés par RTP/RTCP  
  
Choix d'un maitre pour une conférence  
  
Exemple de messages :  
* Terminalcapabilityset (formats dispos)  
* MasterSlaveDetermination  
* OpenMLogicalChannel (envoyé par EP avec infos sur les données à envoyer)  
* OpenLogicalChannelAck (la réponse)  
  
H323 : Avantages  
  
Bien rodée et maitrisée  
Technologie bien connue  
Gestion de la sécurisé H235  
Codage ASN1 bien connu  
Possibilité de transporter de nombreux media  
Passage des NAT compliquée mais on a des proxy qui savent le faire (passage par H460)  
Ajout de nouveaux services (H450)  
* Transfert d'appel  
* Renvoi d'appel  
* …  
  
H323 : Limites et évolution  
  
Temps de mise en correspondance long (négociation longue)  
Syntax compliqué  
Multiplicationds canaux (10 appels = 30 canaux : lourd)  
Implémentations souvent mauvaises. Base bien solide mais ajouts ont commencé à chier dans la colle  
=> remplacé petit à petit par le SIP  
  
SIP  
  
Très long à se développer .  
Créé par ITF depuis 1996  
* RFC 3261  
* Maintenu par groupe SIP  
Issu du monde du réseau (pas télécom comme H323)  
  
SIP entités  
User Agent (UA) composé de   
* User Agent Client (UAC) : émission des requêtes  
* User Agent server : réception des réponses  
  
Même types de terminaux  
* IP phones  
* Visiophones  
* Softphones  
  
Registrar Server   
* Enregistre/authentifie les terminaux SIP  
* Relié à un proxy/redirect qui gère les appels  
Proxy server  
* Relaie les messages SIP  
* Interprète, traduit  avant de retransmettr  
Redirect server  
*  Gère la signalisation mais ne relaie pas les messages  
Location server  
* Information de localisation d'un utilisateur (pour proxy/redirect)  
  
Les serveurs sont responsable des domaines  
* Résolution DNS si changement de domaine  
  
Pile protocolaire (stack)  
Juste média et signalisation  
  
Signalisation: SIP / SDP  
Média : RTP-RTCP / codec audio-video  
  
Messages   
Envoyés en texte (ASCII)  
* Décomposés en lignes  
2 types de messages  
* Requêtes   
* Réponses  
Types de messages   
* ACK : confirmation à INVITE  
* BYE : Fin appel  
* REGISTER : enregistrement UA au registrat  
* INVITE : initialisation appel  
* --------  
* CANCEL : annule requete précédente  
* INFO: envoi d'infos  
* MESSAGE : messagerie chat  
* NOTIFY: notif d'évènements  
* OPTION: demande d'infos sur un terminal  
  
Requetes :   
* 1 ere ligne = stzart-line. Type de requete, URI, version de sIP  
* Toutes requetes contiennent  
To  
From   
Cseq  
…  
  
Réponses  
* 1xx info, sonnerie  
* 2xx   
* 3xx  
  
Enrgistrement  
Enregistrement d'un UA  
* Registrar + proxy/redirect = PSS (Proxy Server SIP)  
  
Format : Sip:<user>:<password>@<host>:<port>;<url-parameters>?<headers>  
* Password envoyé en clair > déconseillé, champ non utilisé  
>> vieux format, 0 sécurité  
  
TLS ou HTTP Digest  
* Auth plus sure  
* Sips remplace sip  
* Sip peut être remplacé par tel  
* * Numéro de tel  
* * Pas d'infos réseau  
  
REGISTER  
* Branch identifie la transaction (commence tjrs par z9G4bK)  
* Tag est un identifiant supplémentaire (terminal)  
  
Port 5060 = Port par défaut du SIP  
  
Réponse   
* Tag du To : identifie le serveur  
* expires : durée de l'enregistrement  
  
Signalisation  
3 types :   
* Proxy  
* * Serveur d'appel proxy  
* Redirect  
* * Serveur redirect  
* Forking  
* * Plusieurs UA enregistrés partagent me URI, si appel: tous les terminaux sonnent, et le 1er à décrocher prend l'appel  
*   
SDP  
Décrit les sessions multmédia  
Peut utiliser Session Announcement Protocole (SAP)  
Envoie de part et d'autre liste des codecs qu'on est capable de comprendre, le premier qui matche sera utilisé. Vaut mieux mettre les meilleurs en premier donc.  
  
Compléments intéressants  
Procédure RE-INVITE : permet de modifier une session. Par ex : une conversation audio ou on active caméra, qui devient vidéo. En H323 on doit casser com et la recommencer. En SIP on la met à jour. Bcp moins risqué et long !  
  
IMS (IP Multimedia Service)  
  
Avantages  
Call forwarding et manipulation de numéros  
Identification d'appelant  
Mobilité  
Authentification appelant/appelé  
Automatic call distribution  
Adresse de type URL facilement intégrable au web  
Nombreux mécanismes en cours de dv  
Un seul canal de signalisation  
Passage des NAT (STUN, TURN)  
  
Défauts   
Risques de sécurité (UDP principalement). Pas de sécu par défaut, des surcouches à rajouter (ultra recommandé, principalement SRTP).  
Manque protocole d passage de donnés en temps réel  
Nombreux travaux > problèmes d'interopérabilité  
  
-----------------------  
  
La VOIP passe aujourd'hui principalement par Asterisk. Ça permet de gérer principalement SIP, mais aussi M323 ou MGCP (permet de se faire une infra type France Telecom, mais à l amaison)  
 
