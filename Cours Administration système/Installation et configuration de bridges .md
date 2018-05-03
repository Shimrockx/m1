Installation et configuration de bridges 
========================
*18/01/2018*

## Mise en œuvre du réseau Debian  

 

Networking :   
/etc/init.d/network [start|stop|force-reload]   
/etc/init.d/networking [start|stop|force-reload] 

### Les 6 run levels : 

 * 0 = stop 
* 1 = système mini 
* 2 = démarrage mode texte sans réseau 
* 3 = fonctionnement en mode texte multitâche et multiposte 
* 4 = fonctionnement en mode test admin 
* 5 = plus ou moins comme 3 en mode graphique 
* 6 = reboot 

On vérifie si le service networking est lancé au niveau 3 :  
ls -l /etc/rc3.d | grep netwo*  

puis on vérifie sur tous les services  
ls -l /etc/init.d | grep netwo* 

nano /etc/NetworkManager/NetworkManager.conf 

 

**Arrêt du NetworkManager**  
/etc/init.d/network-manager stop 

Carte reliée au réseau de la classe :  Gigabyte, chipset 3 

 

Première chose à faire quand on arrive sur un serveur :   
**Vérifier les cartes réseau**  
lspci | grep -i ether  
**Vérifier le chipset**  
ethtool –i eth0 (puis eth1...) 

### Réécriture du fichier /etc/network/interfaces 

#### 1/ Faire un backup 

cp /etc/network/interfaces /etc/network/bckp-interfaces 

#### 2/ Réécriture 

nano /etc/network/interfaces 

 

auto lo  
iface lo inet loopback 

 

```
auto eth1  
allow-hotplug eth1  
Iface eth1 inet static  
address 192.168.160.65  
netmask 255.255.255.0  
gateway 192.168.160.161  
broadcast 192.168.160.255  
dns-nameserver 192.168.160.161 
# hw ether <adresse MAC> 

 

auto eth0  
allow-hotplug eth0  
Iface eth0 inet static  
address 172.16.160.65  
netmask 255.255.255.0  
gateway 172.16.160.161  
broadcast 172.16.160.255  
dns-nameserver 172.16.160.161  
# hw ether <adresse MAC>
```
### Attention au fichier /etc/default/networking 

Passer CONFIGURE_INTERFACES à yes 

Redémarrage du réseau avec nouveaux paramètres  
/etc/init.d/networking force-reload 


### Configuration du bridge 

On avait un script à lancer à /root/script-br-tmp.sh 

C'est un peu le bordel, on refait le script, les ping sont chelou, ça dure depuis une heure 

### Test en lançant l'image 

cd /home  
ls –l   

On repère l'image suse 

Puis ctrl alt F4 et x-window-manager &  
Et konsole & dans le carré blanc  
Et losetup /dev/loop2 /home/img_suse42.3  
Puis lostup –a (pour vérifier association) 


