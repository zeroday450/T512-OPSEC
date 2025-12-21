1. Plateforme matérielle principale

Modèle : ThinkPad L512

Architecture : x86 legacy

Rôle : nœud de calcul isolé

Exposition radio : aucune

Interfaces actives : Ethernet uniquement

Contraintes :

Aucun périphérique radio intégré fonctionnel

Aucun stockage interne critique utilisé pour l’exécution

2. Chaîne de confiance firmware
2.1 Intel Management Engine

Intel ME présent (niveau -3)

Neutralisation partielle (~90 %) via me_cleaner

ME laissé dans un état minimal requis au boot

2.2 Firmware système

BIOS remplacé par coreboot / libreboot

Configuration minimale

Désactivation des fonctionnalités non nécessaires

Accès BIOS restreint

3. Chaîne de boot

Boot exclusivement depuis support externe

Support : disque externe chiffré LUKS

SSD interne :

jamais utilisé pour le boot

jamais monté en environnement opérationnel

utilisé comme stockage leurre

Invariants :

Aucun démarrage sans support externe valide

Aucune persistance opérationnelle locale

4. Topologie réseau globale
4.1 Chaîne réseau logique
Alfa WAN → Raspberry Pi 4 → Tunnel WireGuard → (Tor optionnel) → Laptop (Ethernet)


Le laptop ne communique jamais directement avec un réseau radio

Toute exposition réseau est médiée par le Pi

5. Orchestration réseau (Raspberry Pi 4)

Fonctions assurées :

Randomisation MAC avant chaque association

Établissement du tunnel WireGuard

Supervision de l’état du tunnel

Kill-switch strict :

nftables / iptables

watchdog actif

Centralisation de logs chiffrés

Interfaces :

Entrée : USB (Alfa)

Sortie : Ethernet (vers laptop)

6. Sous-système radio
6.1 Interfaces utilisées

Alfa Network AWUS036 : WAN

Alfa NHA : monitor / injection

Contraintes :

Rôles fixes

Aucun switch dynamique de mode

Scripts de verrouillage dédiés

Séparation stricte des usages

7. Stockage
7.1 Stockage opérationnel

Disque externe chiffré (LUKS)

Usage éphémère

Clés dédiées

Effacement logique après déconnexion

7.2 Stockage interne (leurre)

SSD interne installé

Système cohérent simulé

Activité crédible persistante

Aucun lien avec les opérations réelles

8. Gestion des périphériques

Aucun périphérique USB externe autorisé hors disque dédié

Clés et supports strictement associés à la machine

Ports inutilisés désactivés physiquement

9. Réductions matérielles

Micro retiré physiquement

Caméra retirée physiquement

Wi‑Fi retiré physiquement

Bluetooth retiré physiquement

Ports non nécessaires neutralisés

RAM soudée (réduction surface de dumping)

10. Gestion de l’alimentation
10.1 Alimentation réseau exposé

PB1

Alimente : Raspberry Pi + Alfa

Sortie stable continue

Pass-through

Régulation DC‑DC

Faible ripple

10.2 Alimentation du laptop

PB2

Intercalée entre secteur et laptop

Rupture de liaison directe secteur → machine

Atténuation des variations électriques

Bonnes pratiques intégrées :

Câbles blindés

Ferrite beads

Chargeurs distincts

Alternance des cycles de charge

Option :

UPS / transformateur d’isolation

Module régulé dédié

11. Transport et confinement

Stockage dans mallette Faraday

Structure :

bois

aluminium

couche conductrice interne

Confinement total en état fermé

12. Invariants techniques

Le laptop ne voit jamais le Wi‑Fi

Le laptop ne voit jamais le WAN

Le réseau est toujours médié

Le stockage interne n’est jamais critique

L’exposition est observable

La persistance est externe
