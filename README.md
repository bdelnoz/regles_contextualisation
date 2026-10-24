# SOLO Rules

SOLO est un système de règles versionnées destiné à rendre le comportement d’un assistant IA plus stable, reproductible et maintenable entre les chats.

## Baseline active

```text
CTX246 / SCRIPT426 / OP144 / CI010
```

## Règles d’or de chargement

- Toute RULE SOLO activée doit être lue intégralement avant d’être déclarée chargée.
- **100 % du fichier effectivement lu jusqu’à EOF réel impose le statut `CHARGÉ` ; aucun critère sémantique/cognitif supplémentaire n’est requis.**
- Une lecture tronquée doit être poursuivie jusqu’à la fin réelle du fichier avant tout travail dépendant.
- Une famille déjà chargée n’est jamais relue automatiquement ; une relecture exige un ordre explicite de l’utilisateur.
- GitHub reste strictement READ ONLY pour l’assistant.
- Les README portent désormais la version SOLO active dans leur nom ; les CHANGELOG conservent leur nom stable non versionné.

## Principe de fonctionnement

Le mécanisme SOLO repose sur les **Custom Instructions du compte ChatGPT** et sur des fichiers de règles versionnés exposés sur GitHub. La baseline de production CI010 utilise `main → SHA courant → fichier à SHA`. Une variante **CI010 RAW de test A/B** est également fournie afin de comparer le comportement avec un chargement direct via `raw.githubusercontent.com`.

Le contenu de :

```text
_CUSTINST_SOLOLAST_CUSTOM_INSTRUCTIONS.md
```

est copié dans **ChatGPT → Personalization → Custom Instructions**.

À chaque nouveau chat, ChatGPT reçoit automatiquement ces Custom Instructions. Elles constituent le point d’entrée du système SOLO : elles indiquent à l’assistant quelles règles charger, le repository, la branche et les chemins `SOLOLAST`. Le chat résout ensuite `main` vers son SHA courant avant toute lecture.

Le fonctionnement est donc :

```text
Nouveau chat ChatGPT
        ↓
Custom Instructions du compte
        ↓
_CUSTINST_SOLOLAST_CUSTOM_INSTRUCTIONS.md
        ↓
Résolution GitHub READ ONLY : main → SHA courant
        ↓
_RULES_SOLOLAST_CONTEXTUALISATION.md
_RULES_SOLOLAST_SCRIPTING.md
_RULES_SOLOLAST_RULESOPERATOR.md
        ↓
Règles SOLO chargées et appliquées au chat
```

L’intérêt principal est que les Custom Instructions restent **courtes et simples**, tout en servant de point d’entrée vers des fichiers de règles beaucoup plus complets.

Cela permet de dépasser la limite pratique de quantité de règles qu’il serait possible de placer directement dans le champ Custom Instructions : au lieu d’y copier toutes les règles, les Custom Instructions indiquent à l’assistant où charger les règles SOLO externes.

Les fichiers `SOLOLAST` possèdent des chemins stables. Une nouvelle version remplace leur contenu sans modifier ces chemins. À chaque nouveau chargement autorisé, le chat résout `main` vers le SHA courant puis lit le `SOLOLAST` à ce SHA. Tant que les Custom Instructions elles-mêmes ne changent pas, il n’est pas nécessaire de les remplacer dans le compte à chaque nouvelle version de CTX, SCRIPT ou OP.

## Fichiers publics actifs

```text
_RULES_SOLO244_CONTEXTUALISATION.md
_RULES_SOLOLAST_CONTEXTUALISATION.md
_RULES_SOLO426_SCRIPTING.md
_RULES_SOLOLAST_SCRIPTING.md
_RULES_SOLO144_RULESOPERATOR.md
_RULES_SOLOLAST_RULESOPERATOR.md
_CUSTINST_SOLO010_CUSTOM_INSTRUCTIONS.md
_CUSTINST_SOLO010_CUSTOM_INSTRUCTIONS_RAW.md
_CUSTINST_SOLOLAST_CUSTOM_INSTRUCTIONS.md
README.md
CHANGELOG.md
.gitignore
```

Les fichiers versionnés identifient précisément la release utilisée. Les fichiers `SOLOLAST` gardent un chemin stable ; la lecture distante est toujours effectuée à un SHA immuable.

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
_RULES_SOLO244_CONTEXTUALISATION.md
_RULES_SOLOLAST_CONTEXTUALISATION.md
```

Lors d’une nouvelle version, un nouveau fichier versionné est créé et le `SOLOLAST` correspondant devient une copie exacte de cette nouvelle version.

Comme le chemin du `SOLOLAST` reste identique, les nouveaux chats peuvent charger la version courante après résolution de `main` vers son SHA, sans qu’il soit nécessaire de modifier les Custom Instructions du compte.

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

1. créer un fichier de Custom Instructions court contenant les règles minimales de démarrage, le repository, la branche et les chemins stables ;
2. copier son contenu dans les Custom Instructions du compte ChatGPT ;
3. conserver les règles détaillées dans des fichiers versionnés du repository ;
4. créer pour chaque famille un alias `SOLOLAST` dont le nom reste stable ;
5. imposer dans les Custom Instructions la résolution `main → SHA courant → fichier SOLOLAST lu à ce SHA` ;
6. à chaque nouvelle version, créer le nouveau fichier versionné puis synchroniser son `SOLOLAST` ;
7. garder la documentation, les archives et les éléments privés hors publication grâce à `.gitignore`.

Cette séparation permet de conserver des Custom Instructions simples tout en pilotant un ensemble de règles beaucoup plus important, versionné et maintenable depuis le repository.

## Chargement GitHub — baseline SHA et variante RAW A/B

Pour toute RULE SOLO publique, le mécanisme de production actif reste :

```text
main → SHA courant → fichier SOLOLAST à ce SHA → lecture intégrale → validation version + SHA
```

La variante `_CUSTINST_SOLO010_CUSTOM_INSTRUCTIONS_RAW.md` permet un test A/B séparé : elle lit directement les `SOLOLAST` via `raw.githubusercontent.com/.../main/...` sans résolution SHA. Elle ne remplace pas automatiquement la baseline SHA.

Lors d’un RELOAD explicitement demandé, le mécanisme sélectionné est réutilisé. Sans ordre explicite, aucune relecture distante n’est effectuée pour une famille déjà chargée.

L’historique des chats et la mémoire servent à la continuité mais ne remplacent pas une source courante vérifiée.

## GitHub

Dans SOLO, l’assistant utilise GitHub en **READ ONLY STRICT**.

Il peut lire, consulter, analyser et comparer le remote. Il peut préparer localement des modifications et les fournir à l’utilisateur.

**AUCUNE ÉCRITURE GITHUB. AUCUNE EXCEPTION. JAMAIS.**

L’utilisateur reste le seul maître de toute écriture, modification, suppression ou publication distante.


## Documentation locale

La documentation détaillée reste locale sous `.docs/`. Chaque module privé possède localement une paire documentaire maître `README + CHANGELOG`, tandis que les RULES privés restent sous `.private/`; ces emplacements sont exclus de la publication par `.gitignore`.


## Validation de chargement 100 % / EOF
Toute RULE SOLO, publique ou privée, n’est considérée chargée qu’après lecture réelle complète jusqu’à EOF et confirmation explicite `Lecture : 100 % / EOF atteint`.
