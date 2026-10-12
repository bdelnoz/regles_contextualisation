# SOLO Rules

SOLO est un système de règles versionnées destiné à rendre le comportement d’un assistant IA plus stable, reproductible et maintenable entre les chats.

## Baseline active

```text
CTX241 / SCRIPT422 / OP139 / CI006
```

## Règles d’or de chargement

- Toute RULE SOLO activée doit être lue intégralement avant d’être déclarée chargée.
- Une lecture tronquée doit être poursuivie jusqu’à la fin réelle du fichier avant tout travail dépendant.
- Une famille déjà chargée n’est jamais relue automatiquement ; une relecture exige un ordre explicite de l’utilisateur.
- GitHub reste strictement READ ONLY pour l’assistant.
- Les README portent désormais la version SOLO active dans leur nom ; les CHANGELOG conservent leur nom stable non versionné.

## Principe de fonctionnement

Le mécanisme SOLO repose sur les **Custom Instructions du compte ChatGPT** et sur des fichiers de règles versionnés accessibles en RAW depuis GitHub.

Le contenu de :

```text
_CUSTINST_SOLOLAST_CUSTOM_INSTRUCTIONS.md
```

est copié dans **ChatGPT → Personalization → Custom Instructions**.

À chaque nouveau chat, ChatGPT reçoit automatiquement ces Custom Instructions. Elles constituent le point d’entrée du système SOLO : elles indiquent à l’assistant quelles règles charger et fournissent les URL RAW stables permettant d’accéder aux fichiers `SOLOLAST` présents sur GitHub.

Le fonctionnement est donc :

```text
Nouveau chat ChatGPT
        ↓
Custom Instructions du compte
        ↓
_CUSTINST_SOLOLAST_CUSTOM_INSTRUCTIONS.md
        ↓
URL RAW GitHub stables
        ↓
_RULES_SOLOLAST_CONTEXTUALISATION.md
_RULES_SOLOLAST_SCRIPTING.md
_RULES_SOLOLAST_RULESOPERATOR.md
        ↓
Règles SOLO chargées et appliquées au chat
```

L’intérêt principal est que les Custom Instructions restent **courtes et simples**, tout en servant de point d’entrée vers des fichiers de règles beaucoup plus complets.

Cela permet de dépasser la limite pratique de quantité de règles qu’il serait possible de placer directement dans le champ Custom Instructions : au lieu d’y copier toutes les règles, les Custom Instructions indiquent à l’assistant où charger les règles SOLO externes.

Les fichiers `SOLOLAST` possèdent des noms stables. Une nouvelle version peut donc remplacer le contenu du `SOLOLAST` sans modifier l’URL RAW utilisée par les Custom Instructions. Tant que les Custom Instructions elles-mêmes ne changent pas, il n’est pas nécessaire de les modifier dans le compte à chaque nouvelle version de CTX, SCRIPT ou OP.

## Fichiers publics actifs

```text
_RULES_SOLO241_CONTEXTUALISATION.md
_RULES_SOLOLAST_CONTEXTUALISATION.md
_RULES_SOLO422_SCRIPTING.md
_RULES_SOLOLAST_SCRIPTING.md
_RULES_SOLO139_RULESOPERATOR.md
_RULES_SOLOLAST_RULESOPERATOR.md
_CUSTINST_SOLO006_CUSTOM_INSTRUCTIONS.md
_CUSTINST_SOLOLAST_CUSTOM_INSTRUCTIONS.md
README.md
CHANGELOG.md
.gitignore
```

Les fichiers versionnés identifient précisément la release utilisée. Les fichiers `SOLOLAST` gardent un nom stable pour les accès RAW.

## Contextualisation

La famille **CTX** contient les règles conversationnelles générales : comportement, continuité, présentation, modes généraux et conventions applicables aux chats.

Dans le fonctionnement normal de SOLO, la contextualisation générale est chargée au démarrage du nouveau chat selon les Custom Instructions applicables.

## Scripting

La famille **SCRIPT** contient les règles applicables au code, aux scripts, au debug, aux outils CLI, à la documentation technique et aux workflows de développement.

Elle est chargée lorsque le contexte ou une demande explicite nécessite le mode Scripting. La structure du repository SOLO est gouvernée par Operator.

## Operator

La famille **OP** maintient les artefacts SOLO : création et modification des règles, versionnement, alias `SOLOLAST`, documentation locale, structure du repository et préparation des livraisons locales.

Operator est utilisé lorsque le travail concerne la maintenance du système SOLO lui-même.

## Custom Instructions SOLO

Les Custom Instructions SOLO sont elles-mêmes versionnées :

```text
_CUSTINST_SOLOxxx_CUSTOM_INSTRUCTIONS.md
_CUSTINST_SOLOLAST_CUSTOM_INSTRUCTIONS.md
```

Le fichier versionné permet d’identifier précisément la version utilisée.

Le fichier `SOLOLAST` fournit un nom stable et contient la version active destinée à être copiée dans les Custom Instructions du compte ChatGPT.

Les Custom Instructions SOLO doivent rester courtes. Leur rôle n’est pas de contenir toutes les règles SOLO, mais d’indiquer à ChatGPT comment charger et appliquer les fichiers de règles externes nécessaires.

## Mettre à jour SOLO sans modifier les Custom Instructions du compte

Pour chaque famille publique, SOLO conserve :

```text
un fichier versionné
un fichier SOLOLAST
```

Exemple :

```text
_RULES_SOLO241_CONTEXTUALISATION.md
_RULES_SOLOLAST_CONTEXTUALISATION.md
```

Lors d’une nouvelle version, un nouveau fichier versionné est créé et le `SOLOLAST` correspondant devient une copie exacte de cette nouvelle version.

Comme l’URL RAW du `SOLOLAST` reste identique, les nouveaux chats peuvent charger la nouvelle version automatiquement sans qu’il soit nécessaire de modifier les Custom Instructions du compte.

Les Custom Instructions ne doivent être remplacées dans le compte que lorsqu’une nouvelle version **CI** modifie leur propre contenu.

## Structure locale

La documentation locale est conservée sous `.docs/`, les modules locaux privés sous `.private/`, les ZIP sous `.zip/`, les archives sous `.old/` et les exports sous `.export/` ou `.exports/`.

Ces emplacements sont protégés par `.gitignore`.

Les modules privés utilisent une convention générique telle que :

```text
_RULES_PRIVATE_SOLOxxx_<MODULE>.md
```

Les noms réels des modules privés ne doivent pas apparaître dans la documentation publique.

## Reproduire le mécanisme SOLO

Pour reproduire le principe dans un autre repository :

1. créer un fichier de Custom Instructions court contenant les règles minimales de démarrage et les URL RAW stables ;
2. copier son contenu dans les Custom Instructions du compte ChatGPT ;
3. conserver les règles détaillées dans des fichiers versionnés du repository ;
4. créer pour chaque famille un alias `SOLOLAST` dont le nom reste stable ;
5. faire pointer les Custom Instructions vers les URL RAW des fichiers `SOLOLAST` ;
6. à chaque nouvelle version, créer le nouveau fichier versionné puis synchroniser son `SOLOLAST` ;
7. garder la documentation, les archives et les éléments privés hors publication grâce à `.gitignore`.

Cette séparation permet de conserver des Custom Instructions simples tout en pilotant un ensemble de règles beaucoup plus important, versionné et maintenable depuis le repository.

## GitHub

Dans SOLO, l’assistant utilise GitHub en **READ ONLY STRICT**.

Il peut lire, consulter, analyser et comparer le remote. Il peut préparer localement des modifications et les fournir à l’utilisateur.

**AUCUNE ÉCRITURE GITHUB. AUCUNE EXCEPTION. JAMAIS.**

L’utilisateur reste le seul maître de toute écriture, modification, suppression ou publication distante.


## Documentation locale

La documentation détaillée reste locale sous `.docs/`. Chaque module privé possède localement une paire documentaire maître `README + CHANGELOG`, tandis que les RULES privés restent sous `.private/`; ces emplacements sont exclus de la publication par `.gitignore`.
