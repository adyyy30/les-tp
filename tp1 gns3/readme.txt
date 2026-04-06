 TP1 Réseau



---

  Ce que j’ai réalisé
 1. VLANs sur le switch (IOU1)

J’ai créé et configuré plusieurs VLANs :

* VLAN 10
* VLAN 20
* VLAN 30
* VLAN 40

Chaque PC est connecté à un port du switch associé à son VLAN.

---

 2. Trunk entre switch et routeur

J’ai configuré un lien trunk entre le switch (IOU1) et le routeur (R1) pour transporter plusieurs VLANs sur une seule interface.

---

 3. Routage inter-VLAN (Router-on-a-stick)

Sur le routeur R1, j’ai configuré des sous-interfaces :

* f0/0.10 → VLAN 10
* f0/0.20 → VLAN 20
* f0/0.30 → VLAN 30
* f0/0.40 → VLAN 40

Chaque VLAN a une passerelle (ex: 10.1.X.254).

👉 Résultat : les machines de différents VLANs peuvent communiquer entre elles.

---

 4. Accès Internet (NAT)

J’ai configuré :

* Une interface externe (f1/0) avec DHCP
* NAT overload pour traduire les IP privées vers Internet

👉 Résultat : les PCs peuvent ping 8.8.8.8 (Internet fonctionne).

---

 5. Configuration des PCs

Chaque PC a :

* Une adresse IP correcte
* Une passerelle (gateway)
* Un DNS (1.1.1.1)

👉 Résultat : les PCs peuvent accéder à Internet et résoudre les noms (google.com).

---

 Ce que je n’ai pas complètement réalisé

 1. DHCP centralisé (Rocky Linux)

J’ai installé une machine Rocky Linux pour servir de DHCP.

Cependant :

* La communication entre le serveur DHCP et le réseau ne fonctionne pas complètement
* Les PCs utilisent des IP configurées manuellement

👉 Donc le DHCP n’est pas totalement opérationnel.

---

 2. Relay DHCP (ip helper-address)

La configuration DHCP relay  n’est pas finalisée ou testée complètement.

