tp3 



&#x20;Ce que j’ai fait



J’ai commencé ce TP en essayant de mettre en place un serveur DHCP avec une machine Rocky Linux et dnsmasq dans GNS3.

Franchement j’ai perdu pas mal de temps dessus parce que le DHCP ne fonctionnait pas correctement.



Problèmes rencontrés :



&#x20;L’interface réseau changeait (enp0s3 / enp0s8)

&#x20;Le serveur DHCP tournait mais les clients ne recevaient rien

&#x20;Impossible d’obtenir une IP sur le PC (ip dhcp → “can’t find dhcp server”)

&#x20;Debug compliqué à cause de GNS3 + VirtualBox



Après plusieurs tentatives (config interface, dnsmasq, vérification câbles, etc.), ça ne fonctionnait toujours pas correctement.



&#x20;Du coup j’ai décidé de continuer le TP sans DHCP fonctionnel pour ne pas perdre plus de temps.

&#x20;DHCP Snooping



Configuration faite sur le switch :

&#x20;Activation du DHCP snooping

&#x20;Activation sur le VLAN 1

&#x20;Port vers le serveur DHCP en trusted



Objectif :

Empêcher un serveur DHCP malveillant de répondre aux clients.

&#x20;DAI (Dynamic ARP Inspection)



Configuration :

&#x20;Activation sur VLAN 1

&#x20;Port trusted côté “serveur”



Objectif :

Bloquer les attaques de type ARP spoofing / MITM.

&#x20;IP Source Guard



Configuration :



&#x20;Activation sur le port du client
 Ajout de device tracking + port security



Objectif :

Empêcher l’usurpation d’adresse IP.





