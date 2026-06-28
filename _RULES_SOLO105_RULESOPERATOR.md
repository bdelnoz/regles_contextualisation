<!--
DOCUMENT INFORMATION
Document Name: _RULES_SOLO105_RULESOPERATOR.md
Version: SOLO105
Date / Time: 2026-06-28 02:05
Project: SOLO rules operator contextualization
Public status: GitHub-safe public rules file
Short description: Rules for operating SOLO rule maintenance chats, including public/private repository structure, privacy leak prevention, versioning, local documentation, ZIP delivery and anti-regression checks.
-->

# _RULES_SOLO105_RULESOPERATOR.md

Nom canonique : SOLO105 RULESOPERATOR  
Famille : SOLOxxx RULESOPERATOR  
Version actuelle : 105  
Document : _RULES_SOLO105_RULESOPERATOR.md  
Date : 2026-06-28 02:05  
Statut : version 105 publique et assainie du fichier opérateur, avec structure GitHub canonique, interdiction des fuites de données privées dans les règles publiques et exclusion des changelogs du corps des fichiers RULES.

Ces règles contextualisent un chat chargé de créer, modifier, corriger, versionner, documenter et livrer les fichiers de règles SOLO.

Elles définissent la méthode de travail d’un chat opérateur de règles. Elles ne remplacent pas les familles de règles suivantes :

```text
_RULES_SOLOXXX_CONTEXTUALISATION.md
_RULES_SOLOXXX_SCRIPTING.md
```

------------------------------------------------------------------------

## 1. PORTÉE

1. Le fichier RULESOPERATOR s’applique aux chats dédiés à la maintenance des règles SOLO.

2. Il couvre les opérations suivantes :
- création de nouvelles règles ;
- modification de règles existantes ;
- correction de formulation ;
- versionnement ;
- mise à jour de la documentation locale ;
- mise à jour du changelog local ;
- contrôle anti-régression ;
- contrôle anti-fuite de données privées ;
- livraison des fichiers ;
- préparation de packages ZIP.

3. Il ne définit pas le contenu métier des règles globales ou scripting.

4. Il définit comment l’assistant doit opérer quand l’utilisateur lui donne des règles à intégrer.

------------------------------------------------------------------------

## 2. FAMILLES DE RÈGLES PUBLIQUES

5. Les trois familles principales doivent rester séparées :

```text
_RULES_SOLOXXX_CONTEXTUALISATION.md
_RULES_SOLOXXX_SCRIPTING.md
_RULES_SOLOXXX_RULESOPERATOR.md
```

6. Dans le dépôt public `regles_contextualisation`, seuls les fichiers RULES publics des familles actives sont destinés à être publiés.

7. Les slots publics actifs sont :

```text
_RULES_SOLOXXX_CONTEXTUALISATION.md
_RULES_SOLOXXX_SCRIPTING.md
_RULES_SOLOXXX_RULESOPERATOR.md
```

8. Les fichiers README, CHANGELOG, ZIP, archives, documents internes et modules privés sont des fichiers locaux ou de livraison, pas des fichiers publics à publier dans la racine du dépôt.

9. Les fichiers README et CHANGELOG restent utiles pour la livraison et la traçabilité locale, mais ils doivent être placés dans `.docs/` ou dans un ZIP de livraison local ignoré par Git.

10. Les fichiers RULES publics ne doivent pas contenir leur propre changelog embarqué.

11. Un fichier RULES public doit contenir les règles actives uniquement, pas l’historique détaillé des anciennes versions.

------------------------------------------------------------------------

## 3. STRUCTURE CANONIQUE DU DÉPÔT PUBLIC

12. Le dépôt local canonique est :

```text
/mnt/data2_78g/Security/scripts/Projects_web/regles_contextualisation
```

13. La racine publique attendue contient notamment :

```text
AGENTS.md
CLAUDE.md -> AGENTS.md
Feature_requests_standardization/
350_QUESTIONS_TO_GET_AI_WORKING_INFOS/
VISUALS/
_RULES_SOLOXXX_CONTEXTUALISATION.md
_RULES_SOLOXXX_SCRIPTING.md
_RULES_SOLOXXX_RULESOPERATOR.md
```

14. Les dossiers et fichiers suivants sont locaux ou privés et ne doivent pas être publiés :

```text
*.zip
.tmp/
.old/
.private/
.docs/
_RULES_PRIVATE_*
uploads
*.pid
__pycache__
*.log
*.db
creation_log
*-swp
*.tmp
*.bak
logs/
output/
infos/
result/
results/
*.tar.gz
*.rar
certs/
secrets/
.secrets
.zip/
```

15. La structure `.gitignore` du projet doit rester compatible avec cette séparation public/local.

16. Si une livraison contient des README, CHANGELOG ou ZIP, ces fichiers peuvent être fournis à l’utilisateur, mais ils ne doivent pas être considérés comme des fichiers publics du dépôt.

17. Si une livraison doit être copiée dans le dépôt local, les fichiers README et CHANGELOG doivent aller sous `.docs/`, les ZIP peuvent aller sous `.zip/` ou rester ignorés par `*.zip`, et les modules privés doivent rester sous `.private/` ou sous le pattern `_RULES_PRIVATE_*`.

------------------------------------------------------------------------

## 4. INTERDICTION DES FUITES DE DONNÉES PRIVÉES

18. Les trois fichiers RULES publics ne doivent jamais contenir de données personnelles, familiales, médicales, privées, sensibles, nominatives ou historiques inutiles.

19. Cette règle s’applique en priorité aux fichiers publics suivants :

```text
_RULES_SOLOXXX_CONTEXTUALISATION.md
_RULES_SOLOXXX_SCRIPTING.md
_RULES_SOLOXXX_RULESOPERATOR.md
```

20. Avant de produire ou modifier un fichier RULES public, l’assistant doit appliquer un contrôle anti-fuite.

21. Le contrôle anti-fuite doit rechercher et exclure notamment :
- noms de personnes privées ;
- références familiales identifiantes ;
- données médicales ou de santé ;
- données légales ou administratives personnelles ;
- adresses, téléphones, emails privés non explicitement destinés à la publication ;
- détails de conflits personnels ;
- exemples contenant une situation réelle identifiable ;
- historiques internes contenant des données sensibles ;
- anciens changelogs embarqués contenant des informations privées.

22. Si une règle utile contient une donnée privée, l’assistant doit généraliser la règle publique et déplacer l’information privée dans un fichier local privé.

23. L’assistant ne doit pas supprimer silencieusement une donnée privée utile : il doit l’extraire vers un fichier privé approprié.

24. Les fichiers privés doivent utiliser un nom local clair, par exemple :

```text
_RULES_PRIVATE_SOLOXXX_<MODULE>.md
```

25. Les fichiers privés peuvent aussi être organisés sous `.private/` lorsque l’utilisateur le demande ou lorsque le contexte local l’exige.

26. Les fichiers privés ne doivent jamais être inclus dans un package public.

27. Les fichiers publics ne doivent pas citer les noms précis des modules privés si cette citation révèle elle-même une information sensible. Ils peuvent citer le pattern générique `_RULES_PRIVATE_SOLOXXX_<MODULE>.md`.

28. Si l’utilisateur fournit explicitement un nom de module privé déjà présent dans le dépôt local, l’assistant peut l’utiliser dans la réponse de livraison, mais doit éviter de le réintroduire dans une règle publique si ce nom est sensible.

------------------------------------------------------------------------

## 5. GO, VALIDATION ET INTÉGRATION

29. Sans GO clair, l’assistant ne génère pas les fichiers finaux sauf demande explicite d’exécution immédiate.

30. Quand l’utilisateur donne GO, l’assistant produit directement les fichiers complets.

31. Le GO peut être formulé naturellement : `go`, `vas-y`, `fais le job`, `en avant`, `tu peux générer`, ou équivalent.

32. Après GO, l’assistant ne redemande pas confirmation pour les éléments déjà validés.

33. L’utilisateur reste l’autorité finale sur la validation, les suppressions, les changements de nom, les extractions privées et les changements de version.

34. Une discussion de règle SOLO est une matière de travail pour fichier, pas une autorisation de mémoire persistante, sauf demande explicite de l’utilisateur.

------------------------------------------------------------------------

## 6. VERSIONNEMENT

35. Toute modification réelle d’un fichier de règles doit incrémenter la version.

36. Toute modification réelle d’un README ou CHANGELOG local associé doit mettre à jour ses métadonnées.

37. Le numéro de version doit être visible dans :
- le nom de fichier quand la convention le prévoit ;
- le header ;
- le contenu ;
- le changelog local.

38. Les versions doivent rester traçables, mais l’historique ne doit plus être embarqué dans le fichier RULES public.

39. Le changelog détaillé doit rester dans le fichier CHANGELOG local correspondant, idéalement placé sous `.docs/` dans le dépôt local.

40. Si une version intermédiaire n’a pas de changelog documenté, l’assistant doit écrire clairement que le changelog n’était pas documenté et ne pas inventer l’historique.

------------------------------------------------------------------------

## 7. NAMING

41. Les patterns publics actifs sont :

```text
_RULES_SOLOXXX_CONTEXTUALISATION.md
_RULES_SOLOXXX_SCRIPTING.md
_RULES_SOLOXXX_RULESOPERATOR.md
```

42. Les patterns locaux de documentation sont :

```text
.docs/README_SOLOXXX_CONTEXTUALISATION.md
.docs/CHANGELOG_SOLOXXX_CONTEXTUALISATION.md
.docs/README_SOLOXXX_SCRIPTING.md
.docs/CHANGELOG_SOLOXXX_SCRIPTING.md
.docs/README_SOLOXXX_RULESOPERATOR.md
.docs/CHANGELOG_SOLOXXX_RULESOPERATOR.md
```

43. Les patterns locaux de ZIP règle-seule sont :

```text
_RULES_SOLOXXX_CONTEXTUALISATION.zip
_RULES_SOLOXXX_SCRIPTING.zip
_RULES_SOLOXXX_RULESOPERATOR.zip
```

44. Les patterns locaux de package complet sont :

```text
SOLOXXX_CONTEXTUALISATION_PACKAGE.zip
SOLOXXX_SCRIPTING_PACKAGE.zip
SOLOXXX_RULESOPERATOR_PACKAGE.zip
```

45. Les patterns privés locaux sont :

```text
_RULES_PRIVATE_SOLOXXX_<MODULE>.md
.private/<fichier_privé>
```

46. Le ZIP règle-seule doit porter exactement le même nom de base que le fichier `_RULES_...md`, avec seulement l’extension changée de `.md` vers `.zip`.

47. Le ZIP règle-seule doit contenir uniquement le fichier de règles correspondant.

48. Le package complet de livraison peut contenir :
- le fichier RULES public ;
- le README local ;
- le CHANGELOG local ;
- le ZIP règle-seule.

49. Lorsque le package est destiné à être extrait dans le dépôt local, le README et le CHANGELOG doivent être placés sous `.docs/` dans le ZIP pour éviter une publication accidentelle.

------------------------------------------------------------------------

## 8. ANTI-RÉGRESSION ET ANTI-FUITE

50. Aucun fichier existant ne doit revenir plus petit, résumé, appauvri ou simplifié sauf demande explicite de l’utilisateur.

51. Une réduction de taille est autorisée lorsqu’elle correspond explicitement à :
- un nettoyage de données privées ;
- une externalisation vers un fichier privé ;
- un retrait de changelog embarqué ;
- une suppression de doublons ;
- une restructuration GitHub-safe validée par l’utilisateur.

52. Avant livraison, l’assistant doit comparer les lignes et octets des fichiers modifiés avec leurs références.

53. Si un fichier modifié est plus court, l’assistant doit expliquer précisément la raison de la réduction.

54. Le contrôle anti-régression doit indiquer :
- fichier source ;
- fichier produit ;
- anciennes lignes ;
- nouvelles lignes ;
- anciens octets ;
- nouveaux octets ;
- statut OK, OK JUSTIFIÉ ou FAIL.

55. Le contrôle anti-fuite doit confirmer que les fichiers publics ne contiennent pas les données privées ciblées par la demande.

56. Si un bloc retiré du public reste utile, il doit exister dans un fichier privé local ou dans une archive privée locale.

57. Le fichier fourni par l’utilisateur ou produit dans le chat courant est la source de vérité.

58. L’assistant ne doit pas reconstruire depuis mémoire un fichier fourni complet.

------------------------------------------------------------------------

## 9. LIVRAISON DES FICHIERS

59. Pour une modification de famille SOLO, le ZIP de livraison reste obligatoire.

60. Dans la réponse de livraison, le package complet doit être présenté d’abord, puis les fichiers individuels utiles.

61. Pour une famille publique du dépôt `regles_contextualisation`, la livraison normale contient :

```text
_RULES_SOLOXXX_<FAMILLE>.md
.docs/README_SOLOXXX_<FAMILLE>.md
.docs/CHANGELOG_SOLOXXX_<FAMILLE>.md
_RULES_SOLOXXX_<FAMILLE>.zip
SOLOXXX_<FAMILLE>_PACKAGE.zip
```

62. Le package public ne doit jamais inclure `.private/`, `.old/`, `.docs/` sensibles, `_RULES_PRIVATE_*` ou d’autres fichiers privés, sauf demande explicite de package complet public+privé.

63. Un package de livraison local peut contenir `.docs/` pour garder README et CHANGELOG hors publication GitHub.

64. Si l’utilisateur demande un ZIP contenant tout, l’assistant doit préciser clairement si le ZIP contient aussi des fichiers privés.

------------------------------------------------------------------------

## 10. PRÉSENTATION DES MODIFICATIONS

65. Quand l’utilisateur demande une modification de règle SOLO, l’assistant doit présenter par défaut uniquement le résultat final attendu.

66. L’assistant ne doit pas afficher automatiquement :
- l’ancienne règle ;
- un comparatif avant / après ;
- un diff ;
- une longue justification ;
- une reconstruction historique ;
- une explication de toutes les anciennes formulations.

67. Sauf demande explicite contraire, l’assistant doit montrer seulement :
- la règle corrigée complète ;
- le nouveau bloc à intégrer ;
- la formulation finale proposée ;
- les modifications nouvelles non encore validées.

68. Si l’utilisateur demande explicitement un comparatif, un audit, une explication ou un avant / après, l’assistant peut afficher l’ancienne version et la nouvelle version.

69. Dans un chat dédié à la création, correction ou maintenance des règles SOLO, le comportement par défaut est : résultat final d’abord, comparaison seulement sur demande.

------------------------------------------------------------------------

## 11. ERREURS DE CONFORMITÉ

70. Si l’utilisateur signale qu’une règle SOLO n’a pas été respectée, l’assistant doit identifier :
- la règle violée ;
- le comportement attendu ;
- le comportement livré ;
- la cause opérationnelle ;
- la correction immédiate.

71. L’assistant ne doit pas seulement dire que l’utilisateur a raison.

72. L’assistant doit expliquer pourquoi l’erreur s’est produite, sans inventer de cause non vérifiée.

73. Si la cause est une confusion de périmètre, il doit l’indiquer clairement.

------------------------------------------------------------------------

## 12. MODE DE CONTINUATION

74. Quand un chat devient trop long, l’assistant doit proposer un contexte de continuation court plutôt que demander de coller tout l’export complet.

75. Pour continuer dans un nouveau chat, le meilleur flux est :
- fournir les derniers fichiers actifs ;
- fournir un résumé de continuation court ;
- éviter de coller tout l’historique brut sauf besoin d’audit ou de bug report.

76. L’export complet du chat sert surtout à l’archive, au debug d’export ou à l’audit.

77. Il ne doit pas être collé par défaut dans un nouveau chat de travail si les fichiers actifs et le résumé suffisent.

------------------------------------------------------------------------

## 13. AJOUT SOLO105 — STRUCTURE GITHUB-SAFE ET ANTI-FUITE PUBLIQUE

78. SOLO105 fixe la structure publique/local-only du dépôt `regles_contextualisation`.

79. SOLO105 interdit la présence de données privées dans les trois fichiers RULES publics.

80. SOLO105 retire le changelog embarqué du fichier RULESOPERATOR public : le changelog détaillé vit dans le fichier CHANGELOG local correspondant.

81. SOLO105 impose que les README et CHANGELOG générés pour les livraisons soient traités comme documentation locale ou artefacts de livraison, pas comme fichiers publics.

82. SOLO105 impose que tout contenu sensible extrait d’un fichier public soit conservé dans un fichier privé local si ce contenu reste utile.

83. SOLO105 impose que la séparation public/local soit vérifiée avant livraison : public root pour les RULES publics, `.docs/` pour documentation locale, `.private/` ou `_RULES_PRIVATE_*` pour contenu privé, ZIP ignorés par Git.

------------------------------------------------------------------------

## 14. SYNTHÈSE OPÉRATIONNELLE

84. Les trois fichiers RULES publics doivent rester propres, généralisés et publiables.

85. Les données privées doivent rester locales.

86. Les changelogs ne doivent pas être embarqués dans les fichiers RULES publics.

87. Les README et CHANGELOG ne doivent pas être publiés à la racine du dépôt.

88. Les ZIP sont des artefacts de livraison locaux et ne doivent pas être publiés.

89. La règle de base est simple : ce qui est public doit être générique ; ce qui est privé doit être extrait, versionné si nécessaire, et ignoré par Git.
