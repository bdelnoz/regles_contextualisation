# PACKAGE SOLO COMPLET — BASELINE DE TRAVAIL

Baseline française complète destinée à être jointe à un nouveau chat SOLO / Operator.

## Versions incluses

- Contextualisation : CTX235
- Scripting : SCRIPT417
- Rules Operator : OP126

## Décisions actives

- SCRIPT415 et SCRIPT416 restent exclus de la production.
- SCRIPT417 est la version Scripting active.
- OP126 ajoute la liste exacte des fichiers à déplacer vers `.old/` après chaque livraison.
- Les nouveaux chats Operator utilisent une séquence `001.`, `002.`, `003.`… au lieu de réinitialiser à `000.`.
- Tout package complet contient désormais `CHANGELOG.md` à la racine.
- Les alias `SOLOLAST` sont remplacés en place et ne sont pas déplacés vers `.old/`.

## Structure

- Racine : fichiers actifs, bootstrap, README/CHANGELOG, `.gitignore`, manifest.
- `.docs/` : README et CHANGELOG de chaque famille active.
- `.zip/` : ZIP règle-seule et package complet par famille.

- CTX235 makes rule 101 the single complete Read Aloud rule; former Read Aloud rules 114 and 117 and the 101 bis reminder are absorbed and removed.
