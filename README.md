# SOLO Rules

SOLO est un système de règles versionnées destiné à rendre le comportement d’un assistant IA plus stable, reproductible et maintenable entre les chats.

## Baseline active

```text
CTX239 / SCRIPT420 / OP133 / CI004
```

## Fichiers publics actifs

```text
_RULES_SOLO239_CONTEXTUALISATION.md
_RULES_SOLOLAST_CONTEXTUALISATION.md
_RULES_SOLO420_SCRIPTING.md
_RULES_SOLOLAST_SCRIPTING.md
_RULES_SOLO133_RULESOPERATOR.md
_RULES_SOLOLAST_RULESOPERATOR.md
_CUSTINST_SOLO004_CUSTOM_INSTRUCTIONS.md
_CUSTINST_SOLOLAST_CUSTOM_INSTRUCTIONS.md
README.md
CHANGELOG.md
.gitignore
```

Les fichiers versionnés identifient précisément la release utilisée. Les fichiers `SOLOLAST` gardent un nom stable pour les accès RAW.

## Contextualisation

La famille **CTX** contient les règles conversationnelles générales : comportement, continuité, présentation, modes généraux et conventions applicables aux chats.

## Scripting

La famille **SCRIPT** contient les règles applicables au code, aux scripts, au debug, aux outils CLI, à la documentation technique et aux workflows de développement. La structure du repository SOLO est gouvernée par Operator.

## Operator

La famille **OP** maintient les artefacts SOLO : création et modification des règles, versionnement, alias `SOLOLAST`, documentation locale, structure du repository et préparation des livraisons locales.

## Custom Instructions SOLO

Le contenu de `_CUSTINST_SOLOLAST_CUSTOM_INSTRUCTIONS.md` est destiné à être copié dans **Personalization / Custom Instructions** du compte ChatGPT. Les Custom Instructions restent volontairement courtes et servent de bootstrap vers les fichiers SOLO.

## Reproduire le mécanisme

Pour chaque famille publique, conserver un fichier versionné et un alias `SOLOLAST`. Lors d’une nouvelle version, créer le nouveau fichier versionné et remplacer le contenu du `SOLOLAST` par une copie exacte de la version active.

La même mécanique s’applique aux Custom Instructions :

```text
_CUSTINST_SOLOxxx_CUSTOM_INSTRUCTIONS.md
_CUSTINST_SOLOLAST_CUSTOM_INSTRUCTIONS.md
```

La documentation locale est conservée sous `.docs/`, les modules locaux privés sous `.private/`, les ZIP sous `.zip/`, les archives sous `.old/` et les exports sous `.export/` ou `.exports/`. Ces emplacements sont protégés par `.gitignore`. Les modules privés utilisent une convention générique telle que :

```text
_RULES_PRIVATE_SOLOxxx_<MODULE>.md
```

Les noms réels des modules privés ne doivent pas apparaître dans la documentation publique.

## GitHub

Dans SOLO, l’assistant utilise GitHub en **READ ONLY STRICT**. Il peut lire et comparer le remote, préparer localement les modifications et les fournir à l’utilisateur. **AUCUNE EXCEPTION. JAMAIS.** L’utilisateur reste le seul maître de toute écriture distante.
