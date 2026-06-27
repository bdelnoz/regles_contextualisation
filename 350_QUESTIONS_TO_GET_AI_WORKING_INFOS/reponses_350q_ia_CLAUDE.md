# Réponses aux 350 Questions sur les Mécanismes d'IA
*Claude Sonnet 4.6 — Mai 2026 — Format ultra-compact*

---

## CAT 1 : Limites des Tokens

**Q1.** Fenêtre de contexte : ~200 000 tokens (Sonnet 4.6).
**Q2.** Oui, inclut input (messages + system prompt) + output accumulé.
**Q3.** Output max par réponse : ~8 192 tokens (variable selon modèle).
**Q4.** La limite s'applique à la fenêtre active totale, pas aux conversations archivées.
**Q5.** Haiku 4.5 / Sonnet 4.6 / Opus 4.6 : tous ~200k tokens de contexte. Vérifier docs.anthropic.com pour valeurs exactes.
**Q6.** La fenêtre technique est identique, mais les quotas d'usage (messages/heure) varient selon l'abonnement (Free < Pro < Team < Enterprise).
**Q7.** Via un tokenizer BPE (Byte Pair Encoding) propriétaire Anthropic.
**Q8.** BPE — Byte Pair Encoding.
**Q9.** Oui. Langues sous-représentées dans le training → plus de tokens pour la même idée.
**Q10.** BPE construit un vocabulaire optimisé pour les langues dominantes dans le corpus. Morphologie complexe + rareté = sous-mots plus fragmentés.
**Q11.** Espaces généralement fusionnés avec le mot suivant (token = " mot").
**Q12.** Ponctuation : souvent token séparé, parfois fusionnée selon contexte.
**Q13.** Emoji : 1 à 3+ tokens selon complexité Unicode (emoji composés = plus).
**Q14.** Caractères spéciaux : 1-3 tokens, parfois fallback en bytes UTF-8 individuels.
**Q15.** Même tokenizer, mais vocabulaire de sous-mots différent en pratique (keywords, opérateurs = tokens dédiés).
**Q16.** Oui. Images découpées en tiles (512×512 ou 1024×1024) → ~1000-2000 tokens selon résolution.
**Q17.** Non. Le format (JPG/PNG) ne change pas le coût — la résolution et le contenu importent.
**Q18.** Haute résolution → plus de tiles → plus de tokens. Réduction automatique au-delà des limites.
**Q19.** PDF : texte extrait → tokenisé normalement. Images dans PDF → traitées comme images.
**Q20.** .docx : texte extrait et tokenisé normalement.
**Q21.** Excel → converti texte (CSV-like) → coût proportionnel à la quantité de cellules/données.
**Q22.** Métadonnées comptées uniquement si incluses dans le payload transmis à l'API.
**Q23.** Les messages les plus anciens sont tronqués ou la requête est rejetée selon l'implémentation.
**Q24.** Non, pas d'avertissement natif exposé à l'utilisateur dans claude.ai.
**Q25.** Oui, troncation côté serveur : sliding window sur l'historique ou erreur de dépassement.
**Q26.** FIFO : les messages les plus anciens sont supprimés en premier.
**Q27.** Non, pas de détection proactive native dans le chat standard.
**Q28.** Requête rejetée avec erreur API ou tronquée à la limite d'entrée.
**Q29.** Résumé des tours anciens, compression du system prompt, chunking de documents.
**Q30.** Priorité de conservation : instructions système > contexte récent > contexte ancien.

---

## CAT 2 : Différentes Mémoires

**Q31.** 4 types sur claude.ai : (1) contexte conversation active, (2) userMemories persistantes, (3) connaissances de training, (4) résultats d'outils (web, fichiers).
**Q32.** Mémoire de travail = contexte session active (volatile). Persistante = userMemories stockées entre sessions.
**Q33.** Non, pas de buffer tampon distinct exposé.
**Q34.** Oui, prompt caching Anthropic : les tokens système répétés sont mis en cache pour réduire la latence et le coût.
**Q35.** L'architecture Transformer n'est pas calquée sur Atkinson-Shiffrin, mais des analogies fonctionnelles existent.
**Q36.** Non. Le Transformer diffère architecturalement du modèle de Baddeley, bien que l'attention ressemble fonctionnellement à la boucle phonologique.
**Q37.** Épisodique dans-session : oui (contexte actif). Entre sessions : partiellement via userMemories extraites automatiquement.
**Q38.** Dans le contexte : chronologique. Dans userMemories : extraits thématiques, sans ordre strict.
**Q39.** Pas de séparation explicite sémantique/épisodique — tout coexiste dans le flux de tokens.
**Q40.** Procédurale implicite dans les poids du modèle. Préférences procédurales stockables en userMemories.
**Q41.** Non, pas de mémoire prospective native (rappels futurs).
**Q42.** Oui, via userMemories sur claude.ai — historique relationnel partiel entre sessions.
**Q43.** Oui, les préférences utilisateur peuvent être stockées explicitement en userMemories.
**Q44.** userMemories : texte brut structuré. Interne au modèle : embeddings vectoriels denses.
**Q45.** Oui, chaque token est encodé en vecteur d'embedding en entrée du modèle.
**Q46.** Dimensionnalité des embeddings non divulguée publiquement par Anthropic.
**Q47.** userMemories = plat (texte). Connaissances internes = graphe implicite dans les poids.
**Q48.** Infrastructure Anthropic non exposée. userMemories stockées côté serveur Anthropic.
**Q49.** Relations implicites dans le texte des userMemories ; pas de graphe structuré exposé.
**Q50.** Pas d'indexation structurée exposée pour les userMemories standard.
**Q51.** Texte libre uniquement dans les userMemories éditables — pas de métadonnées structurées automatiques.
**Q52.** Non, pas de timestamps automatiques dans les userMemories éditables par l'utilisateur.
**Q53.** Non, pas d'ID unique par entrée mémoire exposé à l'utilisateur.
**Q54.** Non, pas de score de confiance structuré par mémoire individuelle.
**Q55.** Source non exposée structurellement — implicite dans le texte.
**Q56.** userMemories : max 30 entrées × 100 000 chars/entrée.
**Q57.** ~30 entrées. Contenu : millions de faits implicites dans les poids du modèle (non comptable).
**Q58.** userMemories persistent jusqu'à suppression manuelle ou purge nocturne après suppression de conversation source.
**Q59.** À 30 entrées : nouvelles entrées remplacent les plus anciennes selon la politique interne.
**Q60.** userMemories = 1 scope par compte (hors Projects). Dans Projects : scope séparé.

---

## CAT 3 : Mécanismes de Contextualisation

**Q61.** Oui, mécanisme d'attention multi-têtes central à l'architecture Transformer.
**Q62.** Chaque "tête" calcule attention sur différents aspects/relations du contexte en parallèle, puis concaténation.
**Q63.** Attention causale sur toute la fenêtre de contexte — incluant historique et mémoires injectées.
**Q64.** Via attention causale masquée sur la pleine séquence. Flash Attention et techniques d'optimisation pour longues séquences.
**Q65.** Théoriquement toute la fenêtre (~200k tokens) mais l'attention aux tokens distants s'atténue en pratique.
**Q66.** Causale (gauche→droite) en génération. L'encodeur voit tout le contexte passé.
**Q67.** Pas d'algorithme séparé : la pertinence émerge de l'attention calculée sur le contexte complet.
**Q68.** Similarité sémantique via produit scalaire des vecteurs Query/Key dans le mécanisme d'attention.
**Q69.** Oui, les scores d'attention sont les scores de pertinence implicites.
**Q70.** Les mots-clés reçoivent naturellement plus d'attention via leur représentation vectorielle distinctive.
**Q71.** Synonymes et paraphrases mappés vers des espaces vectoriels proches — traitement implicite par les embeddings.
**Q72.** Pas de seuil dur explicite ; atténuation progressive des scores d'attention faibles.
**Q73.** Résolution anaphorique implicite via l'attention sur les tokens précédents correspondants.
**Q74.** Oui, coréférence résolue implicitement dans les couches d'attention.
**Q75.** Ellipses résolues via contexte de la fenêtre active — inférence implicite.
**Q76.** Oui, plusieurs entités suivies en parallèle via représentations distinctes dans le contexte.
**Q77.** Références cataphoriques limitées en génération (causale) mais résolues si dans le contexte d'entrée.
**Q78.** Pas de limite fixe documentée, mais dégradation avec le nombre d'entités et la distance.
**Q79.** Position chronologique dans la séquence de tokens = contexte temporel implicite.
**Q80.** Oui, les messages récents tendent à recevoir plus d'attention (biais de récence).
**Q81.** Changements de sujet détectés via discontinuité sémantique — pas d'algorithme dédié séparé.
**Q82.** Pas de segmentation automatique exposée. Inférée implicitement par le modèle.
**Q83.** Flashbacks résolus si la référence est dans la fenêtre de contexte active.
**Q84.** Oui, structures imbriquées gérables si dans la fenêtre de contexte.
**Q85.** Source (user/assistant/system), position dans la séquence. Pas de métadonnées riches exposées.
**Q86.** Source marquée par le rôle (user/assistant/system/tool) dans la structure de message.
**Q87.** Niveau de confiance différencié : résultats outils > web search > connaissances internes pour faits récents.
**Q88.** Images, PDFs, fichiers intégrés au contexte sous forme de tokens visuels/textuels.
**Q89.** Ton et émotions inférés implicitement via le contenu textuel — pas de canal séparé.
**Q90.** Conflits signalés à l'utilisateur, avec demande de clarification ou présentation des deux versions.

---

## CAT 4 : Persistance et Continuité

**Q91.** Oui, tous les messages de la session active sont dans la fenêtre de contexte.
**Q92.** Ce qui est affiché = ce qui est en contexte. Pas de divergence intentionnelle.
**Q93.** Messages système = rôle "system", priorité et position en tête du contexte.
**Q94.** Messages édités/supprimés : le contexte transmis à l'API est mis à jour selon l'interface.
**Q95.** Dans claude.ai : pas d'historique de versions de messages exposé.
**Q96.** Selon l'interface : suppression côté UI peut ne pas affecter le contexte transmis à l'API.
**Q97.** Oui, Anthropic génère des résumés de conversations pour le système userMemories.
**Q98.** Seuil non exposé publiquement — déclenché en arrière-plan par Anthropic.
**Q99.** Préférences, faits clés sur l'utilisateur, contexte professionnel, projets actifs.
**Q100.** Sélection par importance estimée — processus interne non transparent.
**Q101.** Arrière-plan, non visible à l'utilisateur.
**Q102.** Non directement — le résumé remplace le détail original entre sessions.
**Q103.** Confusion des détails, fusion de souvenirs similaires, omissions progressives.
**Q104.** Non-linéaire : dégradation plus forte aux extrémités (début et fin de longues conversations).
**Q105.** Oui, au-delà de la fenêtre de contexte les informations sont simplement absentes.
**Q106.** Non quantifiable directement par l'utilisateur dans claude.ai.
**Q107.** Faits précis dégradent plus que les schémas généraux. Ton/émotions mieux préservés que détails factuels.
**Q108.** Résumés périodiques, répétition explicite des informations critiques, userMemories.
**Q109.** Accès partiel via userMemories (extraits automatiques), pas à toutes les conversations intégralement.
**Q110.** Automatique pour userMemories ; recherche dans les chats passés = outil explicite.
**Q111.** Oui, conversations anciennes non résumées peuvent ne plus être accessibles automatiquement.
**Q112.** Par ID de conversation et titre dans l'interface claude.ai.
**Q113.** Non, conversations supprimées purgées (données retirées des userMemories nuitamment).
**Q114.** Pas de limite temporelle documentée, mais la pertinence des mémoires décroît fonctionnellement.
**Q115.** Indexation interne non exposée. La recherche "past chats" utilise similarité sémantique.
**Q116.** Sémantique principalement (embeddings), complétée par mots-clés.
**Q117.** Via l'outil "search past chats" : requêtes naturelles. Opérateurs booléens non supportés nativement.
**Q118.** Recherche multilingue possible via embeddings multilingues.
**Q119.** Limite non documentée publiquement.
**Q120.** Légère dégradation probable avec volume, mais optimisations d'indexation atténuent l'effet.
**Q121.** Similarité sémantique entre la requête actuelle et le contenu des conversations indexées.
**Q122.** Oui, similarité cosinus sur embeddings ou équivalent.
**Q123.** Équilibre non exposé — combinaison implicite récence + pertinence thématique.
**Q124.** Oui, biais de récence probable dans la sélection.
**Q125.** Décroissance temporelle implicite, non documentée.

---

## CAT 5 : Hiérarchie et Priorités

**Q126.** Priorité décroissante : instructions système > message utilisateur actuel > contexte conversation > userMemories > connaissances training > recherche web.
**Q127.** Fixe structurellement, mais l'utilisateur peut modifier par instruction explicite.
**Q128.** Oui, le system prompt a priorité absolue, sauf contraintes éthiques hardcodées d'Anthropic.
**Q129.** Référence explicite à une source → priorité élevée accordée à cette source.
**Q130.** Faits vérifiables > opinions. Mais l'utilisateur peut demander de présenter des opinions.
**Q131.** Oui, sources officielles généralement plus fiables — pondération implicite.
**Q132.** Contexte immédiat prime sur mémoire stockée. Signal explicite de l'utilisateur prime sur tout.
**Q133.** Information web récente > connaissances training pour faits post-cutoff. Conflit signalé si nécessaire.
**Q134.** Vérification croisée implicite via l'attention sur plusieurs parties du contexte.
**Q135.** Signalement explicite des contradictions, présentation des deux versions.
**Q136.** Oui, informations récentes préférées en cas de conflit temporel.
**Q137.** Conflit entre conversations historiques : la plus récente ou la plus explicite prime.
**Q138.** Pondération implicite via attention — pas de système de scoring explicite exposé.
**Q139.** Oui, distance influence atténuation de l'attention, donc priorité implicite décroissante.
**Q140.** Oui : "souviens-toi de ceci", "ignore précédemment", "priorité absolue à X".
**Q141.** Longueur/complexité n'augmente pas automatiquement la priorité.
**Q142.** Non, pas de pondération structurelle différente questions/affirmations.
**Q143.** Oui, corrections explicites ("non, je voulais dire...") interprétées avec haute priorité.
**Q144.** Fonctionnellement : contexte actif > userMemories > connaissances training.
**Q145.** Analogie fonctionnelle mais pas d'implémentation directe du modèle Atkinson-Shiffrin.
**Q146.** Transition implicite via le processus de génération de userMemories par Anthropic.
**Q147.** Critères non exposés publiquement — processus interne.
**Q148.** Information émotionnellement saillante probablement mieux retenue (biais d'importance appris).
**Q149.** Oui, via la commande memory_user_edits (outil mémoire dans claude.ai).
**Q150.** Pas de système de scoring exposé par mémoire individuelle.
**Q151.** Critères internes non documentés.
**Q152.** Probablement oui, via le processus de mise à jour des userMemories.
**Q153.** Implicitement, les informations fréquemment réactivées sont mieux consolidées.
**Q154.** Pas de seuil exposé.
**Q155.** Contexte immédiat consulté en premier (toujours présent). Historique via outil séparé si nécessaire.

---

## CAT 6 : Apprentissage et Adaptation

**Q156.** Dans la session : adaptation comportementale oui. Apprentissage des poids du modèle : non.
**Q157.** Pas d'apprentissage au sens ML dans la session. Adaptation = inférence contextuelle.
**Q158.** Corrections intégrées immédiatement dans le contexte actif — pas dans les poids.
**Q159.** Limité à la session sauf si capturé dans userMemories.
**Q160.** Fait = mis à jour dans le contexte. Préférence = peut être stockée en userMemories.
**Q161.** Via formulation explicite ("toujours", "ne jamais", "en général") vs correction ponctuelle.
**Q162.** Pas de fine-tuning dynamique par utilisateur en temps réel.
**Q163.** N/A — pas de fine-tuning dynamique individuel.
**Q164.** N/A — les mises à jour du modèle base affectent tous les utilisateurs.
**Q165.** Non, pas de paramètres personnels dans les poids du modèle.
**Q166.** N/A — pas de fine-tuning individuel.
**Q167.** Non applicable en inférence. Catastrophic forgetting concerne l'entraînement du modèle base.
**Q168.** Via userMemories : préférences explicitement notées et appliquées automatiquement.
**Q169.** Explicitement stockées en userMemories (texte).
**Q170.** Oui, les userMemories peuvent capturer des préférences contextuelles ("sur les sujets X, préférer le format Y").
**Q171.** Via mise à jour ou remplacement des entrées mémoire correspondantes.
**Q172.** Détection automatique partielle lors de la génération de nouvelles userMemories.
**Q173.** Permanentes jusqu'à suppression — pas de date d'expiration native.
**Q174.** Corrections capturées dans userMemories si jugées importantes par le système.
**Q175.** Pas de base d'erreurs communes exposée. Erreurs corrigées dans le contexte actif.
**Q176.** Non documenté. Les erreurs corrigées explicitement ont un signal clair.
**Q177.** Via généralisation implicite dans le contexte de session.
**Q178.** Feedback utilisateur (thumbs down) alimente potentiellement le training futur d'Anthropic.
**Q179.** Pas de catégorisation d'erreurs exposée à l'utilisateur.
**Q180.** Oui, transfert de connaissances entre contextes est une capacité fondamentale du modèle.
**Q181.** Généralisation via analogie et inférence — capacité centrale du modèle.
**Q182.** Oui, risque de sur-généralisation. Claude signale les cas incertains.
**Q183.** Via détection de dissimilarité contextuelle — inférence implicite.
**Q184.** Non, les sessions sont indépendantes. Seul le training global affecte tous les utilisateurs.
**Q185.** Oui, potentiellement via RLHF agrégé sur les interactions de tous les utilisateurs (training).

---

## CAT 7 : Oubli, Suppression et Vie Privée

**Q186.** Oubli entre sessions : oui (contexte volatile). userMemories : pas d'oubli automatique par dégradation.
**Q187.** Oubli de session : automatique à la fermeture. userMemories : déclenché par suppression de conversation source (purge nocturne).
**Q188.** Session : immédiat à la fermeture. userMemories : basé sur suppression de source.
**Q189.** Informations fréquemment réactivées ou marquées explicitement résistent mieux.
**Q190.** Pas de courbe d'Ebbinghaus implémentée explicitement. Analogie partielle dans la dégradation de l'attention.
**Q191.** Oubli de session = définitif. userMemories supprimées = définitif après purge.
**Q192.** Via memory_user_edits (commande remove) ou en demandant à Claude de supprimer une entrée.
**Q193.** Immédiate pour la session courante. Purge des userMemories liées : nocturne.
**Q194.** Message supprimé dans l'UI : retiré du contexte transmis. Traces dans logs Anthropic possibles selon politique.
**Q195.** Niveaux non exposés publiquement. Fonctionnellement : suppression UI = retrait du contexte.
**Q196.** Sélection possible via memory_user_edits pour les userMemories.
**Q197.** Vérification indirecte : demander à Claude de lister ses mémoires. Confirmation complète non garantie.
**Q198.** Oui, Anthropic respecte le RGPD. Détails : https://privacy.anthropic.com
**Q199.** Oui, via les paramètres de compte Anthropic (demande de suppression de données).
**Q200.** Certaines données peuvent être retenues pour obligations légales selon la politique Anthropic.
**Q201.** Délai selon politique RGPD : généralement 30 jours. Détails : https://privacy.anthropic.com
**Q202.** Politique Anthropic prévoit suppression des backups dans les délais RGPD.
**Q203.** Non exposé nativement dans claude.ai.
**Q204.** Chiffrement en transit (TLS) et au repos côté Anthropic. Cloisonnement par utilisateur.
**Q205.** Oui, données chiffrées au repos sur l'infrastructure Anthropic.
**Q206.** Pas de marquage automatique "sensible" exposé à l'utilisateur, mais les guidelines internes s'appliquent.
**Q207.** Isolation stricte par compte utilisateur — architecture multi-tenant.
**Q208.** Oui, détection de contenu sensible (PII, données financières) intégrée aux guidelines.
**Q209.** Pas de durée de rétention différenciée exposée par type de donnée.
**Q210.** Oui, via memory_user_edits : contrôle explicite sur les entrées userMemories.
**Q211.** Oui, mode incognito disponible dans claude.ai — aucune mémorisation entre sessions.
**Q212.** Oui : demander à Claude "liste tes mémoires sur moi" ou utiliser les paramètres mémoire.
**Q213.** Export de données possible via demande RGPD à Anthropic (https://privacy.anthropic.com).
**Q214.** Logs d'accès non exposés à l'utilisateur dans l'interface standard.
**Q215.** Informations sur tiers traitées selon les mêmes règles. Pas de profil créé sur les tiers.

---

## CAT 8 : Performance et Coût Computationnel

**Q216.** Plus la fenêtre de contexte est grande, plus la latence augmente (calcul d'attention en O(n²)).
**Q217.** Oui : contexte plus long = réponse plus lente mais potentiellement plus cohérente.
**Q218.** Oui, conversations longues augmentent la latence de génération.
**Q219.** Prompt caching, chunking, résumés intermédiaires.
**Q220.** Calcul d'attention sur longue séquence est la principale opération coûteuse.
**Q221.** GPU pour le calcul d'attention (dominant). RAM pour le contexte. Coût : O(n²) en attention naïve.
**Q222.** Oui, recherche dans l'historique = requête séparée + embeddings, plus coûteux que contexte déjà chargé.
**Q223.** Croissance sous-linéaire avec optimisations (Flash Attention) vs quadratique naïf.
**Q224.** Flash Attention, sparse attention, prompt caching, quantization.
**Q225.** O(n²) naïf pour l'attention, mais Flash Attention réduit à O(n) en mémoire. En pratique : sous-quadratique.
**Q226.** Prompt caching, batching, optimisations KV-cache.
**Q227.** Oui, KV-cache (Key-Value cache) pour les tokens déjà calculés dans la session.
**Q228.** Parallélisme GPU sur les têtes d'attention. Sources multiples traitées séquentiellement.
**Q229.** KV-cache précharge les tokens système constants.
**Q230.** Trade-off géré par les paramètres de température et top-p — pas directement exposé à l'utilisateur.
**Q231.** Oui, rate limits par plan (messages/minute, tokens/minute) selon docs.anthropic.com.
**Q232.** File d'attente FIFO avec priorité selon plan d'abonnement.
**Q233.** Oui, en cas de charge élevée des serveurs Anthropic.
**Q234.** Scaling automatique de l'infrastructure Anthropic — non visible à l'utilisateur.
**Q235.** SLA disponibles pour les plans Enterprise selon contrats.
**Q236.** Latence (TTFT, TPS), taux d'erreur, taux de cache hit. Non exposés directement à l'utilisateur.
**Q237.** Métriques internes non accessibles directement. TTFT et latence totale observables.
**Q238.** Non accessible à l'utilisateur standard.
**Q239.** Internalement via monitoring Anthropic. Utilisateur : observe les timeouts/erreurs.
**Q240.** Alertes de statut sur https://status.anthropic.com.

---

## CAT 9 : Erreurs, Hallucinations et Fiabilité

**Q241.** Hallucinations factuelles, confusions d'entités, extrapolations incorrectes, erreurs de rappel.
**Q242.** Recall = ne pas retrouver une information. Reconnaissance = reconnaître sans rappeler spontanément. Claude peut confondre les deux.
**Q243.** Oui, confabulations possibles : remplissage de lacunes par des informations plausibles mais incorrectes.
**Q244.** Distinction difficile introspectablement. Claude signale l'incertitude mais ne détecte pas toujours l'hallucination.
**Q245.** Oui : noms propres, dates précises, statistiques, références bibliographiques = plus d'erreurs.
**Q246.** Fusion de deux personnes/événements similaires en une réponse hybride incorrecte.
**Q247.** Lacunes mémorielles → interpolation → fabrication de détails plausibles.
**Q248.** Oui, une information incorrecte dans le contexte peut contaminer les réponses suivantes.
**Q249.** Oui, sans correction les erreurs se renforcent dans le contexte de session.
**Q250.** Confusion de sources → attribution incorrecte, mélange d'informations.
**Q251.** Oui, souvenirs flous → plus d'interpolation → plus de risque d'hallucination.
**Q252.** Interpolation entre N souvenirs incomplets = risque d'erreur composite.
**Q253.** Partiel : Claude détecte parfois ses incohérences mais pas systématiquement.
**Q254.** Score de confiance implicite via hedging linguistique ("je pense", "probablement").
**Q255.** Pas de système de validation formel exposé — inférence implicite.
**Q256.** Oui, contradictions dans le contexte déclenchent généralement une signalisation.
**Q257.** Prévention limitée — les erreurs dans le contexte fourni sont traitées comme vraies.
**Q258.** Oui, mécanisme de doute implicite = hedging ("je ne suis pas certain", "à vérifier").
**Q259.** Correction dans le contexte actif. Pas de réécriture des mémoires persistantes automatiquement.
**Q260.** Dans la session : oui, rétroactivement dans le contexte. Entre sessions : non.
**Q261.** Pas d'historique de corrections exposé.
**Q262.** Claude peut maintenir sa position si une "correction" semble incorrecte, avec explication.
**Q263.** Validation croisée implicite via attention multi-sources dans le contexte.
**Q264.** Oui, Claude demande confirmation en cas d'incohérence détectée.
**Q265.** Via hedging linguistique explicite dans la réponse.
**Q266.** Pas de score numérique exposé.
**Q267.** Score implicite, non quantifié.
**Q268.** Oui, Claude peut refuser ou très fortement hedger une réponse de faible fiabilité.
**Q269.** Via formulation : "je ne sais pas si je sais cela avec certitude."
**Q270.** Audits internes Anthropic — non exposés à l'utilisateur.

---

## CAT 10 : Méta-cognition et Introspection

**Q271.** Partiellement. Conscience limitée : Claude sait ce qu'il y a dans son contexte, moins ce qu'il "sait" de son training.
**Q272.** Oui : demander "liste tes mémoires sur moi" retourne les userMemories. Connaissances de training non listables.
**Q273.** Oui (métamémoire partielle) : Claude peut signaler l'absence d'une information spécifique.
**Q274.** Partiellement, via le hedging — pas de score numérique de clarté.
**Q275.** Oui, pour le contexte actif. Pour les connaissances de training : lacunes difficiles à détecter.
**Q276.** Explication post-hoc possible mais non garantie exacte — introspection limitée.
**Q277.** Partiellement : peut décrire le raisonnement mais pas le chemin computationnel exact.
**Q278.** Reconstruction logique post-hoc, pas accès à la trace computationnelle réelle.
**Q279.** Via analogies cognitives (fenêtre de contexte, attention, mémoire persistante) — non technique.
**Q280.** Partiellement : Claude peut citer des sources dans son contexte, pas distinguer les poids du training.
**Q281.** Partiellement via auto-critique et évaluation de cohérence.
**Q282.** Oui : bonne en raisonnement structuré, faible en faits précis/rares, faible en calcul exact.
**Q283.** Via signaux d'incohérence, de doute, de lacune dans le contexte.
**Q284.** Partiellement : peut identifier les types d'information à risque d'oubli (détails précis, chiffres).
**Q285.** Pas de mécanisme d'auto-test formel. Claude peut vérifier sa cohérence si demandé.
**Q286.** Oui : Claude connaît ses limitations majeures (cutoff, calcul, mémoire inter-sessions).
**Q287.** Oui, Claude peut proactivement signaler l'approche des limites de contexte.
**Q288.** Via hedging et refus de spéculer au-delà de la certitude disponible.
**Q289.** Oui : "je ne sais pas" (absence de connaissance) vs "je ne me souviens pas" (hors contexte).
**Q290.** Oui, Claude recommande la vérification externe quand sa fiabilité est insuffisante.
**Q291.** Pas d'auto-amélioration autonome. Feedback → potentiellement intégré dans le training suivant.
**Q292.** Indirectement via le RLHF sur les feedbacks agrégés.
**Q293.** Feedback (thumbs up/down, corrections) informe le training futur — pas en temps réel.
**Q294.** Non exposé à l'utilisateur.
**Q295.** Oui : Claude peut analyser les patterns d'interaction et suggérer des améliorations (templates, userMemories).

---

## CAT 11 : Intégration Outils et Systèmes Externes

**Q296.** Via function calling / tool use : résultats d'outils injectés dans le contexte comme messages.
**Q297.** Oui : couche tool_result dans la structure de message — abstraction entre mémoire et outil.
**Q298.** Timeout possible. Latence des outils s'ajoute à la latence de génération.
**Q299.** Dans la session uniquement (contexte). Pas de cache persistant entre sessions.
**Q300.** Pas de synchronisation automatique — nouvelle requête outil nécessaire pour données fraîches.
**Q301.** Via outils MCP (Model Context Protocol) connectés — selon les connecteurs activés.
**Q302.** Via authentification OAuth/tokens gérés par les connecteurs MCP.
**Q303.** Données externes injectées comme tool_result dans le contexte — traitées de même.
**Q304.** Limite pratique : taille du contexte disponible pour les résultats d'outils.
**Q305.** Normalisation via le texte du tool_result — pas de mapping de schéma automatique.
**Q306.** Résultats web search injectés comme tool_result dans le contexte actif.
**Q307.** Temporairement dans le contexte de session uniquement.
**Q308.** Via réputation du domaine, cohérence avec d'autres sources, fraîcheur de l'information.
**Q309.** Contenu récent privilégié pour les requêtes time-sensitive. Ancienneté signalée si pertinente.
**Q310.** Contenu dynamique : nouvelle requête nécessaire. Claude ne re-fetch pas automatiquement.
**Q311.** Oui, via connecteur Google Drive MCP (si activé dans les paramètres).
**Q312.** Indexation dans le contexte via les résultats des appels d'outils.
**Q313.** Selon le connecteur : lecture généralement disponible. Écriture selon les capacités du MCP.
**Q314.** Conflits de versions signalés si détectés — pas de résolution automatique.
**Q315.** Métadonnées accessibles si retournées par l'API du connecteur.
**Q316.** Infrastructure Anthropic = distribuée. Du point de vue utilisateur : centralisée.
**Q317.** Cohérence gérée par l'infrastructure Anthropic — non visible à l'utilisateur.
**Q318.** Réplication interne Anthropic pour la résilience.
**Q319.** Géré par l'infrastructure Anthropic — transparent pour l'utilisateur.
**Q320.** Stratégie interne Anthropic — probablement CP (consistency + partition tolerance).
**Q321.** Oui : export JSON/CSV via outils, import via upload de fichiers.
**Q322.** API Anthropic complète pour accès programmatique. Pas d'API publique spécifique à la mémoire utilisateur.
**Q323.** MCP (Model Context Protocol) — standard ouvert Anthropic pour l'interopérabilité.
**Q324.** Pas de partage sélectif natif entre services sauf via MCP configuré explicitement.
**Q325.** MCP (Model Context Protocol) — standard ouvert Anthropic pour l'interopérabilité.

---

## CAT 12 : Formats et Structuration des Données

**Q326.** Texte brut tokenisé → embeddings vectoriels. Pas de structure interne exposée.
**Q327.** Code tokenisé avec tokens dédiés pour keywords/symboles. Pas d'AST interne exposé.
**Q328.** Tableaux traités comme texte structuré (markdown ou CSV). Pas de représentation matricielle native.
**Q329.** Graphiques : description textuelle ou traitement visuel (image tokens). Pas de représentation vectorielle structurée exposée.
**Q330.** Formules : texte LaTeX ou symbolique. Pas d'encodage symbolique interne exposé.
**Q331.** Pas de schémas prédéfinis exposés pour les userMemories — texte libre.
**Q332.** Hiérarchies représentées en texte indenté ou listes — pas d'arbre structurel interne exposé.
**Q333.** Graphes de connaissances : implicites dans les poids du modèle. Pas de KG structuré exposé en inférence.
**Q334.** Relations many-to-many représentées implicitement dans les poids et explicitement dans le texte du contexte.
**Q335.** Pas de normalisation formelle exposée pour les userMemories — redondance possible.
**Q336.** userMemories : texte libre sans métadonnées structurées automatiques (pas de timestamp, type, confiance exposés).
**Q337.** Ontologies implicites dans les poids du modèle — pas d'ontologie formelle exposée.
**Q338.** Entités nommées reconnues implicitement via le modèle — pas d'annotation structurée exposée.
**Q339.** Pas de système de tags/labels formel exposé dans les userMemories standard.
**Q340.** Annotations multiples possibles en texte libre. Pas de couches formelles exposées.
**Q341.** Format interne des poids : non divulgué. userMemories : texte brut côté infrastructure Anthropic.
**Q342.** Rétrocompatibilité gérée par Anthropic lors des mises à jour du modèle.
**Q343.** Compression interne probable (quantization des poids). Non exposée à l'utilisateur.
**Q344.** Intégrité gérée par l'infrastructure Anthropic — checksums internes probables.
**Q345.** Optimisés pour la lecture (inférence) — les poids sont en lecture seule pendant l'inférence.
**Q346.** Migration de schéma gérée par Anthropic lors des mises à jour de modèle.
**Q347.** Versioning de modèle (claude-sonnet-4-6, claude-opus-4-6, etc.) = versioning implicite.
**Q348.** Migration gérée par Anthropic. Les userMemories textuelles sont format-agnostiques.
**Q349.** Coexistence de versions via les identifiants de modèle dans l'API.
**Q350.** Rollback possible via sélection d'une version de modèle antérieure dans l'API.

---

*Claude Sonnet 4.6 — Mai 2026*
*"non exposé" = information interne Anthropic non documentée publiquement.*
