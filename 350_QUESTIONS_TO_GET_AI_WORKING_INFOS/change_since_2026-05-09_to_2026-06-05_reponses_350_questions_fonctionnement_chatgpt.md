# Change since baseline - questionnaire 350 questions fonctionnement ChatGPT

**Version :** 1.0  
**Date de génération :** 2026-06-05  
**Baseline analysée :** `reponses_350_questions_fonctionnement_chatgpt(1).md`  
**Date interne affichée par la baseline :** 2026-05-09  
**Modèle / produit concerné :** ChatGPT / GPT-5.5 Thinking, mémoire, contexte, fichiers, outils, confidentialité  
**Portée demandée :** ne lister que les questions dont la réponse doit changer ou être corrigée/fortement nuancée.

---

## Avertissement de méthode

Le fichier fourni ne semble pas être une réponse de septembre 2025. Il affiche lui-même :

- **Version :** 1.0
- **Date de génération :** 2026-05-09
- **Modèle concerné :** ChatGPT / GPT-5.5 Thinking

Donc ce rapport compare le document fourni du **2026-05-09** avec l'état documenté et observable au **2026-06-05**.  
Si tu veux une comparaison stricte avec septembre 2025, il faut fournir le vrai fichier de septembre 2025.

J'ai gardé uniquement les entrées dont la réponse change, doit être corrigée, ou doit être nettement nuancée. Les questions absentes de ce rapport sont considérées comme **sans changement matériel identifié** dans le cadre de cette passe.

---

## Synthèse courte

**Nombre d'entrées listées :** 33 questions + 1 point de métadonnées.  

Les changements principaux sont :

1. les limites de contexte et de modèles sont plus instables et plus dépendantes du plan que la baseline ne le laisse entendre ;
2. les pages officielles OpenAI contiennent quelques incohérences entre elles, notamment sur les fenêtres de contexte, Canvas et la rétention des fichiers ;
3. la mémoire/personnalisation s'est enrichie : Memory Sources, meilleur usage des chats passés, fichiers et Gmail connecté, mémoire de projet ;
4. Temporary Chat reste privé pour la mémoire/personnalisation, mais peut encore utiliser un contexte limité pour sûreté/sécurité et suit les Custom Instructions ;
5. les fichiers sont désormais à traiter comme un système séparé de la conversation dans certains documents : Library, quotas, limites par projet, stockage séparé ;
6. la hiérarchie d'autorité doit être formulée plus précisément : la terminologie publique actuelle parle de **Root > System > Developer > User > Guideline**.

---

## Point de métadonnées hors numérotation

### Metadata-001 - Date de référence du fichier

**Constat baseline :** l'utilisateur parle d'une réponse de septembre 2025, mais le fichier fourni indique 2026-05-09.

**Correction actuelle :** ce rapport ne peut pas prétendre comparer septembre 2025 à juin 2026. Il compare la baseline effectivement fournie, datée 2026-05-09, à l'état connu au 2026-06-05.

**Impact :** important. Toute conclusion "depuis septembre" doit être relue si un vrai export septembre 2025 est fourni.

**Sources :** fichier fourni ; [O1], [O2], [O3].

---

# Changements par question

## Q001 - Limite maximale exacte de tokens / fenêtre de contexte d'entrée

**Ancienne réponse résumée :** GPT-5.5 Thinking = 256K tokens pour les niveaux payants, avec 128K entrée + 128K sortie ; Pro = 400K avec 272K entrée + 128K sortie.

**Réponse actuelle corrigée :** je ne répondrais plus avec une limite unique sans préciser **plan + mode + page officielle consultée**. La page GPT-5.5 générale indique encore 256K pour Thinking sur les niveaux payants et 400K en Pro, mais d'autres pages officielles donnent des valeurs différentes pour Business/Enterprise/Edu. Pour Enterprise/Edu, une page indique GPT-5.5 Instant 128K et GPT-5.5 Thinking 196K. Pour Business, une autre indique 128K pour Instant/Thinking et 272K pour Pro.

**Changement :** correction de prudence. Il faut dire : "limite plan-dépendante, non déductible avec certitude depuis le chat, et documentation officielle actuellement non parfaitement homogène".

**Sources :** [O1], [O11], [O12].

---

## Q005 - Variation des limites entre modèles

**Ancienne réponse résumée :** les limites varient selon modèle et plan ; Claude ne me concerne pas directement.

**Réponse actuelle corrigée :** la réponse reste vraie, mais elle doit maintenant ajouter que plusieurs anciens modèles ChatGPT ont été retirés ou sont en période de retrait. Les comparaisons doivent donc être datées. Les anciens chats peuvent être routés vers des équivalents actuels, et les sorties peuvent changer quand on continue un ancien chat.

**Changement :** ajout obligatoire de datation et de statut de disponibilité des modèles.

**Sources :** [O1], [O8], [O11], [O12].

---

## Q006 - Différences selon l'abonnement

**Ancienne réponse résumée :** les plans influencent limites, uploads, mémoire et contexte ; Free, Go, Plus, Pro, Business, Enterprise.

**Réponse actuelle corrigée :** oui, mais il faut maintenant inclure plus explicitement : limites de messages GPT-5.5 par plan, accès manuel à Thinking selon plan, Pro/Business sous guardrails d'abus, différences de fenêtres de contexte par plan, Free limité sur fichiers, et distinctions liées aux ads pour Free/Go.

**Changement :** réponse plus précise et plus plan-dépendante.

**Sources :** [O1], [O7], [O9], [O11], [O12].

---

## Q019 - PDF : texte, images et multimodal

**Ancienne réponse résumée :** un PDF est traité par extraction de texte ; les pages scannées/figures/images peuvent nécessiter OCR ou analyse visuelle ; documents texte plafonnés à 2M tokens.

**Réponse actuelle corrigée :** il faut distinguer les plans. La FAQ File Uploads indique que **ChatGPT Enterprise** supporte Visual Retrieval pour les PDF. Pour les autres plans et pour les documents non-PDF, la FAQ dit que la recherche est textuelle et que les images embarquées sont ignorées/discarded. Une page Enterprise séparée décrit en plus un mécanisme 110K tokens + index privé pour gros fichiers multimédias.

**Changement :** correction majeure. Je ne dirais plus simplement "les images peuvent être analysées" sans préciser le plan et le type de fichier.

**Sources :** [O4], [O5].

---

## Q028 - Requête ou fichier dépassant les limites

**Ancienne réponse résumée :** une requête trop grosse peut être rejetée, tronquée ou nécessiter un découpage ; fichiers soumis à limites de taille/tokens.

**Réponse actuelle corrigée :** il faut ajouter les limites documentées actuelles : 512 MB par fichier, 2M tokens par document texte, environ 50 MB pour CSV/spreadsheets, 20 MB par image, 80 fichiers toutes les 3 heures pour utilisateurs non-Free, 3 fichiers par jour pour Free, 25 GB par utilisateur, 100 GB par organisation, et limites de fichiers par projet selon plan.

**Changement :** réponse inchangée dans le principe, mais incomplète sans ces chiffres.

**Sources :** [O4].

---

## Q031 - Nombre de systèmes de mémoire distincts

**Ancienne réponse résumée :** contexte actif, mémoire enregistrée, référence historique, instructions personnalisées, fichiers/outils, tâches/rappels.

**Réponse actuelle corrigée :** il faut ajouter explicitement : **Memory Sources**, **Library files**, **fichiers de projet**, **mémoire de projet / project-only memory**, et usage possible de contexte depuis Gmail connecté quand disponible. Ce ne sont pas forcément des "mémoires" au même sens, mais ce sont des sources de contextualisation/personnalisation.

**Changement :** ajout de nouvelles sources ou surfaces de contextualisation à nommer.

**Sources :** [O2], [O3], [O10], [O13].

---

## Q043 - Mémoire de préférences utilisateur distincte

**Ancienne réponse résumée :** les préférences peuvent être stockées comme mémoire enregistrée ou déduites via l'historique.

**Réponse actuelle corrigée :** il faut préciser les différences de plan : selon la documentation "What is Memory?", Saved Memories et Chat History sont disponibles pour Plus/Pro, tandis que les comptes Free sont limités aux Saved Memories. Certaines interfaces montrent un seul toggle Memory ou deux toggles distincts.

**Changement :** précision plan-dépendante.

**Sources :** [O10], [O2].

---

## Q058 - Durée de rétention des mémoires/chats/fichiers

**Ancienne réponse résumée :** saved memories jusqu'à suppression ; historique/chats avec règles de conservation propres.

**Réponse actuelle corrigée :** il faut distinguer plus fermement chats, saved memories et fichiers. La page "Chat and File Retention" dit que les chats restent jusqu'à suppression manuelle, puis suppression système sous 30 jours sauf exceptions. Elle dit aussi que les fichiers uploadés dans une conversation peuvent être stockés dans la Library et gérés séparément des chats. La FAQ File Uploads contient une formulation moins nette sur les fichiers liés au chat ; il faut donc signaler cette tension documentaire.

**Changement :** correction/nuance importante sur les fichiers et la Library.

**Sources :** [O6], [O4], [O2].

---

## Q063 - Attention croisée entre contexte actuel et historique

**Ancienne réponse résumée :** pas d'attention magique sur toute l'archive ; les éléments d'historique doivent être récupérés/injectés.

**Réponse actuelle corrigée :** la base reste vraie, mais l'état actuel permet de dire plus concrètement que ChatGPT peut mieux récupérer du contexte depuis chats passés, saved memories, fichiers et Gmail connecté selon disponibilité. Ce n'est toujours pas une attention directe sur toute l'archive.

**Changement :** clarification : récupération historique officiellement améliorée.

**Sources :** [O3], [O2].

---

## Q086 - Contextualisation selon source

**Ancienne réponse résumée :** je traite différemment utilisateur, web, fichiers, outils.

**Réponse actuelle corrigée :** il faut ajouter que l'interface peut maintenant exposer des **Memory Sources** : saved memories, past chats, custom instructions, et parfois fichiers/emails selon plan/région/connexion. Ces sources peuvent être corrigées, supprimées ou marquées comme pertinentes/non pertinentes.

**Changement :** ajout de transparence utilisateur via Memory Sources.

**Sources :** [O2], [O3].

---

## Q087 - Niveau de confiance/fiabilité associé aux sources

**Ancienne réponse résumée :** pas toujours de score visible ; hiérarchie qualitative des sources.

**Réponse actuelle corrigée :** il faut ajouter que Memory Sources donne une visibilité partielle sur les éléments ayant informé une réponse personnalisée, mais ne montre pas forcément tous les facteurs qui ont façonné la réponse.

**Changement :** ajout de traçabilité partielle, sans score complet.

**Sources :** [O2], [O3].

---

## Q109 - Accès à l'historique complet des conversations

**Ancienne réponse résumée :** pas d'accès automatique à tout l'historique ; seulement éléments pertinents via mémoire/référence historique ou fichiers/export.

**Réponse actuelle corrigée :** réponse toujours vraie, mais elle doit mentionner que la récupération des chats passés est officiellement améliorée et que Memory Sources peut montrer certains chats utilisés. Le point critique reste : je n'ai pas accès librement à toute ton archive.

**Changement :** nuance : meilleure récupération, pas accès complet.

**Sources :** [O2], [O3].

---

## Q111 - Conversations archivées/supprimées

**Ancienne réponse résumée :** il peut y avoir chats archivés ou supprimés non accessibles ; archivage surtout UI ; suppression selon politiques.

**Réponse actuelle corrigée :** la page de rétention précise que les chats archivés suivent les mêmes règles de rétention que les chats non archivés. La documentation mémoire indique aussi que supprimer ou archiver un chat peut empêcher ChatGPT de le référencer, sauf mémoire déjà sauvegardée issue de ce chat.

**Changement :** précision importante : archive n est pas suppression, mais peut affecter la référence historique selon la doc mémoire.

**Sources :** [O6], [O10].

---

## Q115 - Indexation de l'historique

**Ancienne réponse résumée :** l'indexation exacte n'est pas publique ; la référence historique récupère des informations utiles.

**Réponse actuelle corrigée :** l'index exact reste non public, mais Memory Sources rend une partie du résultat visible : l'utilisateur peut voir certains past chats/saved memories/custom instructions/fichiers/emails ayant aidé la personnalisation.

**Changement :** transparence partielle nouvelle, mais pas accès à l'index complet.

**Sources :** [O2], [O3].

---

## Q121 - Décision des conversations passées pertinentes

**Ancienne réponse résumée :** sélection par demande actuelle, préférences, entités, sujet, pertinence estimée.

**Réponse actuelle corrigée :** il faut ajouter que l'utilisateur peut maintenant agir sur certaines sources via Memory Sources : supprimer, corriger, ou marquer comme pertinente/non pertinente. Cela peut améliorer les futures sélections.

**Changement :** ajout de contrôle utilisateur sur la pertinence historique.

**Sources :** [O2], [O3].

---

## Q125 - Décroissance temporelle / pertinence des anciens chats

**Ancienne réponse résumée :** récence et fréquence peuvent compter ; modèle exact non public.

**Réponse actuelle corrigée :** réponse globalement inchangée, mais il faut ajouter que les nouvelles Memory Sources ne montrent pas tous les facteurs et peuvent n'afficher qu'un petit nombre de chats pertinents même si davantage a été recherché/référencé.

**Changement :** nuance de transparence : l'absence d'une source affichée ne prouve pas qu'elle n'a pas influencé le résultat.

**Sources :** [O2].

---

## Q126 - Hiérarchie de priorité entre sources

**Ancienne réponse résumée :** système/sécurité, développeur, demande actuelle, fichiers/outils, mémoire, connaissance interne, web si consulté.

**Réponse actuelle corrigée :** la hiérarchie opérationnelle reste globalement correcte pour ce chat, mais la formulation publique actuelle du Model Spec ajoute un niveau supérieur nommé **Root**, puis **System**, **Developer**, **User**, **Guideline**. Il faut aussi intégrer que les sorties d'outils peuvent avoir une autorité implicite quand cela correspond à l'intention utilisateur et évite les effets indésirables.

**Changement :** correction terminologique et hiérarchique.

**Sources :** [O8].

---

## Q128 - Priorité absolue des instructions système

**Ancienne réponse résumée :** les instructions système ont priorité absolue sur tout.

**Réponse actuelle corrigée :** je ne formulerais plus cela comme absolu dans le vocabulaire public OpenAI. La formulation actuelle est : **Root > System > Developer > User > Guideline**. Dans un chat, les instructions système restent au-dessus de l'utilisateur, de la mémoire et des outils, mais il existe publiquement un niveau Root au-dessus du système.

**Changement :** correction conceptuelle importante.

**Sources :** [O8].

---

## Q155 - Équilibre mémoire immédiate vs historique

**Ancienne réponse résumée :** le contexte immédiat prime ; historique/mémoire selon pertinence.

**Réponse actuelle corrigée :** l'équilibre doit inclure les améliorations de mémoire : ChatGPT peut mieux tirer du contexte des chats passés, saved memories, fichiers et Gmail connecté. Mais pour une consigne actuelle explicite, le message courant et les sources fournies dans le tour restent prioritaires.

**Changement :** historique/fichiers/Gmail ont plus de poids pratique qu'avant dans la personnalisation.

**Sources :** [O3], [O2].

---

## Q168 - Apprentissage des préférences de communication

**Ancienne réponse résumée :** préférences apprises via instructions, corrections, mémoire et historique.

**Réponse actuelle corrigée :** il faut ajouter le réglage Personality/Base Style and Tone, qui fonctionne avec saved memories et custom instructions. Une mémoire de préférence peut réduire ou override le style de personnalité sélectionné.

**Changement :** ajout de la couche Personality dans la réponse.

**Sources :** [O14], [O8].

---

## Q171 - Évolution des préférences dans le temps

**Ancienne réponse résumée :** nouvelles corrections/préférences peuvent remplacer les anciennes.

**Réponse actuelle corrigée :** il faut ajouter que Memory Sources permet de corriger, supprimer, ou marquer certaines sources comme non pertinentes, ce qui donne un moyen utilisateur plus concret de gérer l'évolution des préférences.

**Changement :** ajout d'un contrôle UI exploitable.

**Sources :** [O2], [O3].

---

## Q194 - Suppression d'un message/chat et traces restantes

**Ancienne réponse résumée :** supprimer un chat ne supprime pas forcément une saved memory dérivée ; il faut supprimer la mémoire et le chat d'origine pour retrait complet de la mention.

**Réponse actuelle corrigée :** garder cette réponse, mais ajouter la distinction fichiers : selon la page de rétention, les fichiers uploadés pendant une conversation peuvent rester dans la Library et être gérés séparément ; supprimer un chat ne supprime pas forcément les fichiers actifs de la Library.

**Changement :** ajout important pour les fichiers uploadés.

**Sources :** [O6], [O2], [O4].

---

## Q210 - Contrôle de ce qui peut être mémorisé

**Ancienne réponse résumée :** désactiver mémoire, gérer saved memories, Temporary Chat, data controls, export/suppression.

**Réponse actuelle corrigée :** il faut ajouter deux nuances : selon le compte, les réglages peuvent être un toggle Memory unique ou des toggles séparés Saved memory / Chat history ; les versions avec ads ont des contrôles d'ads personalization distincts, et les actions sur ads ne sont pas ajoutées à la mémoire.

**Changement :** nouveaux contrôles ou contrôles à mentionner selon plan/région.

**Sources :** [O10], [O9].

---

## Q211 - Mode privé / incognito / Temporary Chat

**Ancienne réponse résumée :** Temporary Chat ne référence/crée pas de memories, n'apparaît pas dans l'historique, n'est pas utilisé pour améliorer les modèles ; peut être conservé jusqu'à 30 jours pour sécurité.

**Réponse actuelle corrigée :** il faut ajouter : Temporary Chat peut encore utiliser des informations de conversations antérieures pour des buts limités de sûreté/sécurité, et continue de suivre les Custom Instructions si elles sont activées.

**Changement :** nuance importante : "privé" ne veut pas dire absence totale de tout contexte de sûreté.

**Sources :** [O7], [O10].

---

## Q212 - Consulter ce qui est mémorisé

**Ancienne réponse résumée :** Manage Memories pour saved memories ; export/Privacy Portal pour données plus larges.

**Réponse actuelle corrigée :** il faut ajouter Memory Sources : dans certaines réponses personnalisées, l'utilisateur peut voir des sources telles que past chats, saved memories, custom instructions, fichiers ou emails connectés selon plan/région. Mais Memory Sources peut ne pas afficher tous les facteurs.

**Changement :** ajout d'une visibilité partielle par réponse.

**Sources :** [O2], [O3].

---

## Q213 - Export des données

**Ancienne réponse résumée :** export possible ; lien email expirant après 24h.

**Réponse actuelle corrigée :** il faut ajouter que les exports de chat ne sont pas disponibles pour ChatGPT Business ou Enterprise via cette procédure, que l'export est disponible sur Free/Plus/Pro, que l'export peut prendre jusqu'à 7 jours, et que seule la demande d'export la plus récente est honorée.

**Changement :** réponse à compléter fortement.

**Sources :** [O15].

---

## Q280 - Identifier quelle source a contribué à quelle partie d'une réponse

**Ancienne réponse résumée :** oui si sources présentes ; sinon signaler l'absence de source visible.

**Réponse actuelle corrigée :** il faut dire : oui partiellement. Memory Sources peut exposer certains éléments de personnalisation, mais ne constitue pas un journal complet des facteurs ayant façonné la réponse et ne remplace pas des citations web/fichier explicites pour une analyse factuelle.

**Changement :** nuance de traçabilité.

**Sources :** [O2], [O3].

---

## Q293 - Feedback utilisateur et évolution de la mémoire

**Ancienne réponse résumée :** feedback influence comportement local, mémoire si activée, et processus d'amélioration selon contrôles.

**Réponse actuelle corrigée :** il faut ajouter que l'utilisateur peut marquer des Memory Sources comme pertinentes ou non pertinentes, corriger/supprimer des saved memories, supprimer des chats référencés, et que les interactions avec ads ne sont pas ajoutées à la mémoire. Si un utilisateur utilise "Ask ChatGPT" sur une ad, la conversation peut ensuite être référencée si Reference chat history est activé.

**Changement :** ajout de feedback direct sur les sources mémorielles et distinction ads/memory.

**Sources :** [O2], [O9].

---

## Q296 - Mémoire interne et APIs/services externes

**Ancienne réponse résumée :** les outils externes fournissent des données au tour de conversation ; elles ne deviennent pas automatiquement mémoire persistante.

**Réponse actuelle corrigée :** garder le principe, mais ajouter deux points : les données de Gmail connecté et fichiers peuvent maintenant servir davantage à la personnalisation quand disponibles ; les sorties d'outils peuvent recevoir une autorité implicite dans certains cas alignés avec l'intention utilisateur. Attention aussi : les notes de version indiquent que Canvas n'est plus disponible dans GPT-5.5 Instant/Thinking, tandis qu'une page GPT-5.5 plus ancienne/contradictoire le liste encore pour Thinking.

**Changement :** outillage et autorité des outils à nuancer ; documentation officielle contradictoire sur Canvas.

**Sources :** [O3], [O8], [O16], [O1].

---

## Q300 - Synchronisation avec systèmes externes

**Ancienne réponse résumée :** pas de synchronisation automatique générale ; il faut relire/reconnecter/rechercher.

**Réponse actuelle corrigée :** la réponse reste vraie, mais il faut intégrer les Projects : les projets ont une mémoire intégrée des chats et fichiers créés/uploadés dans le projet. Les connected apps dans les projets peuvent être utilisées, mais la doc précise que Google Drive ne supporte pas la synchronisation préalable lorsqu'il est ajouté dans un projet.

**Changement :** ajout de la mémoire de projet et limite spécifique Google Drive.

**Sources :** [O13].

---

## Q311 - Accès aux stockages cloud

**Ancienne réponse résumée :** possible si connecteur disponible et autorisé ; sinon non.

**Réponse actuelle corrigée :** réponse toujours vraie, mais elle doit mentionner les connected apps dans les projets et la confirmation possible pour rechercher hors projet. La disponibilité dépend des apps connectées, du plan, de la région et des permissions.

**Changement :** précision projet/connecteurs.

**Sources :** [O13], [O3].

---

## Q312 - Indexation des fichiers cloud

**Ancienne réponse résumée :** les fichiers cloud peuvent être indexés par connecteur ou analysés quand ouverts ; détails dépendants du connecteur.

**Réponse actuelle corrigée :** il faut préciser que, dans les projets, Google Drive ne supporte pas le sync/pré-indexing quand ajouté dans un projet ; il peut encore être recherché/accessé, mais pas synchronisé à l'avance pour retrieval.

**Changement :** limite concrète à ajouter.

**Sources :** [O13].

---

## Q313 - Synchronisation bidirectionnelle

**Ancienne réponse résumée :** lecture plus fréquente que l'écriture ; certaines actions peuvent créer/modifier selon outils ; pas de synchro automatique à supposer.

**Réponse actuelle corrigée :** la réponse reste correcte, mais elle doit maintenant ajouter : les projets/fichiers/connecteurs peuvent avoir une mémoire de projet, mais cela ne signifie pas une synchronisation bidirectionnelle générale avec un cloud externe. Google Drive dans projet est un exemple explicite de non-sync préalable.

**Changement :** nuance importante pour éviter de confondre mémoire de projet et synchronisation cloud.

**Sources :** [O13].

---

# Questions proches mais non listées comme changement matériel

Je n'ai pas listé les questions dont la réponse reste substantiellement identique, par exemple :

- Q003 : la sortie maximale de 128K pour GPT-5.5 Thinking reste cohérente avec la page GPT-5.5 générale, même si les limites pratiques restent plan/interface dépendantes.
- Q024, Q027, Q106, Q287 : je ne vois toujours pas de compteur exact fiable de contexte restant.
- Q048, Q051, Q053, Q069, Q072, Q150, Q266 : les détails internes exacts restent non publiés.
- Q156 à Q167 : il n'y a toujours pas d'apprentissage neuronal/fine-tuning personnel en temps réel.
- Q278 : je ne peux toujours pas fournir une chaîne de pensée interne complète ; je peux fournir un résumé des sources et critères.
- Q347 à Q350 : versioning/rollback des structures internes de mémoire non public.

---

# Sources consultées

- **[O1] GPT-5.5 in ChatGPT** - https://help.openai.com/en/articles/11909943-gpt-5-1-in-chatgpt
- **[O2] Memory FAQ** - https://help.openai.com/en/articles/8590148-memory-faq
- **[O3] ChatGPT Release Notes** - https://help.openai.com/en/articles/6825453-chatgpt-release-notes
- **[O4] File Uploads FAQ** - https://help.openai.com/en/articles/8555545-file-uploads-faq
- **[O5] Optimizing File Uploads in ChatGPT Enterprise** - https://help.openai.com/en/articles/10029836-optimizing-file-uploads-in-chatgpt-enterprise
- **[O6] Chat and File Retention Policies in ChatGPT** - https://help.openai.com/en/articles/8983778-chat-and-file-retention-policies-in-chatgpt
- **[O7] Temporary Chat FAQ** - https://help.openai.com/en/articles/8914046-temporary-chat-faq
- **[O8] Model Release Notes** - https://help.openai.com/en/articles/9624314-model-release-notes
- **[O9] Ads in ChatGPT** - https://help.openai.com/en/articles/20001047-ads-in-chatgpt
- **[O10] What is Memory?** - https://help.openai.com/en/articles/8983136-what-is-memory
- **[O11] ChatGPT Enterprise and Edu - Models & Limits** - https://help.openai.com/en/articles/11165333-chatgpt-enterprise-and-edu-models-limits
- **[O12] ChatGPT Business - Models & Limits** - https://help.openai.com/en/articles/12003714-chatgpt-business-models-limits
- **[O13] Projects in ChatGPT** - https://help.openai.com/en/articles/10169521-projects-in-chatgpt
- **[O14] Customizing Your ChatGPT Personality** - https://help.openai.com/en/articles/11899719-customizing-your-chatgpt-personality
- **[O15] How do I export my ChatGPT history and data?** - https://help.openai.com/en/articles/7260999-how-do-i-export-my-chatgpt-history-and-data
- **[O16] GPTs in ChatGPT** - https://help.openai.com/en/articles/8554407-gpts-in-chatgpt

---

## Conclusion

Oui, je sais faire ce type de comparaison. Sur ce fichier précis, les plus gros changements ne sont pas dans les réponses purement théoriques sur les LLM, mais dans les couches produit ChatGPT : modèles disponibles, limites par plan, mémoire enrichie, Memory Sources, fichiers/Library/projets/connecteurs, Temporary Chat, ads et hiérarchie publique d'autorité.

La correction critique à garder : **ne pas traiter ce fichier comme septembre 2025**, car son propre en-tête indique **2026-05-09**.
