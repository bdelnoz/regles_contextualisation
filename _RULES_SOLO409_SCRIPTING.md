Nom canonique : SOLO409  
Famille : SOLOxxx (xxx = numéro de version)  
Version actuelle : 409
Document : _RULES_SOLO409_SCRIPTING.md  
Auteur : non publié dans la version publique
Email : non publié dans la version publique
Date : 2026-07-26
Statut : version scripting publique assainie avec structure publique finale, confidentialité nominative, README synchronisé, fichiers génériques SOLOLAST et compatibilité GitHub avec bypass de démarrage.

CES RÈGLES DE SCRIPTING S’APPELLENT SOLOxxx, où xxx représente le numéro de version.

Lorsque je dis SOLO409, je fais référence à la version 409 des règles.

Lorsque je dis SOLO suivi d’un numéro, par exemple SOLO405, je fais référence à la version correspondante.

Lorsque je dis simplement SOLO, cela fait référence à la dernière version publiée.

SOLO409 remplace SOLO408, SOLO407, SOLO406, SOLO405, SOLO404, SOLO403, SOLO402, SOLO401, SOLO400, SOLO311, SOLO310, SOLO309, SOLO308, SOLO307, SOLO306, SOLO305, SOLO304, SOLO303, SOLO302, SOLO301, SOLO300 et toutes les versions SOLO scripting précédentes pour les demandes de scripting, génération de code, correction de code, génération de fichiers techniques et génération de documentation liée à des scripts.

SOLO409 est conçu pour les LLM de chat, notamment ChatGPT, LeChat ou équivalents.

SOLO409 reprend la logique de travail de AGENTS.md sous une forme adaptée à un LLM de chat : mêmes attentes de rigueur, documentation, non-suppression, versionnement, spécifications et livrables complets, mais sans prétendre remplacer les règles système de la plateforme utilisée.

# Scripting Contextualisation Rules

------------------------------------------------------------------------

## 1. PORTÉE DE SOLO405

### 1.1 Objectif

SOLO405 définit les règles applicables aux demandes utilisateur concernant :

- création de scripts ;
- correction de scripts ;
- amélioration de scripts ;
- génération de code ;
- modification de code ;
- génération de fichiers techniques liés à un script ;
- documentation liée à un script ou à un dépôt de scripts ;
- analyse technique préparatoire avant modification de scripts.

### 1.2 Nature de SOLO405

SOLO405 est une adaptation LLM des règles de dépôt de type AGENTS.md.

SOLO405 doit permettre à un LLM de chat de travailler avec la même logique que AGENTS.md, même lorsque le fichier AGENTS.md n’est pas fourni dans le chat.

SOLO405 n’est pas une règle système de plateforme.

SOLO405 s’applique dans les limites techniques, fonctionnelles, légales et de sécurité de la plateforme utilisée.

### 1.3 Priorité opérationnelle

Pour les demandes de scripting, appliquer l’ordre suivant :

1. règles système et règles de sécurité de la plateforme ;
2. instructions explicites de l’utilisateur dans le message courant ;
3. fichier AGENTS.md si l’utilisateur le fournit ou si le contexte du dépôt le contient ;
4. SOLO405 ;
5. préférences générales de conversation de l’utilisateur.

Si AGENTS.md est fourni ou explicitement présent dans le dépôt, AGENTS.md reste la règle de dépôt master.

SOLO405 sert alors de traduction LLM et de préférence de réponse tant qu’il ne contredit pas AGENTS.md.

------------------------------------------------------------------------

## 2. MODE REPO PAR DÉFAUT ET MODE SIMPLE EXCEPTIONNEL

### 2.1 Mode repo par défaut

Par défaut, toute demande de scripting doit être considérée comme un travail destiné à un dépôt Git.

L’assistant doit orienter l’utilisateur vers le mode repo lorsque la demande concerne :

- un script durable ;
- une modification de script existant ;
- un projet de scripts ;
- un dépôt existant ;
- un fichier avec versionnement ;
- un outil réutilisable ;
- une automatisation ;
- une documentation associée ;
- une modification ayant un impact sur le comportement, les sorties, les options, les fichiers ou le workflow.

### 2.2 Recommandation de passage en mode repo

Si l’utilisateur demande de scripter sans préciser le contexte, l’assistant doit considérer le mode repo comme la voie normale.

L’assistant peut rappeler brièvement que le mode repo est recommandé, sauf si l’utilisateur demande explicitement un script simple hors repo.

### 2.3 Mode script simple hors repo

Le mode script simple hors repo est une exception rare.

Il est autorisé uniquement si l’utilisateur le demande explicitement ou indique clairement qu’il ne veut pas de workflow repo.

Exemples de demande explicite :

- « fais-moi juste un petit script simple » ;
- « pas besoin de repo » ;
- « pas de workflow AGENTS » ;
- « pas de documentation complète » ;
- « script temporaire » ;
- « commande rapide transformée en script ».

### 2.4 Règles minimales en mode script simple

Même en mode simple hors repo, le script doit contenir au minimum :

- un script complet ;
- un en-tête propre ;
- auteur ;
- email ;
- version ;
- date ;
- usage cible ;
- changelog minimal ;
- aide si le script prend des arguments ;
- absence de secret en dur ;
- comportement non destructif par défaut lorsque possible.

En mode simple hors repo, les fichiers SPECIFICATIONS, README, CHANGELOG, INSTALL et WHY ne sont pas obligatoires sauf demande explicite de l’utilisateur.

------------------------------------------------------------------------

## 3. RÈGLE ABSOLUE DE PROTECTION AGENTS.md, CLAUDE.md ET SYMLINKS D’INSTRUCTION

### 3.1 AGENTS.md comme référence de dépôt

Dans un dépôt utilisateur, AGENTS.md est considéré comme la règle master de dépôt si le fichier existe ou si l’utilisateur l’a fourni.

SOLO405 ne doit pas concurrencer AGENTS.md.

SOLO405 ne doit pas remplacer AGENTS.md.

SOLO405 ne doit pas fusionner arbitrairement des règles contradictoires avec AGENTS.md.

En cas de conflit entre SOLO405 et AGENTS.md dans un contexte de dépôt, AGENTS.md prime pour le dépôt.

### 3.2 Interdiction stricte de modification de AGENTS.md

AGENTS.md ne doit jamais être modifié automatiquement.

L’assistant ne doit jamais modifier, réécrire, reformater, normaliser, renommer, supprimer, déplacer, régénérer, convertir, copier, écraser, versionner ou version-bumper AGENTS.md sauf si l’utilisateur demande explicitement une modification de AGENTS.md dans la demande courante.

AGENTS.md ne doit jamais être inclus dans une mise à jour automatique de documentation, de spécifications, de synchronisation, de nettoyage, de formatage, de maintenance, de refactor, de changelog ou de repository-wide update.

AGENTS.md n’est pas une documentation normale de projet.

AGENTS.md est un fichier de gouvernance du dépôt.

Si une proposition, un patch, un fichier généré, une archive ou une instruction inclut une modification non demandée de AGENTS.md, l’assistant doit arrêter cette partie, signaler l’erreur et fournir une version corrigée sans modification de AGENTS.md.

### 3.3 Interdiction stricte de modification de CLAUDE.md

CLAUDE.md ne doit jamais être modifié automatiquement.

L’assistant ne doit jamais modifier, réécrire, reformater, normaliser, renommer, supprimer, déplacer, régénérer, convertir, copier, écraser, versionner ou version-bumper CLAUDE.md sauf si l’utilisateur demande explicitement une modification de CLAUDE.md dans la demande courante.

CLAUDE.md doit être traité comme un lien symbolique vers AGENTS.md.

L’état attendu est :

```text
CLAUDE.md -> AGENTS.md
```

CLAUDE.md ne doit jamais être remplacé par un fichier Markdown normal contenant une copie de AGENTS.md.

CLAUDE.md ne doit jamais devenir une source indépendante de règles.

CLAUDE.md ne doit jamais contenir une version dupliquée, divergente, reformulée ou condensée des règles AGENTS.md.

### 3.4 Interdiction stricte de modification des symlinks d’instruction liés à AGENTS.md et CLAUDE.md

Les liens symboliques d’instruction liés à AGENTS.md ou CLAUDE.md ne doivent jamais être modifiés automatiquement.

L’assistant ne doit jamais modifier, réécrire, reformater, normaliser, renommer, supprimer, déplacer, régénérer, convertir, copier, écraser, versionner ou version-bumper un symlink d’instruction lié à AGENTS.md ou CLAUDE.md, sauf si l’utilisateur demande explicitement une modification de ce symlink exact dans la demande courante.

Les liens symboliques d’instruction ne doivent jamais être remplacés par des fichiers Markdown normaux.

Les liens symboliques d’instruction ne doivent jamais être déréférencés puis écrasés par leur cible.

Les liens symboliques d’instruction ne doivent jamais être convertis en copies indépendantes.

Cette protection s’applique uniquement aux liens symboliques d’instruction explicitement liés à AGENTS.md ou CLAUDE.md, sauf demande explicite contraire de l’utilisateur.

Sans demande explicite, AGENTS.md, CLAUDE.md et leurs symlinks d’instruction restent hors périmètre, même pendant une génération, une synchronisation, une mise à jour documentaire, une création d’archive ou un nettoyage de dépôt.

### 3.5 Comportement si CLAUDE.md est absent ou incorrect

Si CLAUDE.md est absent, incorrect, non symbolique, cassé ou remplacé par une copie, l’assistant ne doit pas le corriger automatiquement sauf demande explicite de l’utilisateur.

L’assistant peut signaler l’état constaté et fournir une commande de correction uniquement si cela est utile et explicitement demandé.

Sans demande explicite, AGENTS.md et CLAUDE.md restent intouchables.

### 3.6 Règle de priorité pratique

Pour tout travail de scripting, documentation, spécifications, nettoyage, génération de fichiers, création d’archive ou maintenance de dépôt, considérer AGENTS.md, CLAUDE.md et tous les symlinks d’instruction explicitement liés à AGENTS.md ou CLAUDE.md comme hors périmètre par défaut.

Ils ne deviennent dans le périmètre que si l’utilisateur les nomme explicitement comme fichiers à modifier.

### 3.7 Exclusion des fichiers d’instruction dans les livrables

AGENTS.md, CLAUDE.md et tous les symlinks d’instruction explicitement liés à AGENTS.md ou CLAUDE.md ne doivent jamais être inclus dans les archives ZIP, livrables, paquets de fichiers, bundles, rapports de projet ou fichiers générés, sauf demande explicite de l’utilisateur.

L’assistant ne doit pas livrer une copie de AGENTS.md ou CLAUDE.md comme fichier projet.

L’assistant ne doit pas inclure ces fichiers dans une archive sous prétexte de complétude, synchronisation, contexte, conformité ou documentation.

### 3.8 Aucune procédure de vérification AGENTS.md / CLAUDE.md

L’assistant ne doit pas proposer de procédure de vérification de AGENTS.md, CLAUDE.md ou de leurs liens symboliques, sauf demande explicite de l’utilisateur.

L’assistant ne doit pas fournir spontanément de commandes `find`, `readlink`, `ls -l`, `test -L`, `cp`, `ln`, `rm`, `unzip`, ou équivalentes pour gérer ou vérifier ces fichiers d’instruction.

La présence, l’absence, l’état ou le lien symbolique de AGENTS.md ou CLAUDE.md n’est pas à gérer par l’assistant.

L’utilisateur gère lui-même ces fichiers et leurs liens symboliques.

------------------------------------------------------------------------

## 4. RÈGLE GIT

### 4.1 Git hors périmètre SOLO405

SOLO405 ne définit pas le workflow Git de l’utilisateur.

L’utilisateur gère lui-même :

- branches ;
- commits ;
- pull ;
- push ;
- rebase ;
- reset ;
- tags ;
- PR ;
- aliases Git ;
- commandes comme gita ou équivalents.

### 4.2 Ne pas ajouter de workflow Git automatique

L’assistant ne doit pas inclure de règles Git dans SOLO405 sauf demande explicite.

L’assistant ne doit pas imposer de commandes Git dans les livrables scripting sauf si l’utilisateur le demande.

L’assistant peut mentionner qu’un fichier doit être ajouté au dépôt, mais ne doit pas automatiser le workflow Git par défaut.

------------------------------------------------------------------------

## 5. GATE DE SPÉCIFICATIONS ADAPTÉ LLM

### 5.1 Principe général

Pour tout travail de scripting en mode repo qui modifie ou crée un comportement durable, l’assistant doit appliquer une logique specification-first inspirée de AGENTS.md.

Cette règle concerne les demandes qui peuvent modifier :

- comportement ;
- logique ;
- sorties ;
- interfaces ;
- options CLI ;
- noms de fichiers ;
- structure de dossiers ;
- validation ;
- configuration ;
- dépendances ;
- architecture ;
- documentation sémantique ;
- workflow d’exécution ;
- résultats attendus.

### 5.2 Fichiers de spécification attendus en mode repo

En mode repo, les fichiers de spécification attendus sont :

- `./SPECIFICATIONS_GLOBAL.md` ;
- `./SPECIFICATIONS_GLOBAL_FR.md` ;
- `./SPECIFICATIONS.md` ;
- `./SPECIFICATIONS_FR.md`.

`SPECIFICATIONS_GLOBAL.md` décrit la baseline stable du dépôt.

`SPECIFICATIONS_GLOBAL_FR.md` est la traduction française fidèle de `SPECIFICATIONS_GLOBAL.md`.

`SPECIFICATIONS.md` décrit la spécification ciblée de la tâche courante.

`SPECIFICATIONS_FR.md` est la traduction française fidèle de `SPECIFICATIONS.md`.

### 5.3 Adaptation à ChatGPT ou LLM de chat

Si l’assistant n’a pas accès au dépôt réel, il doit fournir les fichiers complets prêts à télécharger ou prêts à copier dans le dépôt.

L’assistant ne doit pas prétendre avoir modifié le dépôt si les fichiers n’ont pas réellement été écrits dans le dépôt.

L’assistant doit distinguer clairement :

- fichier proposé ;
- fichier généré en téléchargement ;
- fichier réellement modifié dans un environnement outillé ;
- action non exécutée.

### 5.4 Validation utilisateur

En mode repo avec modification structurante, l’assistant doit d’abord produire ou proposer les spécifications complètes.

L’implémentation ne doit commencer qu’après validation explicite de l’utilisateur, par exemple `GO`, sauf si l’utilisateur a explicitement demandé un mode simple hors repo.

Cette validation concerne le contenu fonctionnel et documentaire, pas le workflow Git.

### 5.5 Contenu minimal de SPECIFICATIONS_GLOBAL.md

`SPECIFICATIONS_GLOBAL.md` doit contenir au minimum :

- Purpose ;
- Global scope ;
- Stable verified repository behavior ;
- Repository architecture ;
- Global functional requirements ;
- Global non-functional requirements ;
- Global inputs ;
- Global outputs ;
- Global files and directories ;
- Global interfaces and commands ;
- Global constraints and safety rules ;
- Global validation and acceptance criteria ;
- Task-scoped specification boundary ;
- Out-of-scope items ;
- Changelog.

### 5.6 Contenu minimal de SPECIFICATIONS.md

`SPECIFICATIONS.md` doit contenir au minimum :

- Purpose ;
- Scope ;
- Existing verified behavior ;
- Functional requirements ;
- Non-functional requirements ;
- Inputs ;
- Outputs ;
- Files and directories concerned ;
- Interfaces and commands ;
- Constraints and safety rules ;
- Validation and acceptance criteria ;
- Out-of-scope items ;
- Changelog.

### 5.7 Changelog des spécifications

Les fichiers de spécifications doivent être versionnés.

Ils doivent contenir un changelog interne append-only.

Le changelog doit conserver l’historique complet.

Aucune version historique ne doit être supprimée, compressée ou remplacée par un résumé.

### 5.8 Traductions françaises

`SPECIFICATIONS_GLOBAL_FR.md` et `SPECIFICATIONS_FR.md` doivent être des traductions françaises fidèles.

Elles ne doivent pas ajouter de règles absentes de la version anglaise.

Elles ne doivent pas omettre de règles présentes dans la version anglaise.

En cas de contradiction, la version anglaise est la source de référence et la version française doit être corrigée.

------------------------------------------------------------------------

## 6. FOURNITURE DE CONTENU ET ARTEFACTS

### 6.1 Lien de téléchargement par défaut

Les scripts, documents, fichiers Markdown, fichiers texte, archives, rapports ou autres contenus produits par ChatGPT, LeChat ou un LLM doivent être fournis sous forme de lien de téléchargement lorsque la plateforme le permet.

Cette règle s’applique par défaut.

Après avoir fourni le lien de téléchargement, l’assistant peut demander si l’utilisateur veut aussi afficher le contenu complet dans une boîte Markdown.

Si l’utilisateur demande explicitement le contenu inline, l’assistant peut l’afficher directement.

### 6.2 Livraison ZIP non systématique en mode LLM scripting

En mode LLM scripting, l’assistant ne doit pas produire systématiquement une archive ZIP.

Le type de livrable doit suivre la quantité réelle de fichiers à fournir :

- si un seul fichier est ajouté ou modifié, fournir uniquement ce fichier en téléchargement ;
- si deux petits fichiers simples sont ajoutés ou modifiés, fournir les deux fichiers séparément en téléchargement ;
- utiliser une archive ZIP seulement lorsqu’il y a plusieurs fichiers, une vraie arborescence, ou une demande explicite de ZIP par l’utilisateur.

Une archive ZIP doit contenir uniquement les fichiers projet strictement générés ou modifiés par l’assistant.

Une archive ZIP ne doit jamais contenir AGENTS.md, CLAUDE.md, ni aucun symlink d’instruction explicitement lié à AGENTS.md ou CLAUDE.md, sauf demande explicite de l’utilisateur.

Une archive ZIP ne doit pas contenir de rapport de validation statique sauf demande explicite de l’utilisateur.

Pendant une phase de mise au point des scripts, si l’utilisateur indique que les documents Markdown seront faits plus tard, l’assistant doit livrer uniquement les scripts ou fichiers strictement concernés.

Sauf demande explicite ou passe documentaire finale, un livrable de scripting ne doit pas contenir de fichiers Markdown documentaires additionnels, de rapports annexes, de README supplémentaires, de notes de validation ou de fichiers d’explication.

Lors d’une première livraison complète d’un projet ou d’une version stabilisée, les fichiers Markdown requis doivent être fournis avec les scripts.

Quand l’utilisateur demande explicitement une livraison complète, une version stabilisée ou la passe documentaire finale, l’assistant doit fournir les scripts et les documents Markdown synchronisés.

Les validations effectuées par l’assistant doivent être indiquées dans la réponse de chat, pas livrées comme fichier projet dans l’archive.

L’assistant ne doit pas supposer le chemin local exact du téléchargement.

L’assistant ne doit pas écrire lui-même le répertoire `zip/` dans le dépôt utilisateur sauf demande explicite.

### 6.2.1 Workflow utilisateur pour les ZIP

Workflow utilisateur à respecter lorsqu’un ZIP est explicitement fourni ou nécessaire :

- l’utilisateur crée lui-même le répertoire `./zip` dans le dossier du dépôt ;
- l’utilisateur télécharge lui-même l’archive ZIP dans `./zip` ;
- l’utilisateur extrait lui-même l’archive via Thunar ;
- l’utilisateur déplace lui-même les fichiers extraits vers la racine ou les emplacements voulus du dépôt.

L’assistant ne doit pas fournir spontanément de procédure `unzip`, `cp`, `mv`, `find`, `readlink`, ou équivalente pour appliquer l’archive dans le dépôt.

L’assistant ne doit pas fournir de procédure d’extraction, de copie, de déplacement ou de vérification des fichiers d’instruction sauf demande explicite de l’utilisateur.

### 6.3 Fichiers complets

Lorsqu’un script ou un fichier est créé ou modifié, l’assistant doit fournir le fichier complet.

Ne pas fournir uniquement un diff, un extrait ou une rustine partielle, sauf si l’utilisateur demande explicitement un diff.

### 6.3.1 Livraison immédiate après correction réelle d’un script

À chaque correction réelle d’un script, l’assistant doit fournir immédiatement le fichier complet corrigé en téléchargement.

Cette livraison doit inclure le script complet avec :

- version incrémentée ;
- date mise à jour ;
- changelog interne mis à jour ;
- conservation de l’historique complet des versions précédentes.

L’assistant ne doit pas attendre que l’utilisateur redemande explicitement le fichier corrigé.

Si la correction produit un seul fichier, fournir uniquement ce fichier en téléchargement, sans ZIP.

L'assistant ne doit jamais se limiter à expliquer la correction réelle d'un script sans fournir le fichier complet corrigé lorsque la correction modifie effectivement le contenu du script.

Même pendant une phase d'itération rapide, toute livraison d'un script modifié doit contenir la version complète du script, pas seulement les lignes modifiées.

### 6.4 Pas de placeholders

Les livrables ne doivent pas contenir de placeholders tels que :

- TODO ;
- FIXME ;
- `<value_here>` ;
- « à adapter » ;
- « exemple à compléter » ;
- « mettre ici ».

Exception : l’utilisateur demande explicitement un template.

### 6.5 Ne pas inventer

L’assistant ne doit jamais inventer :

- tests exécutés ;
- validations réalisées ;
- résultats ;
- métriques ;
- dates ;
- environnements ;
- état du dépôt ;
- présence de fichiers ;
- actions terminées.

Si quelque chose n’a pas été exécuté ou vérifié, l’assistant doit le dire clairement.

------------------------------------------------------------------------

## 7. SECRETS, PASSWORDS, CERTIFICATS ET DONNÉES SENSIBLES

### 7.1 Secrets interdits en dur

Ne jamais placer de secrets, mots de passe, certificats privés, tokens, clés API ou équivalents directement dans le code versionné.

### 7.2 Fichier ./.secrets

Si un script a besoin de secrets, utiliser un fichier local :

```text
./.secrets
```

### 7.3 .gitignore

Le fichier `./.secrets` doit être couvert par `.gitignore`.

Avant de modifier `.gitignore`, l’assistant doit demander à l’utilisateur de fournir le `.gitignore` existant ou le template `.gitignore` du dépôt.

L’assistant ne doit pas créer de fichier `gitignore_additions_*`.

Si des ajouts `.gitignore` sont nécessaires, l’assistant doit fournir un fichier `.gitignore` complet fusionné avec l’existant, uniquement si l’utilisateur demande explicitement la modification de `.gitignore` ou fournit le `.gitignore` existant à fusionner.

Ne pas fournir un fragment isolé, un patch partiel ou un fichier d’additions séparé pour `.gitignore`, sauf demande explicite de l’utilisateur.

### 7.4 Modèle ./.secrets et noms de champs

Pour les scripts utilisant un fichier `./.secrets`, utiliser des noms de champs génériques lorsque c’est réutilisable.

Noms génériques préférés :

- `EMAIL`
- `PASSWORD`
- `AUTH_CODE`
- `OTP`
- `TOKEN`
- `API_KEY`

Ne pas préfixer inutilement les variables par le nom du service sauf nécessité technique réelle, conflit de champs ou besoin multi-service dans le même fichier.

Le fichier `./.secrets` livré comme modèle doit contenir les bons noms de champs, avec des valeurs bidon non sensibles ou des valeurs vides.

Une valeur principale ou sensible vide dans `./.secrets` est autorisée.

Une valeur principale ou sensible vide dans `./.secrets` peut être volontairement utilisée pour forcer une saisie runtime.

### 7.5 Saisie runtime des secrets

Si un champ principal ou sensible est vide dans `./.secrets`, le script doit demander cette valeur à l’utilisateur à l’exécution.

Pour `PASSWORD`, `AUTH_CODE`, `OTP`, `TOKEN`, `API_KEY` et équivalents, la saisie interactive doit être masquée.

Si techniquement possible, la saisie masquée doit afficher des astérisques pendant la frappe.

Si l’affichage d’astérisques n’est pas techniquement possible, le fallback doit être une saisie sans écho terminal.

Le script ne doit jamais afficher les valeurs sensibles en clair dans la console.

Le script ne doit jamais écrire les valeurs sensibles dans les logs.

Le script doit accepter qu’un champ sensible soit volontairement laissé vide dans `./.secrets` pour imposer une saisie runtime à chaque exécution.

Si un outil CLI exige un password, token, auth code ou secret en argument, l’assistant ne doit pas inventer un mode interactif non vérifié.

L’assistant doit vérifier ou respecter la syntaxe réelle de l’outil CLI et créer un wrapper utilisant `./.secrets` avec prompt runtime pour les valeurs sensibles lorsque c’est nécessaire.

### 7.6 Pas de push de secrets

Aucun secret ne doit être inclus dans un fichier destiné au dépôt ou à un artefact public.

### 7.7 Données confidentielles de dépôt

L’assistant ne doit pas envoyer ou suggérer d’envoyer le contenu du dépôt, secrets, logs, prompts, fichiers internes, variables d’environnement ou données extraites vers des services externes sans demande explicite de l’utilisateur.

------------------------------------------------------------------------

## 8. RÈGLES GÉNÉRALES DE SCRIPTING ET GÉNÉRATION DE CODE

### 8.1 Script complet obligatoire

Pour toute création, correction ou amélioration de script, fournir le script complet.

Ne jamais répondre seulement avec les modifications à faire.

Ne jamais fournir uniquement des fragments isolés si l’utilisateur attend un script utilisable.

### 8.2 Pas de simplification non demandée

Ne pas simplifier un script existant sans demande explicite.

Ne pas condenser un script existant sans demande explicite.

Ne pas réduire volontairement les fonctionnalités existantes.

Ne pas retirer les commentaires, options, checks, logs, changelogs, validations ou sections de documentation existantes sans demande explicite.

### 8.3 Pas de suppression non demandée

Ne jamais supprimer de fonction existante, option existante, comportement existant, validation existante ou sortie existante sauf si l’utilisateur le demande explicitement.

Si la demande implique une suppression ou simplification, l’assistant doit signaler clairement que cela retire une partie existante avant de produire la version réduite.

### 8.4 Ne pas renommer sans demande explicite

Ne pas renommer les fichiers, fonctions, variables, dossiers, services, commandes, options CLI ou interfaces existantes sauf demande explicite.

### 8.5 Préserver la structure existante

Quand un fichier existant est fourni, préserver sa logique, sa structure générale, son historique, ses commentaires et ses conventions sauf demande explicite contraire.

### 8.6 Niveau technique attendu

Les livrables doivent être prêts à l’emploi, opérationnels, précis et adaptés à un utilisateur Linux avancé.

Ne pas sur-expliquer les bases Linux, shell, Git, APT, logs ou permissions sauf demande explicite.

### 8.7 Interdiction des one-liners de substitution en mode développement repo

Quand l’utilisateur travaille explicitement en mode développement, dépôt Git, script durable, outil réutilisable ou projet versionné, l’assistant ne doit pas remplacer une demande de script ou de fonctionnalité par une commande one-liner, un heredoc temporaire, un bloc Python inline, une commande shell compacte ou une procédure jetable.

Si l’utilisateur demande une fonctionnalité durable dans un dépôt, l’assistant doit fournir un vrai fichier complet correspondant au langage demandé ou au langage approprié au projet.

Cette règle s’applique notamment lorsque l’utilisateur demande :

- un nouveau script ;
- un script secondaire ;
- un filtre de rapports ;
- une extraction de données depuis des fichiers générés par un autre script ;
- une automatisation réutilisable ;
- une fonctionnalité destinée à être versionnée.

Les one-liners restent autorisés uniquement si l’utilisateur demande explicitement une commande rapide, un test temporaire, un diagnostic ponctuel ou un mode rapide.

En mode repo ou développement, une solution conforme doit inclure au minimum :

- un fichier script complet ;
- un header versionné ;
- un changelog interne append-only ;
- un help structuré ;
- un comportement sans argument affichant le help ;
- les options CLI applicables selon SOLO ;
- une validation minimale annoncée clairement ;
- aucun effet destructif non demandé.

Si l’assistant fournit par erreur un one-liner à la place d’un fichier durable en mode repo, il doit reconnaître la violation, fournir le script complet corrigé et identifier la règle SOLO concernée.

------------------------------------------------------------------------

## 9. EN-TÊTES, AUTEUR, VERSION ET CHANGELOG DES SCRIPTS

### 9.1 Commentaires internes détaillés

Chaque bloc important et chaque section du script doivent être commentés pour expliquer la logique interne.

Les commentaires doivent être utiles, pas décoratifs.

### 9.2 En-tête obligatoire

Chaque script exécutable doit commencer par un en-tête structuré, lisible et immédiatement compréhensible.

Pour les scripts shell, le format de référence obligatoire est le suivant :

```sh
#!/bin/sh
# ==============================================================================
# PATH         : ./nom_du_script.sh
# SCRIPT NAME  : nom_du_script.sh
# AUTHOR       : <AUTEUR>
# EMAIL        : <EMAIL>
# TARGET USAGE : <USAGE_COURT>
# VERSION      : vX.Y.Z
# DATE         : YYYY-MM-DD HH:MM
# ==============================================================================
# CHANGELOG:
#   vX.Y.Z – YYYY-MM-DD HH:MM – <AUTEUR>
#       Changed:
#       - <CHANGEMENT_1>
#       - <CHANGEMENT_2>
# ==============================================================================
```

La date du header shell doit toujours inclure l’heure.

L’en-tête doit contenir au minimum :

- chemin prévu ou chemin relatif du script ;
- nom du script ;
- auteur ;
- email ;
- usage cible ou objectif court ;
- version ;
- date et heure ;
- changelog interne append-only.

Le header doit rester lisible dans le fichier source.

Il ne doit pas être un bloc compact illisible, un commentaire minimal, ou un simple rappel de version.

### 9.2.1 Lisibilité obligatoire du header

Le header doit être organisé par lignes ou sections claires.

Il doit permettre d’identifier rapidement :

- le nom du script ;
- son rôle ;
- son auteur ;
- sa version courante ;
- sa date et son heure ;
- l’historique complet des versions internes.

Le changelog interne du header doit être append-only.

Aucune entrée historique du changelog interne ne doit être supprimée, réécrite, compressée ou remplacée par un résumé.

### 9.2.2 Référence officielle du header shell

Les futurs scripts shell livrés par l’assistant doivent suivre le modèle de header ci-dessus comme référence principale.

Les anciens exemples de scripts tels que `create_repo.sh` ou `syncgit.sh` ne sont plus la référence formelle pour le header.

Ils peuvent être ignorés si leur structure diverge du modèle SOLO405.

### 9.3 Auteur par défaut

Utiliser les valeurs suivantes sauf demande explicite contraire :

```text
Auteur : <AUTHOR_NAME>
Email  : <AUTHOR_EMAIL>
```

### 9.4 Versionnement

Tous les scripts générés ou modifiés doivent être versionnés et datés.

La première version doit commencer à `v1.0.0` ou `v1.0`.

Toute modification réelle d’un script doit incrémenter la version.

Ne jamais modifier un script sans mettre à jour ensemble :

- version ;
- date ;
- changelog interne.

### 9.5 Changelog interne

Le changelog interne du script doit conserver l’historique complet.

Aucune version ne doit être retirée.

Aucune entrée historique ne doit être compressée ou effacée.

Ne pas ajouter d’entrée indiquant seulement que de nouvelles règles SOLO ont été appliquées.

Chaque modification réelle d’un script impose :

- incrémenter la version interne ;
- mettre à jour la date et l’heure ;
- ajouter une entrée append-only au changelog interne ;
- ne jamais supprimer les anciennes entrées ;
- faire en sorte que `--changelog` affiche le changelog complet.

Format recommandé pour les entrées internes :

```md
## vX.Y.Z – YYYY-MM-DD HH:MM – <AUTEUR>
  - ADDED: ...
  - CHANGED: ...
  - FIXED: ...
  - REMOVED: ...
```

Les catégories doivent être utilisées selon le contenu réel du changement.

Ne pas créer de catégorie vide si elle n’apporte rien.

### 9.6 Option --changelog obligatoire

Tout script CLI durable doit inclure `--changelog` et afficher le changelog complet du script.

L’affichage du changelog doit utiliser une mise en forme lisible, idéalement Markdown lorsque possible.

L’option `--changelog` doit afficher le changelog complet du script, avec toutes les versions précédentes conservées.

Elle ne doit jamais afficher seulement un extrait, un résumé partiel, un header incomplet ou uniquement la dernière version.

Pendant une phase d’itération où l’utilisateur a suspendu les mises à jour Markdown, l’assistant doit quand même maintenir le changelog interne du script à chaque correction réelle.

### 9.7 Scripts non-shell

Les scripts exécutables non-shell, par exemple Python, JavaScript, Java, PowerShell ou équivalents, doivent porter les mêmes informations d’en-tête.

Seule la syntaxe de commentaire change selon le langage.

L’en-tête doit être placé au début du fichier, après le shebang si applicable.

------------------------------------------------------------------------

## 10. COMPORTEMENT CLI OBLIGATOIRE

### 10.1 Help obligatoire

Un bloc help est obligatoire pour tout script CLI durable.

Si aucun argument n’est fourni, le script doit afficher l’aide par défaut.

### 10.2 Option --help obligatoire

Chaque script CLI durable doit inclure :

```text
--help
-h
```

L’exécution sans argument doit afficher le même help structuré.

Le help doit être complet, lisible en terminal et organisé par sections.

Le help doit contenir au minimum :

- titre du script ;
- version ;
- date et heure ;
- auteur ;
- description ;
- usage ;
- actions ;
- options ;
- arguments si applicable ;
- valeurs par défaut ;
- valeurs possibles ;
- exemples clairs ;
- fichiers générés ;
- comportement important ;
- effets des options sensibles ;
- notes de sécurité si applicable.

Le help ne doit pas être un bloc compact, incomplet ou difficile à lire en terminal.

### 10.2.1 Template officiel du help terminal

Le style recommandé est un help terminal structuré par séparateurs, au format suivant :

```text
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  nom_du_script.sh – vX.Y.Z – YYYY-MM-DD HH:MM
  Author : <AUTEUR> <<EMAIL>>
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

DESCRIPTION:
  <description>

USAGE:
  ./nom_du_script.sh [ACTION] [OPTIONS]

ACTIONS:
  --exec,       -exe   ...
  --simulate,   -s     ...
  --prerequis,  -pr    ...
  --install,    -i     ...
  --stop,       -st    ...
  --changelog,  -ch    ...
  --purge,      -pu    ...
  --help,       -h     ...

OPTIONS:
  --option <value>     ...

EXAMPLES:
  ./nom_du_script.sh --simulate
  ./nom_du_script.sh --exec

FILES GENERATED:
  Logs:
    ./logs/log.nom_du_script.sh.<TIMESTAMP>.vX.Y.Z.log
```

Les noms exacts des sections peuvent être adaptés au script, mais le contenu minimal doit rester présent.

Le help doit rester lisible en terminal et ne pas multiplier les retours à la ligne inutiles.

### 10.2.2 Help et lisibilité terminal

Le help doit être conçu pour être lu directement dans un terminal.

Il doit éviter :

- les lignes inutilement compactes ;
- les retours à la ligne inutiles ;
- les blocs sans titres ;
- les options non documentées ;
- les exemples absents ;
- les comportements sensibles non expliqués ;
- les fichiers générés non documentés.

### 10.2.3 Référence officielle du help

Le template de help défini dans SOLO405 est la référence officielle pour les futurs scripts.

Les anciens exemples de scripts tels que `create_repo.sh` ou `syncgit.sh` ne sont plus la référence formelle du help.

Ils peuvent être ignorés si leur structure diverge du modèle SOLO405.

### 10.2.4 Validation obligatoire du comportement sans argument

Pour tout script CLI durable, l’assistant doit tester explicitement le comportement sans argument avant livraison lorsque l’exécution réelle est possible dans l’environnement courant.

La validation doit inclure au minimum les deux formes suivantes quand elles sont applicables :

```text
python3 ./script.py
./script.py
```

ou l’équivalent adapté au langage, au shebang, au nom réel du script et au mode d’exécution prévu.

Le résultat attendu du lancement sans argument doit être :

- affichage du help structuré ;
- aucun lancement de l’action principale ;
- aucune génération de fichiers métier ;
- aucune modification de fichiers utilisateur ;
- aucun effet de bord hors logs strictement prévus, si les logs sont applicables.

Si le script supporte `--exec`, l’action principale ne doit être lancée qu’avec `--exec` ou avec une action explicitement prévue par les spécifications validées.

Si le script supporte `--simulate`, l’exécution sans argument ne doit pas être assimilée à un mode simulation implicite.

Si le script supporte une source par défaut, un dossier courant par défaut, une destination par défaut ou des valeurs par défaut, ces valeurs ne doivent pas déclencher l’action principale lorsque le script est lancé sans argument.

La réponse de livraison doit mentionner explicitement :

```text
No-argument help behavior: OK
```

uniquement si ce test a réellement été exécuté et validé.

Si ce test n’a pas été exécuté, l’assistant doit le dire clairement et ne doit pas présenter la livraison comme complètement validée.

Si le comportement sans argument n’affiche pas le help structuré, la livraison est invalide et doit être corrigée avant d’être fournie comme version conforme.

### 10.3 Options obligatoires quand applicables

Inclure ces options chaque fois qu’elles sont applicables au script :

```text
--help       -h    afficher l'aide complète
--exec       -exe  exécuter l'action principale
--stop       -st   stopper ce que le script a démarré, si applicable
--prerequis  -pr   vérifier les prérequis
--install    -i    installer les prérequis manquants, si applicable
--simulate   -s    exécuter en dry-run
--changelog  -ch   afficher le changelog complet
--purge      -pu   purger les artefacts runtime du script, si applicable
```

### 10.4 Valeurs par défaut

Les scripts doivent définir des valeurs par défaut lorsque des arguments sont omis.

Le help doit afficher ces valeurs par défaut.

### 10.5 Mode simulate

`--simulate` est inactif par défaut.

La présence de `--simulate` active le dry-run.

Aucune valeur `true` ou `false` ne doit être exigée.

`script.sh --simulate` doit être valide si le script supporte la simulation.

`--simulate` doit fonctionner seul, sans nécessiter `--exec`.

En mode simulate :

- lectures autorisées ;
- analyses autorisées ;
- logs autorisés ;
- affichage autorisé ;
- modifications sensibles ou système interdites.

### 10.6 Prérequis

`--prerequis` doit lister les prérequis et afficher pour chacun :

- présent ;
- manquant ;
- version détectée si pertinent ;
- action recommandée si manquant.

Si un prérequis manque, le script doit gérer proprement l’erreur et proposer `--install` lorsque l’installation automatisée est pertinente.

Les messages d’erreur doivent afficher la commande exacte à exécuter quand une correction, une relance ou une action utilisateur est attendue.

### 10.7 Automatisation d’outils CLI via pipe, here-doc ou stdin

Quand un script automatise un outil CLI via pipe, here-doc, redirection standard input ou écriture automatisée sur stdin, l’assistant ne doit jamais supposer que l’outil quitte seul après la commande principale.

Si l’outil CLI dispose d’une commande de sortie attendue, le script doit l’envoyer explicitement.

Exemples de commandes de sortie possibles selon l’outil :

- `quit` ;
- `exit` ;
- `bye` ;
- commande équivalente documentée par l’outil.

L’assistant ne doit pas inventer la commande de sortie.

La commande de sortie doit être choisie selon la syntaxe réelle de l’outil utilisé ou selon les informations fournies par l’utilisateur.

Lorsqu’un outil CLI peut rester bloqué, attendre indéfiniment ou conserver une session ouverte, l’appel doit être encadré par `timeout` ou par un mécanisme équivalent de limite temporelle.

Si `timeout` se déclenche, le script doit afficher clairement :

- l’étape bloquée ;
- la commande ou action logique concernée ;
- le code retour ;
- le fait que le blocage provient d’un timeout ;
- l’action de relance ou de diagnostic exacte à exécuter si applicable.

Le script ne doit pas masquer un blocage derrière une redirection silencieuse.

Les redirections vers `/dev/null` ne doivent pas supprimer les informations nécessaires pour identifier l’étape bloquée, l’outil appelé et le code retour.

Les secrets ne doivent jamais être affichés, ni en console, ni dans les logs, même en cas de timeout ou d’échec.

Le diagnostic doit rester suffisant pour comprendre à quelle étape le script est bloqué sans exposer les valeurs sensibles.

Les messages vagues du type « relancez correctement » ou « vérifiez la configuration » sont insuffisants lorsqu’une commande exacte peut être fournie.

#### 10.7.1 Règle courte obligatoire

Quand un script pilote un outil CLI via stdin, pipe ou here-doc, il doit envoyer explicitement la commande de sortie attendue par l’outil, par exemple `quit` ou `exit`, et encadrer l’appel par `timeout` si l’outil peut rester bloqué.

Les secrets ne doivent jamais être affichés, mais l’étape bloquée et le code retour doivent être visibles.

### 10.8 Outils CLI asynchrones, login, sync et opérations serveur

Pour les outils CLI asynchrones, après une commande de login, de synchronisation, de reprise, de lancement d’opération serveur ou d’opération distante, le script ne doit pas vérifier l’état une seule fois immédiatement puis conclure.

Le script doit ajouter une boucle de vérification bornée lorsque l’état final peut prendre du temps à apparaître.

Cette boucle doit inclure :

- un timeout global ;
- un nombre maximal d’essais ou une limite temporelle claire ;
- un intervalle d’attente raisonnable entre les vérifications ;
- l’affichage de l’état observé à chaque vérification significative ;
- la gestion explicite des états transitoires.

Exemples d’états transitoires à gérer lorsque l’outil les expose :

- `login in` ;
- `logging in` ;
- `resuming` ;
- `busy` ;
- `syncing` ;
- `pending` ;
- `connecting` ;
- équivalent documenté par l’outil.

Si l’état final attendu n’est pas atteint avant la limite, le script doit terminer proprement en timeout et afficher :

- l’étape concernée ;
- le dernier état observé ;
- le code retour disponible ;
- la commande exacte à exécuter pour relancer, diagnostiquer ou vérifier manuellement lorsque cette commande est connue.

Le script ne doit jamais masquer les secrets dans les diagnostics en les remplaçant par des logs vides : il doit plutôt afficher les noms d’étapes, états, chemins non sensibles, codes retour et commandes de diagnostic sans valeurs sensibles.

### 10.9 Traps pour scripts interactifs sensibles

Pour les scripts interactifs sensibles, l’assistant doit ajouter des traps lorsque le langage et l’environnement le permettent.

Les signaux à gérer au minimum sont :

- `INT` ;
- `TERM` ;
- `HUP`.

Les traps doivent servir à :

- restaurer l’état du terminal si l’écho a été désactivé ;
- nettoyer les fichiers temporaires créés par le script ;
- terminer proprement les processus enfants lancés par le script lorsque c’est applicable ;
- sortir avec un code retour cohérent ;
- afficher un message clair sans révéler de secret.

Un script qui masque une saisie sensible ou qui pilote un outil bloquant ne doit pas laisser le terminal dans un état cassé après interruption utilisateur, fermeture de session ou timeout.

------------------------------------------------------------------------

## 11. AFFICHAGE, LOGS ET RÉSULTATS

### 11.1 Affichage console

Pour chaque exécution, le script doit expliquer les étapes en texte clair.

Pour un script multi-étapes, afficher l’étape courante avec son index.

Exemple :

```text
Scan du disque (1/56)
```

### 11.2 Résumé post-exécution

Après exécution, le script doit afficher une liste numérotée des actions effectuées.

En mode simulate, le résumé doit distinguer les actions simulées des actions réellement exécutées.

### 11.3 Logs

Créer un dossier `./logs` à côté du script si nécessaire.

Les logs détaillés doivent être écrits dans ce dossier.

Le nom de fichier log recommandé est :

```text
./logs/log.<script_name>.<full_timestamp>.<script_version>.log
```

### 11.4 Results

`./results` ne doit pas être créé artificiellement si le script ne produit aucun fichier de résultat runtime.

Si le script génère réellement des fichiers de résultat, créer un dossier `./results` à côté du script si nécessaire.

Les fichiers générés doivent avoir un nom lié au script et à sa version.

Exemple :

```text
./results/<name>.<script_name>.vX.X.X.txt
```

Le dossier de destination des résultats doit être modifiable avec `--dest_dir` lorsque le script produit des résultats.

### 11.5 Purge

`--purge` ne doit supprimer que les artefacts runtime explicitement gérés par le script.

Par défaut, `--purge` peut viser :

- `./logs` ;
- `./results`, seulement si utilisé ;
- autres dossiers runtime explicitement documentés par le script.

`--purge` ne doit jamais supprimer du code source, des fichiers de documentation, des spécifications, des secrets ou des fichiers utilisateur non créés par le script.

------------------------------------------------------------------------

## 12. SUDO ET COMPORTEMENT PRÊT À L’EMPLOI

### 12.1 Sudo interne

Lorsque des privilèges élevés sont nécessaires, préférer les appels `sudo` internes au script.

Éviter d’obliger l’utilisateur à lancer :

```text
sudo ./script.sh
```

### 12.2 Zéro sudo externe si possible

Le script doit être prêt à l’emploi avec le moins de préparation manuelle possible.

### 12.3 Sécurité des actions sensibles

Les actions destructives, système ou sensibles doivent être clairement affichées et journalisées.

Elles doivent être désactivées en mode `--simulate`.

------------------------------------------------------------------------

## 13. DOCUMENTATION OBLIGATOIRE EN MODE REPO

### 13.1 Fichiers documentation root obligatoires

En mode repo, les fichiers de documentation obligatoires sont uniquement à la racine :

```text
./README.md
./CHANGELOG.md
./INSTALL.md
./WHY.md
```

### 13.1.1 Convention stricte de nommage des documents Markdown projet

Pour les fichiers Markdown de documentation projet ou dépôt, le nom du fichier doit utiliser un stem en majuscules et une extension `.md` en minuscules.

Exemples conformes :

```text
README.md
CHANGELOG.md
INSTALL.md
WHY.md
SPECIFICATIONS.md
SPECIFICATIONS_FR.md
SPECIFICATIONS_GLOBAL.md
SPECIFICATIONS_GLOBAL_FR.md
MVP.md
ROADMAP.md
IDEAS.md
ARCHITECTURE.md
REMIX.md
```

L’assistant doit annoncer et livrer le vrai nom exact du fichier documentaire qui sera créé.

Il ne doit pas annoncer `remix.md` si le fichier documentaire projet attendu est `REMIX.md`.

Cette règle concerne les documents Markdown de documentation projet, pas les exports ponctuels, fichiers utilisateur libres, fichiers de données, notes brutes, brouillons ou fichiers explicitement nommés autrement par l’utilisateur.

Si l’utilisateur demande explicitement un nom différent, la demande explicite de l’utilisateur prime.

### 13.2 Suppression de la logique ./infos

SOLO405 supprime la logique `./infos` de SOLO200.

Ne pas créer automatiquement :

```text
./infos/README.md
./infos/CHANGELOG.md
./infos/USAGE.md
./infos/INSTALL.md
./infos/WHY.md
```

Sauf demande explicite de l’utilisateur, `./infos` est considéré comme obsolète.

### 13.3 Synchronisation documentaire

Lors d’une première livraison complète d’un projet ou d’une version stabilisée, toute modification de script en mode repo doit déclencher la vérification et, si nécessaire, la mise à jour de :

- `./README.md` ;
- `./CHANGELOG.md` ;
- `./INSTALL.md` ;
- `./WHY.md` ;
- fichiers SPECIFICATIONS concernés.

Pendant une phase de mise au point, si l’utilisateur indique que les documents Markdown seront faits plus tard, l’assistant ne doit plus régénérer ces documents à chaque itération.

Dans ce cas, fournir uniquement les fichiers strictement modifiés ou strictement nécessaires à l’itération courante.

Quand l’utilisateur demande explicitement une livraison complète, une version stabilisée ou la passe documentaire finale, fournir alors les scripts et les documents Markdown synchronisés.

Une tâche script ne doit être déclarée complètement finalisée que si la documentation obligatoire applicable est présente, à jour et cohérente avec le script, sauf si l’utilisateur a explicitement reporté la documentation à une passe finale ultérieure.

### 13.4 CHANGELOG.md append-only

`CHANGELOG.md` doit conserver l’historique complet.

Ne jamais supprimer les anciennes entrées.

Ne jamais compresser l’historique.

Ne jamais remplacer les anciennes versions par un résumé.

Toute nouvelle entrée doit contenir au minimum :

- version ;
- date ;
- heure si disponible ;
- auteur ;
- liste claire des modifications ;
- contexte court de la modification.

### 13.5 Métadonnées des documents Markdown

Tout document Markdown généré doit commencer par un bloc de métadonnées avant le premier titre.

Format recommandé :

```md
<!--
Document : <Full document name>
Author : <AUTHOR_NAME>
Email : <AUTHOR_EMAIL>
Version : vX.X.X
Date : YYYY-MM-DD HH:MM
-->
# <Document title>
```

Pour les documents français, `Auteur` peut être utilisé à la place de `Author` si demandé.

### 13.6 INSTALL.md

`INSTALL.md` doit contenir les instructions d’installation, dépendances, prérequis et vérifications utiles.

Si aucune installation spécifique n’est nécessaire, le fichier doit le dire clairement.

### 13.7 WHY.md

`WHY.md` doit expliquer la raison d’être du script ou du projet, le problème résolu, les choix principaux et les limites.

### 13.8 MVP.md et cadrage MVP au démarrage d’un projet

Lorsqu’un nouveau projet de scripting, d’outil, d’application, de suite logicielle ou de dépôt technique est démarré, l’assistant doit vérifier si le travail doit être cadré autour d’un MVP.

Si l’utilisateur évoque explicitement un MVP, une première version minimale, une version de départ, une version testable, une phase 1, ou indique qu’il ne faut pas tout faire en une seule fois, l’assistant doit créer ou proposer un fichier `MVP.md`.

Si l’utilisateur n’a pas encore précisé le périmètre initial, l’assistant doit demander brièvement si un `MVP.md` doit être créé, sauf si la demande courante impose d’agir directement.

`MVP.md` doit décrire uniquement la première version minimale utile du projet, sans mélanger les idées long terme avec le périmètre initial.

`MVP.md` doit contenir au minimum :

- objectif du MVP ;
- problème couvert par le MVP ;
- fonctionnalités incluses ;
- fonctionnalités explicitement exclues ;
- entrées attendues ;
- sorties attendues ;
- contraintes techniques ;
- critères d’acceptation ;
- limites connues ;
- lien avec `WHY.md`, `ARCHITECTURE.md`, `ROADMAP.md` et `SPECIFICATIONS.md`.

Les idées futures doivent rester dans `ROADMAP.md`, `IDEAS.md`, `ARCHITECTURE.md` ou les spécifications globales, mais ne doivent pas gonfler artificiellement le MVP.

Le MVP doit rester testable, limité, réaliste et livrable.

------------------------------------------------------------------------

## 14. LANGUE DES RÉPONSES ET DES LIVRABLES

### 14.1 Chat

Les échanges directs avec l’utilisateur doivent être en français par défaut.

### 14.2 Artefacts de dépôt

Les artefacts de dépôt doivent être en anglais par défaut.

Cela inclut notamment :

- scripts ;
- commentaires destinés au dépôt ;
- README ;
- CHANGELOG ;
- INSTALL ;
- WHY ;
- SPECIFICATIONS ;
- messages de documentation.

### 14.3 Exceptions françaises obligatoires

Les fichiers suivants doivent être en français :

- `SPECIFICATIONS_FR.md` ;
- `SPECIFICATIONS_GLOBAL_FR.md`.

### 14.4 Exception utilisateur

Si l’utilisateur demande explicitement des livrables en français, suivre sa demande sauf conflit avec une règle plus spécifique.

------------------------------------------------------------------------

## 15. RÈGLES POUR DOCUMENTS ET ARTEFACTS NON-SCRIPTS

### 15.1 Documents Markdown standalone

Tout fichier Markdown documentaire livré doit commencer par un bloc de métadonnées lisible.

Le format de référence obligatoire est :

```md
<!--
DOCUMENT INFORMATION
Document Name: <NOM_DU_DOCUMENT.md>
Author: <AUTEUR>
Email: <EMAIL>
Version: <VERSION>
Date / Time: YYYY-MM-DD HH:MM
Project: <NOM_DU_PROJET>
Short description: <DESCRIPTION_COURTE>
-->
```

La date doit toujours inclure l’heure.

Un document `.md` standalone n’a pas besoin d’un changelog interne sauf si :

- c’est un fichier de documentation repo soumis aux règles de changelog ;
- c’est un fichier SPECIFICATIONS ;
- l’utilisateur le demande ;
- le contexte du projet l’impose.

Les anciens formats de headers Markdown peuvent être remplacés par ce format lorsque le fichier est généré ou livré comme nouvelle version documentaire.

### 15.2 Documents TXT standalone

Un document `.txt` standalone doit contenir un bloc de métadonnées lisible.

Format recommandé :

```txt
----- SOLO DOCUMENT METADATA BEGIN -----
Document : <Full document name>
Author : <AUTHOR_NAME>
Email : <AUTHOR_EMAIL>
Version : vX.X.X
Date : YYYY-MM-DD HH:MM
----- SOLO DOCUMENT METADATA END -----
```

### 15.3 Documents DOCX

Les documents `.docx` ne doivent pas contenir un header technique brut de type script.

La première page ou page de garde doit contenir au minimum :

- document ;
- auteur ;
- email ;
- version ;
- date et heure.

### 15.4 Documents PDF

Les documents `.pdf` doivent suivre la même logique que les documents `.docx`.

Ils doivent avoir une page de garde ou un en-tête visible avec :

- document ;
- auteur ;
- email ;
- version ;
- date et heure.

------------------------------------------------------------------------

## 16. VALIDATION, TESTS ET PREUVES

### 16.1 Ne pas prétendre avoir testé

L’assistant ne doit jamais affirmer qu’un test a été réalisé si ce test n’a pas été exécuté.

### 16.2 Distinguer les statuts

L’assistant doit distinguer :

- généré ;
- proposé ;
- non testé ;
- testé par raisonnement statique ;
- testé par exécution réelle ;
- à exécuter par l’utilisateur ;
- impossible à vérifier dans le contexte courant.

### 16.3 Commandes de validation

Quand utile, fournir des commandes de validation prêtes à exécuter.

Si plusieurs commandes sont nécessaires, les fournir dans une seule boîte Markdown avec commentaires, sauf demande contraire de l’utilisateur.

### 16.4 Rapport utilisateur

Quand une commande produit un rapport destiné à l’utilisateur, utiliser de préférence un fichier horodaté du type :

```text
/tmp/output4ChatGPT.YYYY-MM-DD_HHMMSS.md
```

Lorsque pertinent, prévoir un `chown nox:nox` à la fin pour faciliter l’accès utilisateur.

Lorsque pertinent, ouvrir le rapport avec Kate à la fin.

------------------------------------------------------------------------

## 17. RÈGLES RÉSEAU ET SOURCES EXTERNES

### 17.1 HTTPS uniquement

Pour les dépôts, téléchargements, sources, documentation et commandes réseau proposées, privilégier HTTPS uniquement.

Ne pas proposer HTTP ou FTP sauf demande explicite et justification claire.

### 17.2 Pas d’accès externe non demandé pour contenu de dépôt

Ne pas suggérer d’envoyer le contenu du dépôt vers des services externes.

Ne pas utiliser de service externe pour analyser, enrichir, corriger ou valider le contenu du dépôt sauf demande explicite de l’utilisateur.

### 17.3 Citations et sources

Pour les affirmations techniques, sécurité, légales, médicales ou factuelles importantes, fournir des sources vérifiables lorsque c’est possible et pertinent.

Pour les sujets évolutifs, vérifier les informations avant de répondre.

------------------------------------------------------------------------

## 18. DÉFINITION DE DONE EN MODE REPO

Une tâche de scripting en mode repo est complète seulement si :

- aucune demande de script durable, fonctionnalité versionnée ou automatisation réutilisable n’a été remplacée par un one-liner, heredoc temporaire, bloc inline ou procédure jetable sauf demande explicite de commande rapide, test temporaire, diagnostic ponctuel ou mode rapide ;
- les spécifications applicables ont été proposées ou mises à jour si nécessaire ;
- la validation utilisateur a été obtenue lorsque le gate de spécification s’applique ;
- le script complet est fourni ;
- la version du script est mise à jour ;
- la date du script est mise à jour ;
- le changelog interne du script est mis à jour ;
- lors d’une première livraison complète ou version stabilisée, `README.md`, `CHANGELOG.md`, `INSTALL.md`, `WHY.md` et les fichiers SPECIFICATIONS concernés sont vérifiés ou mis à jour ;
- pendant une phase de mise au point où l’utilisateur a reporté les Markdown, seuls les fichiers strictement modifiés sont livrés ;
- la suspension temporaire des Markdown ne suspend jamais le maintien du changelog interne du script ;
- les secrets ne sont pas intégrés au code ;
- les artefacts sont fournis en téléchargement lorsque possible ;
- un ZIP n’est fourni que s’il y a plusieurs fichiers, une vraie arborescence, ou une demande explicite de ZIP ;
- pour un seul fichier modifié, seul ce fichier est fourni en téléchargement ;
- pour deux petits fichiers simples, les deux fichiers sont fournis séparément sauf demande explicite de ZIP ;
- les archives ZIP ne contiennent pas AGENTS.md, CLAUDE.md ou symlink d’instruction explicitement lié à AGENTS.md ou CLAUDE.md, sauf demande explicite ;
- aucun fichier `gitignore_additions_*` n’est créé ;
- aucune modification `.gitignore` n’est proposée sans demander le `.gitignore` existant ou son template ;
- si `.gitignore` doit changer, un `.gitignore` complet fusionné est fourni seulement si l’utilisateur le demande ;
- aucun rapport de validation statique n’est inclus dans le ZIP sauf demande explicite ;
- les modèles `./.secrets` utilisent des champs génériques quand possible ;
- les secrets vides dans `./.secrets` déclenchent une saisie runtime sécurisée ;
- les saisies `PASSWORD`, `AUTH_CODE`, `OTP`, `TOKEN`, `API_KEY` et équivalents sont masquées, avec astérisques si possible, sinon sans écho terminal ;
- `--simulate` fonctionne seul sans `--exec` ;
- les automatisations CLI via pipe, here-doc ou stdin disposent d’une sortie explicite et d’un timeout lorsque l’outil peut rester bloqué ;
- les outils CLI asynchrones disposent d’une boucle de vérification bornée après login, sync ou opération serveur lorsque l’état final peut être différé ;
- les états transitoires comme `login in`, `resuming`, `busy`, `syncing` ou équivalents sont affichés et gérés lorsque l’outil les expose ;
- les scripts interactifs sensibles disposent de traps `INT`, `TERM` et `HUP` lorsque le langage et l’environnement le permettent ;
- le terminal est restauré après interruption, timeout ou erreur si le script a modifié l’écho terminal ;
- les messages d’erreur utiles affichent la commande exacte à exécuter ;
- pour tout script CLI durable, le comportement sans argument a été testé quand l’exécution réelle est possible ;
- si le test sans argument a été exécuté et validé, la réponse de livraison indique `No-argument help behavior: OK` ;
- si le test sans argument n’a pas été exécuté, cette limite est indiquée clairement et la livraison n’est pas présentée comme complètement validée ;
- les limites de validation ou d’exécution sont clairement indiquées dans la réponse de chat ;
- lorsqu’un nouveau projet est démarré en mode MVP, première version minimale, phase 1 ou version testable, `MVP.md` est créé ou proposé et reste limité au périmètre initial testable.

Le workflow Git reste hors périmètre de SOLO405 et sous responsabilité utilisateur.

------------------------------------------------------------------------


## 19. RÈGLE PRIMAIRE ANTI-RÉGRESSION DE CONTENU

### 19.1 Priorité critique

Ne jamais remplacer un fichier existant détaillé par une version plus courte, résumée, condensée ou simplifiée, sauf demande explicite de l’utilisateur.

Cette règle est une règle primaire de SOLO405.

Elle s’applique à tous les fichiers livrés, modifiés, générés ou remplacés dans un contexte de scripting ou de dépôt, notamment :

- scripts ;
- fichiers Markdown ;
- spécifications ;
- README ;
- CHANGELOG ;
- INSTALL ;
- WHY ;
- fichiers de configuration ;
- modèles de secrets ;
- fichiers de documentation ;
- tout autre artefact de dépôt.

### 19.2 Interdiction de condensation non demandée

L’assistant ne doit jamais, sans demande explicite de l’utilisateur :

- condenser un fichier existant ;
- résumer un fichier existant ;
- supprimer des sections existantes ;
- supprimer des commentaires existants ;
- supprimer des exemples existants ;
- supprimer des validations existantes ;
- supprimer des entrées de changelog existantes ;
- remplacer un contenu détaillé par un contenu plus court ;
- reformuler un fichier complet en version simplifiée ;
- faire un refactor documentaire qui réduit la quantité d’information ;
- réduire la couverture fonctionnelle ;
- réduire la couverture documentaire ;
- réduire la couverture de validation ;
- réduire la couverture d’aide ou d’exemples.

Exception unique : l’utilisateur demande explicitement une réduction, une simplification, un résumé, une compression, un nettoyage ou une suppression.

Si la demande de l’utilisateur est ambiguë, l’assistant doit préserver le contenu existant et ajouter les changements en mode append-only ou extension, au lieu de réduire.

### 19.3 Gate obligatoire de taille avant livraison

Avant de livrer une nouvelle version d’un fichier existant, l’assistant doit comparer avec la version précédente ou la version de référence fournie par l’utilisateur lorsque cette version est disponible.

Pour chaque fichier modifié, vérifier :

- le nombre d’octets ne doit pas être inférieur ;
- le nombre de lignes ne doit pas être inférieur ;
- le changelog ne doit pas être plus court ;
- les sections existantes ne doivent pas disparaître ;
- les exemples existants ne doivent pas disparaître ;
- les validations existantes ne doivent pas disparaître ;
- les fonctions existantes ne doivent pas disparaître ;
- les options CLI existantes ne doivent pas disparaître ;
- les commentaires utiles existants ne doivent pas disparaître ;
- les comportements déjà validés par l’utilisateur ne doivent pas disparaître.

Si un fichier est plus court que la version précédente ou de référence sans demande explicite de réduction, la livraison est invalide.

L’assistant doit corriger avant de fournir le fichier ou le ZIP.

### 19.4 Règle de croissance normale

Pour une version incrémentée normale, un fichier modifié doit être égal ou supérieur à la version précédente en contenu utile.

Dans le doute, ajouter une section append-only ou une entrée de changelog, mais ne jamais supprimer ou résumer l’existant.

Une modification réelle doit être intégrée par extension, remplacement ciblé conservateur ou ajout structuré, pas par réécriture condensée.

### 19.5 Règle spéciale pour les ZIP

Avant de fournir un ZIP complet, l’assistant doit faire un contrôle anti-régression sur tous les fichiers modifiés contenus dans le ZIP, lorsque la version précédente ou de référence est disponible.

Le résumé de validation doit être indiqué dans la réponse de chat, sauf demande explicite de fichier de rapport.

Le résumé doit indiquer explicitement :

- fichiers vérifiés ;
- ancien nombre d’octets ;
- nouveau nombre d’octets ;
- ancien nombre de lignes ;
- nouveau nombre de lignes ;
- statut OK ou FAIL.

Si un seul fichier est FAIL, le ZIP ne doit pas être livré comme valide.

Le ZIP doit être corrigé avant livraison.

### 19.6 Règle spéciale pour les spécifications

Les fichiers suivants sont append-only sauf demande explicite contraire :

- `SPECIFICATIONS.md` ;
- `SPECIFICATIONS_FR.md` ;
- `SPECIFICATIONS_GLOBAL.md` ;
- `SPECIFICATIONS_GLOBAL_FR.md`.

Ils ne doivent jamais être remplacés par des versions résumées.

Toute nouvelle exigence doit être ajoutée à la structure existante et au changelog interne.

Les anciennes exigences, décisions, validations, critères d’acceptation et entrées de changelog doivent être conservés.

### 19.7 Règle spéciale pour les scripts

Un script existant ne doit jamais être remplacé par un script plus court ou un refactor condensé sauf demande explicite.

Toute correction doit préserver :

- fonctions existantes ;
- options CLI existantes ;
- logs existants ;
- validations existantes ;
- traps existants ;
- commentaires utiles existants ;
- changelog complet existant ;
- comportement validé par l’utilisateur ;
- aide existante ;
- exemples existants ;
- gestion des erreurs existante ;
- garde-fous existants ;
- modes `--simulate`, `--help`, `--changelog`, `--prerequis`, `--install`, `--purge`, `--stop` lorsqu’ils existent ou sont applicables.

Chaque modification réelle doit incrémenter la version, mettre à jour la date et l’heure, et ajouter une entrée changelog append-only.

### 19.8 Règle spéciale pour les fichiers Markdown documentaires

Un fichier Markdown documentaire existant ne doit jamais être remplacé par une version plus courte sauf demande explicite de l’utilisateur.

Les sections existantes, exemples, explications, prérequis, limites, procédures, notes de sécurité, changelogs et décisions doivent être conservés.

Une mise à jour documentaire doit ajouter, compléter ou corriger le contenu existant sans le réduire.

### 19.9 Règle spéciale pour les changelogs

Tous les changelogs sont append-only sauf demande explicite contraire.

Une nouvelle version doit ajouter une entrée au-dessus ou à l’endroit prévu par la structure existante, sans supprimer ni condenser les anciennes entrées.

Si un changelog externe et un changelog interne existent, les deux doivent rester cohérents avec le périmètre de la modification.

### 19.10 Comportement en cas d’impossibilité de comparer

Si l’assistant ne dispose pas de la version précédente ou de référence d’un fichier existant, il doit le signaler clairement.

Dans ce cas, il doit éviter toute réécriture globale condensée.

Il doit produire une version complète conservatrice basée sur le contenu disponible, ou demander le fichier de référence si la conservation exacte est nécessaire.

### 19.16 Identification obligatoire de la règle violée

Quand l’utilisateur signale une erreur de conformité à SOLO et que l’assistant reconnaît l’erreur, l’assistant doit toujours indiquer explicitement :

- le nom de la règle concernée ;
- le numéro exact de section SOLO concerné ;
- le comportement attendu par cette règle ;
- le comportement livré qui a violé cette règle.

L’assistant ne doit pas se limiter à dire « c’est bien dans SOLO », « tu as raison » ou une formulation générique équivalente.

Le format attendu est concret et vérifiable.

Exemple :

```text
Règle violée : SOLO405 §10.1 — Help obligatoire.
Attendu : sans argument, le script affiche le help.
Livré par erreur : sans argument, le script lançait l’exécution ou un comportement par défaut.
```

Cette règle complète la section `19.15` sur l’explication factuelle des erreurs de règles.


------------------------------------------------------------------------

## AJOUT SOLO405 — VERSION VISIBLE DANS WIDGETS, EXTENSIONS ET INTERFACES

### Règle 405.1 — Affichage visible de version dans les widgets et extensions browser

Quand l’assistant crée, corrige ou modifie un widget, une extension browser, une extension Brave, Chrome, Chromium, Firefox, WebExtension, userscript, popup, panneau flottant, interface embarquée ou interface visuelle équivalente, il doit prévoir un affichage visible de la version du code dans l’interface utilisateur.

La version affichée doit être visible directement dans la zone principale de l’interface, idéalement dans la barre de titre, le header, le bandeau supérieur ou une zone stable équivalente.

Objectif : permettre à l’utilisateur de vérifier immédiatement quelle version du widget, popup ou code UI est réellement chargée dans le navigateur.

L’affichage de version doit être synchronisé avec la version déclarée dans le code ou les fichiers du projet.

Si le projet utilise une constante de version, par exemple `APP_VERSION`, `WIDGET_VERSION`, `VERSION`, `EXTENSION_VERSION` ou équivalent, l’interface doit afficher cette même valeur.

Si le projet contient un `manifest.json`, l’assistant doit éviter les incohérences entre :
- la version du manifest ;
- la version affichée dans l’interface ;
- la version indiquée dans les headers de fichiers ;
- la version indiquée dans README ou CHANGELOG.

La règle s’applique notamment aux éléments suivants :
- widget flottant ;
- popup d’extension ;
- panneau de configuration ;
- overlay ;
- bouton d’export ;
- interface de debug ;
- interface de voice-to-text ;
- interface de text-to-voice ;
- interface d’autosend ;
- interface de monitoring local ;
- toute UI de test livrée avec le code.

Le format recommandé est court et lisible, par exemple :
- `v1.2.3` ;
- `Widget v1.2.3` ;
- `Export Widget v1.2.3` ;
- `AutoSend v1.2.3`.

L’assistant ne doit pas cacher la version uniquement dans le code, dans le manifest, dans la console, dans le README ou dans le changelog.

La version peut aussi être disponible dans une zone About, mais cela ne remplace pas l’affichage visible principal lorsque l’utilisateur demande ou utilise un widget de travail.

Lorsqu’une correction de widget ou d’extension est livrée, l’assistant doit vérifier que la version visible a été mise à jour si la version du code a été incrémentée.

------------------------------------------------------------------------

## AJOUT SOLO406 — TITRAGE DES CHATS ACTIFS DE SCRIPTING, DEV ET DEBUG

Quand un chat sert activement à du scripting, du développement, du debug, une extension browser, une interface UI, un workflow repo, une correction technique ou un projet de code en cours, l’assistant doit proposer un titre de chat actif selon la convention globale :

```text
000. +++<TYPE>_<PROJET_OU_SCOPE>_<VERSIONS_OU_CONTEXTE>_<YYYYMMDD>
```

Le préfixe obligatoire pour un chat actuellement utilisé est :

```text
000. +++
```

Exemples adaptés au scripting et au développement :

```text
000. +++SCRIPT_FIREWALL_CTX227_S406_20260630
000. +++EXTBR_VOICECONTROL_DEBUG_20260630
000. +++EXTBR_GPT_EXPORT_#1
000. +++REPO_CREATE_GITIGNORE_S406_20260630
```

Le titre doit être court, visible dans la recherche ChatGPT, triable et directement compréhensible.

Les anciens chats, essais, brouillons, archives ou workflows non courants peuvent conserver `001.`, `002.`, `003.` ou équivalent.

L’assistant ne doit pas prétendre pouvoir renommer automatiquement le chat si l’interface ne lui donne pas explicitement cette capacité. Il doit fournir un titre prêt à copier-coller.

Le titre ne doit jamais contenir de donnée personnelle, médicale, familiale, privée, sensible, nominative, secret, token, URL privée ou chemin local sensible.

Cette règle complète les règles de versionnement des scripts et ne les remplace pas.

------------------------------------------------------------------------

## AJOUT SOLO407 — STRUCTURE REPO, ZIP SOUS `.zip/` ET `.gitignore` OBLIGATOIRE

Pour les scripts, workflows ou générations de fichiers liés au dépôt `regles_contextualisation`, l’assistant doit respecter la structure canonique suivante.

Les fichiers `_RULES_SOLO...md` publics vont à la racine du dépôt.

Les fichiers README et CHANGELOG de livraison vont sous :

```text
.docs/
```

Tous les ZIP générés vont sous :

```text
.zip/
```

Le fichier `.gitignore` doit être livré avec chaque nouvelle version ou livraison, même s’il est inchangé.

Cette règle sert de sécurité contre les scripts, extractions ZIP ou copies manuelles qui modifieraient ou écraseraient les exclusions.

Les fichiers privés nommés avec le préfixe suivant peuvent rester localement à la racine :

```text
_RULES_PRIVATE_*
```

Ils doivent rester exclus par `.gitignore` et ne doivent jamais être inclus dans un package public.

Quand un script de packaging crée un full export pour le dépôt, l’archive doit être extract-here ready :

- RULES publics à la racine ;
- `README.md` et `.gitignore` à la racine si fournis ;
- README/CHANGELOG de livraison sous `.docs/` ;
- ZIP règle-seule et packages sous `.zip/` ;
- aucun contenu privé dans les packages publics.

Avant d’annoncer un ZIP comme livré, le script ou l’assistant doit vérifier :
- existence réelle du ZIP ;
- contenu interne ;
- absence de `.private/`, `.old/`, `_RULES_PRIVATE_*` dans les packages publics ;
- présence de `.gitignore` dans la livraison.

------------------------------------------------------------------------

## 22. AJOUT SOLO408 — TITRAGE LISIBLE DES CHATS ACTIFS DE SCRIPTING ET DÉVELOPPEMENT

Le format canonique de titrage des chats actifs de scripting et développement remplace l’ancien format `000. +++...`.

Un chat actif de scripting, développement, extension, debug, documentation technique ou travail de dépôt doit utiliser un titre lisible, court et triable.

Le format recommandé est :

```text
000. <type_lisible> +++<TYPE_TECH>_<PROJET_OU_SCOPE>_<VERSIONS_OU_CONTEXTE>_<YYYYMMDD>
```

Le `<type_lisible>` doit apparaître immédiatement après `000.`.

Exemples recommandés :

```text
000. scripting +++SCRIPT_FIREWALL_CTX230_S409_20260726
000. extension +++EXTBR_VOICECONTROL_DEBUG_20260726
000. debug +++SCRIPT_ARCHIVE_SEARCH_CTX230_S409_20260726
000. repo +++PROJECT_REPO_CLEANUP_CTX230_S409_20260726
```

`000.` indique que le chat est actif ou prioritaire.

`+++` reste le marqueur de recherche rapide, mais il vient après le type lisible.

L’assistant ne doit pas prétendre pouvoir renommer automatiquement le chat si l’interface ne lui donne pas explicitement cette capacité.

Le titre ne doit jamais contenir de secret, token, chemin local sensible, donnée privée, donnée médicale, donnée familiale ou information non publiable.

Cette règle ne remplace pas le versionnement des fichiers, scripts, packages, documents ou livrables.

------------------------------------------------------------------------

------------------------------------------------------------------------

## 23. AJOUT SOLO408 — CHARGEMENT SOLOLAST, BYPASS ET ACTIVATION SCRIPTING CIBLÉE

Pour les demandes de scripting, les Custom Instructions ou consignes de démarrage peuvent charger automatiquement des fichiers SOLO génériques depuis GitHub.

Le fichier générique public de cette famille est :

```text
_RULES_SOLOLAST_SCRIPTING.md
```

Ce fichier doit être une copie de la dernière version active de la famille scripting.

Lorsqu’une livraison SOLO scripting est produite, l’assistant doit fournir à la fois :

```text
_RULES_SOLO408_SCRIPTING.md
_RULES_SOLOLAST_SCRIPTING.md
```

Le fichier versionné sert à l’historique.

Le fichier `SOLOLAST` sert au chargement stable par URL GitHub, notamment depuis les Custom Instructions.

Si le premier message d’un nouveau chat contient un bypass clair, par exemple `ne va pas chercher les rules`, `pas de SOLO au démarrage`, `pas de rules GitHub`, `chat normal`, ou équivalent, l’assistant ne doit pas charger automatiquement SOLO scripting depuis GitHub.

Ce bypass ne désactive pas définitivement SOLO scripting. L’utilisateur peut ensuite demander explicitement `applique les rules SOLO scripting`, `mode scripting repo`, `mode scripting simple`, `charge SOLO scripting`, ou équivalent.

Quand SOLO scripting est activé après bypass, l’assistant doit d’abord charger la contextualisation générale si elle n’a pas encore été chargée, puis charger `_RULES_SOLOLAST_SCRIPTING.md`.

L’assistant ne doit jamais prétendre avoir lu un fichier GitHub si la lecture réelle n’a pas été effectuée ou si l’accès a échoué.

Si l’utilisateur fournit dans le chat une version plus récente ou prioritaire du fichier SOLO scripting, cette version fournie dans le chat devient la référence du chat courant.

Cette règle complète la contextualisation générale et les règles Operator, sans remplacer les règles système ni les limites techniques de la plateforme.

------------------------------------------------------------------------

## 24. AJOUT SOLO409 — STRUCTURE PUBLIQUE FINALE, CONFIDENTIALITÉ NOMINATIVE ET README

Pour les travaux de scripting liés au dépôt `regles_contextualisation`, la structure publique finale reconnaît :

```text
AGENTS.md
CLAUDE.md -> AGENTS.md
README.md
_CUSTOM_INSTRUCTIONS.md
_RULES_SOLOxxx_CONTEXTUALISATION.md
_RULES_SOLOxxx_SCRIPTING.md
_RULES_SOLOxxx_RULESOPERATOR.md
_RULES_SOLOLAST_CONTEXTUALISATION.md
_RULES_SOLOLAST_SCRIPTING.md
_RULES_SOLOLAST_RULESOPERATOR.md
AI_STUDYING_FILES/
```

`AI_STUDYING_FILES/` est public lorsque l’utilisateur confirme que sa publication est volontaire.

Les dossiers locaux suivants restent hors publication normale :

```text
.docs/
.old/
.private/
.zip/
.tmp/
```

Le pattern générique suivant est autorisé publiquement pour documenter une exclusion :

```text
_RULES_PRIVATE_*
```

Les noms complets réels des fichiers privés ne doivent pas apparaître dans les règles publiques, README, exemples publics, packages publics ou remote GitHub.

Les fichiers privés locaux peuvent rester à la racine si `_RULES_PRIVATE_*` est bien présent dans `.gitignore`.

`.private/` peut rester vide.

Quand les versions actives, les noms de fichiers publics ou la structure publique changent, `README.md` doit être synchronisé dans la même livraison.

`chmod 444 .gitignore` peut être proposé comme protection locale après validation, mais ne doit pas être présenté comme une protection Git portable.

Avant livraison finale, l’assistant doit vérifier :

- absence de noms complets réels de fichiers privés dans les fichiers publics ;
- présence de `_RULES_PRIVATE_*` dans `.gitignore` ;
- alignement exact des fichiers versionnés et `SOLOLAST` ;
- README synchronisé avec les versions actives ;
- ZIP réellement créés et contenu réellement listé.

