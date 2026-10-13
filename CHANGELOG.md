## 2026-10-13 — Validation universelle 100 % / EOF
- Baseline : CTX243 / SCRIPT425 / OP142 / CI009.
- Toutes les RULES SOLO actives, publiques et privées, exigent désormais une lecture réelle 100 % jusqu’à EOF avant statut CHARGÉ.
- Confirmation obligatoire : fichier + version + révision/source + `Lecture : 100 % / EOF atteint`.
- CI009 reste sous la limite de 5000 caractères.

# Baseline CTX242 / SCRIPT424 / OP141 / CI008 — 2026-10-13

- SCRIPT424 : correction des métadonnées de version.
- OP141 : correction des métadonnées et baseline ; limite CI <= 5000 caractères rendue obligatoire.
- CI008 : compression fonctionnellement équivalente du mécanisme SHA/anti-reload, 3893 caractères.
- Aucun ancien fichier actif n’est inclus dans le package de livraison.

# CHANGELOG — baseline CTX242 / SCRIPT423 / OP140 / CI007 — 2026-10-13

- Abandon définitif du mécanisme GitHub RAW pour les chargements et RELOAD SOLO publics.
- Nouveau mécanisme obligatoire : `main → SHA courant → contenu à SHA immuable → lecture intégrale jusqu’à EOF`.
- Custom Instructions : suppression de `CTX_RAW`, `SCRIPT_RAW`, `OP_RAW`.
- RELOAD : nouvelle résolution de SHA uniquement sur ordre explicite de l’utilisateur.
- Historique/mémoire : continuité uniquement, jamais validation de fraîcheur distante.
- Baseline active : CTX242 / SCRIPT423 / OP140 / CI007.

# CHANGELOG — repository SOLO

- 2026-10-13 00:42:43 +02:00 — baseline CTX241 / SCRIPT422 / OP139 / CI006 : correction de cohérence d’une livraison précédente (métadonnées SCRIPT, README SCRIPT, en-tête CTX, références actives Operator/README racine).

- 2026-10-13 — Operator OP138 : archivage `.old/` exhaustif + commande `mv -f` copy/paste obligatoire à chaque livraison.

Ce fichier décrit uniquement les changements publics et structurels du repository. Les historiques détaillés des artefacts SOLO restent locaux sous `.docs/`.

## 2026-10-13 — baseline CTX240 / SCRIPT421 / OP137 / CI006

- Operator incrémenté de OP136 vers OP137.
- Une ancienne version encore présente dans le ZIP local est désormais traitée comme un historique non encore déplacé vers `.old/`, et non comme une version active concurrente.
- Chaque livraison Operator doit fournir la liste exacte `À déplacer vers .old/`, calculée depuis le ZIP local courant et la livraison produite.
- Les anciennes RULES et README versionnés remplacés sont signalés ; les alias `SOLOLAST` et CHANGELOG stables restent remplacés en place.

## 2026-10-13 — baseline CTX240 / SCRIPT421 / OP136 / CI006

- Ajout universel de la règle 0.0 de chargement intégral obligatoire et anti-reload automatique dans toutes les familles SOLO actives publiques et privées.
- GitHub READ ONLY STRICT devient la règle 0.1 sans changement de portée.
- CTX et Scripting renforcés pour diagnostiquer une non-conformité depuis les règles déjà chargées, sans reread spontané.
- Operator exige désormais le ZIP complet du repository local après son chargement réel avant toute modification/livraison.
- README publics et privés renommés avec la version SOLO active ; CHANGELOG inchangés dans leur naming stable.
- Custom Instructions CI006 alignées sur le même verrou strict.


## 2026-10-11 07:13:42 +02:00 — baseline CTX239 / SCRIPT420 / OP135 / CI005

- Operator incrémenté de OP134 vers OP135.
- Standard documentaire local renforcé : chaque module privé possède désormais un README maître et un CHANGELOG maître sous `.docs/`.
- Aucun module privé RULES n’est modifié par cette livraison documentaire.
- Règle GitHub READ ONLY STRICT inchangée.

## 2026-10-11 07:00:05 +02:00 — baseline CTX239 / SCRIPT420 / OP134 / CI005

- Custom Instructions incrémentées de CI004 vers CI005 et documentation associée complétée.
- Operator incrémenté de OP133 vers OP134.
- Toute livraison d’un artefact SOLO modifié doit désormais inclure son CHANGELOG maître mis à jour.
- Le README maître correspondant doit être mis à jour et livré dès qu’il est impacté.
- `README.md` / `CHANGELOG.md` racine sont livrés lorsqu’un changement de baseline, naming public, mécanisme SOLO ou structure publique les impacte.
- Règle GitHub READ ONLY STRICT inchangée : aucune écriture distante par l’assistant.

## 2026-10-11 06:35:35 +02:00 — baseline CTX239 / SCRIPT420 / OP133 / CI004

- Operator incrémenté de OP132 vers OP133.
- Reconstruction des changelogs maîtres locaux à partir de l’historique récupérable.
- Changelogs maîtres ordonnés de la version la plus récente vers la plus ancienne.
- Naming documentaire des Custom Instructions normalisé au pluriel : `CUSTOM_INSTRUCTIONS`.
- Aucun changement de version CTX, SCRIPT, CI ou module privé dans cette livraison documentaire/Operator.

## 2026-10-11 06:24:02 +02:00 — baseline CTX239 / SCRIPT420 / OP132 / CI004

- Operator incrémenté de OP131 vers OP132.
- Horodatage date + heure rendu obligatoire pour toute nouvelle entrée de version dans les changelogs SOLO.
- Aucun changement de version CTX, SCRIPT, CI ou module privé dans cette livraison corrective.

## 2026-10-11 06:23:29 +02:00 — baseline CTX239 / SCRIPT420 / OP131 / CI004
- Naming Custom Instructions corrigé et stabilisé : `_CUSTINST_SOLOxxx_CUSTOM_INSTRUCTIONS.md` + alias `SOLOLAST`.
- Règle d’or GitHub READ ONLY STRICT appliquée à tous les artefacts SOLO, y compris les modules locaux privés.
- Versionnement obligatoire des modules privés lorsqu’ils sont modifiés.
- Ajout d’un changelog maître local par module privé sous `.docs/`.
- Operator synchronisé avec la structure locale canonique et la baseline CTX239 / SCRIPT420 / OP131 / CI004.

## 2026-10-11 — baseline CTX238 / SCRIPT419 / OP130 / CI003

- Adoption d’un versionnement + alias `SOLOLAST` pour les Custom Instructions.
- Centralisation de la gouvernance de structure du repository dans Operator.
- `README.md` devient le README public générique du système SOLO.
- `CHANGELOG.md` devient le changelog public minimal du repository.
- Documentation détaillée locale sous `.docs/`.
- Modules privés locaux sous `.private/`.
- ZIP locaux sous `.zip/`; exports locaux sous `.export/` / `.exports/`.
- Renforcement de la règle GitHub READ ONLY STRICT : aucune écriture distante par l’assistant.
