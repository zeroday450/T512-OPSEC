# Modèle d'état et invariants

## Objectif
Définir les états observables et invariants structurels du système.  
Identifier les conditions où le modèle cesse d'être valide.

---

## États fondamentaux
- Laptop éteint / hors alimentation
- Laptop sous alimentation filtrée (PB2)
- Raspberry Pi maître actif
- Alfa Network actif (WAN)
- Alfa NHA en mode injection / monitor
- VPN WireGuard actif / pass-through
- Honeypot interne actif
- Logs centralisés chiffrés
- Disque externe chiffré monté / démonté
- Boot depuis SSD externe
- État de la RAM soudée
- Ports non utilisés désactivés / sécurisés
- Micro, caméra, Wi-Fi, BT retirés

---

## Invariants
- Le laptop ne voit jamais le réseau direct.
- Le Pi orchestre toute exposition réseau.
- Les Alfa ne changent jamais de rôle sans intervention contrôlée.
- Kill-switch actif : coupure totale si VPN tombe.
- Logs centralisés toujours chiffrés.
- Alimentation PB1 stable pour Pi + Alfa.
- Alimentation PB2 intercalée pour laptop.
- Disque interne simulant honeypot isolé du vrai SSD.
- Clés, USB, périphériques externes limités au disque chiffré.
- BIOS verrouillé, Coreboot / Libreboot flashé, Intel ME neutralisé.

---

## Points de contrôle critiques
- VPN actif avant toute exposition.
- Randomisation MAC Alfa avant association.
- Kill-switch et firewall opérationnels.
- Honeypot monté avant interaction externe.
- Intégrité du SSD externe avant boot.
- Isolation physique : malette Faraday, suppression micro/cam.

---

## Hypothèses fragiles
- Masse suffisante pour masquer signatures radio/électriques.
- Non-ciblage spécifique préalable du matériel.
- Fiabilité des powerbanks et régulateurs.
- Conformité du firmware Coreboot/Libreboot.
- Fiabilité du VPN Mullvad et Tor pour la phase réseau.

---

## Zones de non-validité
- Attaques exploitant comportement humain.
- Corrélations multi-canal externes non mesurables localement.
- Exploits inconnus niveau Intel ME / hardware spécifique.
- Analyse comportementale prolongée de l’utilisateur.
- Observation physique persistante ou multi-agence.

---

## Notes
- Tous les états et invariants sont observables par le modèle.  
- Toute rupture d’invariant rend le raisonnement non fiable.  
- Silence volontaire sur les dépendances externes inobservables.
