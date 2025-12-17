[SEGMENT 02] Threat model et hypothèses

Pourquoi l’OPSEC.
La recherche de discrétion, de dilution dans la masse, ne relève pas uniquement de la peur, du regard d’autrui ou du jugement social. Ces facteurs existent, mais ils ne suffisent pas à expliquer l’engagement réel dans une démarche OPSEC.
Dans le champ technologique, ces motivations sont simplement transposées, réorientées vers des systèmes où la surveillance est permanente, silencieuse et cumulative.

Le contrôle aujourd’hui n’est plus événementiel.
Il est continu.
Agences de renseignement, plateformes, infrastructures de logs, mécanismes d’audit, besoins organisationnels de traçabilité. La liste est longue. La plupart des individus y sont soumis sans jamais en percevoir l’ampleur réelle.

L’hypothèse de départ est simple :
tout individu devrait conserver une part d’anonymat fonctionnel.
Non pas par idéologie, mais par hygiène stratégique.

Or, la majorité est en retard sur la réalité opérationnelle.
Les adversaires ne sont plus humains à l’échelle individuelle. Ce sont des systèmes. Des programmes capables d’agréger une vie entière de logs, de corréler des comportements faibles, de reconstruire une identité à partir de fragments apparemment insignifiants.

Créer un compte Gmail, utiliser un VPN dit “no‑log”, changer de navigateur.
Tout cela laisse des traces.
À un certain niveau, la question n’est même plus de savoir qui logge quoi, mais de reconnaître que tout est loggé quelque part, par quelqu’un, pour une durée indéterminée.

La défiance envers certains acteurs (VPN, services de confidentialité, purisme* ) n’est pas le cœur du problème.
Le problème est systémique : la corrélation.

Dans ce contexte, l’hypothèse centrale est la suivante :

Pour se prémunir contre la surveillance de masse, il ne faut pas devenir invisible, mais devenir banal.

Ressembler à tout le monde protège mieux que disparaître.
Les profils rares attirent. Les fantômes finissent par émerger. La normalité statistique, elle, se dissout dans le bruit.

Cela dépasse largement le choix d’un navigateur.
Disposition clavier, résolution écran, nombre d’écrans, périphériques connectés, fingerprinting logiciel, traces radio passives, modules Bluetooth, jusqu’à des éléments aussi triviaux qu’une souris sans fil pouvant devenir vecteur d’attaque ou de capture indirecte.

La surface d’attaque est large.
Elle ne cesse de s’étendre.

Dans une démarche OPSEC réaliste, l’adversaire n’est pas seulement externe.
L’utilisateur lui‑même est un vecteur critique.
Un écran non verrouillé.
Un kill‑switch défaillant.
Une configuration approximative.
Une décision prise sous fatigue.

Les fuites se combinent.
Elles se recoupent.
Exactement comme une triangulation cellulaire : chaque source isolée est faible, mais leur convergence devient exploitable.

Les outils de corrélation (OSINT automatisé, graphes relationnels, enrichissement de données) ne font qu’accélérer ce phénomène.
La prouesse technique dépasse désormais largement le raisonnement humain individuel.
Les décisions stratégiques fluctuent. Les systèmes, eux, persistent.

À cela s’ajoute une asymétrie matérielle majeure.
Les processeurs modernes intègrent des couches de contrôle situées sous le BIOS, inaccessibles à l’utilisateur. Sur les plateformes récentes, leur neutralisation devient marginale, parfois impossible.
À cela s’ajoutent d’autres vecteurs connus : dumping mémoire, MITM, persistance des logs, compromission indirecte.

Dans ce cadre, le ThinkPad L512 n’est pas conçu comme un objet “furtif”.
Il incarne une application concrète d’un raisonnement stratégique face aux surfaces d’attaque actuelles.

Neutralisation partielle de l’Intel ME.
Firmware maîtrisé.
Boot exclusif sur support externe chiffré.
Stockage interne volontairement utilisé comme leurre.
Réduction matérielle des capteurs.
Séparation stricte entre calcul et exposition réseau.
Chaîne radio externalisée, observable, contrôlable.
Alimentation pensée comme signal.
Transport pensé comme exposition.

Chaque choix découle directement du threat model.

Une hypothèse a cependant été abandonnée dès le départ :
l’hygiène numérique parfaite.

L’humain est la première faille.
Aucune discipline ne tient indéfiniment.
À terme, l’erreur arrive : un compte personnel, une habitude, un relâchement.

Poursuivre une OPSEC parfaite reviendrait à se retirer du monde.
Cette finalité est rejetée.

L’incertitude, l’impossibilité d’atteindre un état “parfait”, ne sont pas des échecs.
Elles constituent le moteur même du projet.

Si une solution définitive existait, ce travail n’aurait aucun sens.
