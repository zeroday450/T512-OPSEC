Architecture technique — L512

Portée limitée à l’état du système.
Aucune pédagogie.
Description factuelle des éléments en présence.

Plateforme matérielle

ThinkPad L512.
Architecture x86 legacy.
Machine dédiée.
Interfaces actives limitées à Ethernet.
Aucune interface radio fonctionnelle.

Contraintes :
- pas de Wi‑Fi
- pas de Bluetooth
- pas de caméra
- pas de micro
- réduction matérielle volontaire

Firmware

Intel Management Engine présent.
Neutralisation partielle via me_cleaner.
ME laissé dans un état minimal requis au boot.

Firmware système remplacé.
coreboot / libreboot.
Fonctionnalités non nécessaires désactivées.
Accès firmware restreint.

Chaîne de boot

Boot exclusivement depuis support externe.
Support chiffré (LUKS).
Aucun boot interne autorisé.

Stockage interne présent.
Jamais utilisé pour l’exécution.
Jamais monté en environnement opérationnel.
Utilisé comme surface crédible persistante.

Invariants :
- aucune persistance opérationnelle locale
- dépendance totale au support externe

Réseau — vue globale

Le laptop ne communique jamais directement avec un réseau radio.

Chaîne logique :

Alfa WAN  
→ Raspberry Pi 4  
→ tunnel WireGuard  
→ Tor (optionnel)  
→ Ethernet  
→ laptop  

Toute exposition réseau est médiée.

Raspberry Pi 4 — rôle intermédiaire

Fonctions assurées :
- association radio
- randomisation MAC
- établissement du tunnel WireGuard
- supervision du tunnel
- kill‑switch strict (iptables / nftables)
- centralisation de logs chiffrés

Interfaces :
- entrée : USB (Alfa)
- sortie : Ethernet (vers laptop)

Sous‑système radio

Interfaces utilisées :
- Alfa Network AWUS036 (WAN)
- Alfa NHA (monitor / injection)

Contraintes :
- rôles fixes
- aucun switch dynamique
- scripts de verrouillage dédiés
- séparation stricte des usages

Stockage

Stockage opérationnel :
- disque externe chiffré
- usage éphémère
- clés dédiées
- effacement logique après déconnexion

Stockage interne :
- SSD interne
- système crédible simulé
- activité persistante
- aucun lien avec les opérations réelles

Périphériques

Aucun périphérique USB tiers autorisé.
Supports dédiés par machine.
Ports inutilisés désactivés physiquement.

Réductions matérielles

Micro retiré physiquement.
Caméra retirée physiquement.
Modules radio retirés physiquement.
Ports non nécessaires neutralisés.
RAM soudée (réduction de surface).
