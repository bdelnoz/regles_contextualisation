# CHANGELOG — repository SOLO

Ce fichier décrit uniquement les changements publics et structurels du repository. Les historiques détaillés des artefacts SOLO restent locaux sous `.docs/`.

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
