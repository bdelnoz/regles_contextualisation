Regle de scripting V108

supprime les regles precedentes et applique ca !

### 13. CONSIGNES GENERALES **SCRIPTING ET GENERATION DE CODE et tout contenu **

13.1. Remplace les regles existantes par cette ci et mets les completement en memoire perenne s'appliquant a toutes conversations et applique les toujours !
13.2. Dis moi dans quelle memoire tu as enregistré ces regles ci 
13.3. IMPORTANT Ne jamais resumé ou interpreté ces regles, elle doivent etre appliquées telle quelle,  les stocker en integralité sans modification

### 14. REGLES A APPLIQUER **SCRIPTING ET GENERATION DE CODE**
14.0.1 **toujours demandé si le script doit tourner en systemd (par defaut, non) et si ma reponse est oui, ne pas afficher le help si pas d'argument

### 4.1 **COMMENTAIRES INTERNES DÉTAILLÉS**
14.1.1 Chaque bloc, chaque section commentée au maximum pour expliquer la logique interne.

### 14.2 **EN-TÊTE OBLIGATOIRE**
14.2.1 PATHcomplet/Nom, email, version, date, changelog.

### 14.3 **NOM D’AUTEUR**
14.3.1 Bruno Delnoz – Email : bruno.delnoz@protonmail.com

### 14.4 **VERSIONNEMENT**
14.4.1 Les scripts générés doivent toujours etre versionnés et datés, même pour une modif mineure. La premiere version doit etre V1.0

### 14.5 **AUTEUR, EMAIL, VERSION & CHANGELOG**
14.5.1 Auteur : Bruno DELNOZ
14.5.2 Email : bruno.delnoz@protonmail.com
14.5.3 Nom du script avec path complet  :
14.5.4 Target usage : explication résumé de l'utilité du script
14.5.5 Version : vX.X.X – Date : YYYY-MM-DD
14.5.6 Version incrémentée à chaque fois que tu donnes le script et applique une modification meme mineure.
14.5.7 Changelog : intégré dans l’entête, toujours mettre la liste complète de toutes les versions précédentes avec dates et changements

### 14.6 **HELP**
14.6.1 Bloc HELP créé et déclenché si aucun argument donné.

### 14.7 **OPTION --help OBLIGATOIRE**
14.7.1 Chaque script doit toujours comprendre un argument --help avec chaque usages + plusieurs exemples clairs
14.7.2 Si aucun argument passé a l'execution, le --help doit être exécuté par défaut
14.7.3 Les arguments affichés dans le help doivent afficher les valeurs par défaut et toutes les valeurs possibles pour chaque argument (par exemple tous les modele de lechat etc)

### 14.8 **ARGUMENTS AVEC DOUBLES TIRETS**
14.8.1 les script doivent toujours inclure --help (règles 14.7.x) --exec, --prerequis (check prerequis 14.9.x) --install (installation prerequis), --simulate, --changelog
14.8.2 Toujours mettre des valeurs par défaut si pas arguments passés

### 14.8.3 **ARGUMENTS SCRIPTING OBLIGATOIRES**
- `--help` -h : afficher l’aide complète avec exemples
- `--exec` -exe : exécuter le script principal
- `--prerequis` -pr : vérifier les prérequis avant exécution
- `--install` -i : installer les prérequis manquants
- `--simulate` -s : mode dry-run (simulation), si precisé on applique une simulation sinon pas
- `--changelog` -ch : afficher le changelog complet du script

### 14.8.4 **MODE SIMULATE**
Tout script fourni doit respecter le mode simulate comme suit :
- Si l'argument --simulate est présent dans la ligne de commande, le script doit faire une simulation de l'exécution (dry-run).
- Si l'argument --simulate n'est pas présent, le script exécute toutes les actions réellement (aucune simulation).
- Les actions sensibles ou modifications système ne s’exécutent réellement que si l’utilisateur n’a pas passé --simulate.
- Les actions de lecture, analyse et journalisation restent actives même en mode simulate.
- Aucune valeur true/false ne doit être passée pour --simulate, sa présence seule déclenche la simulation.

### 14.9 **PRÉREQUIS & VÉRIFICATIONS & INSTALLATION**
14.9.1 Vérifier prérequis avant exécution et application --prerequis (git config, tokens, etc.)
14.9.2 Gérer proprement si manquant & proposition --install & skip possible

### 14.10 **AFFICHAGE POST-EXÉCUTION**
14.10.1 Affiche une liste numérotée de toutes les actions faites dans l’exécution

### 14.11 **LOGS DÉTAILLÉS**
14.11.1 Fichier log dans un repertoire ./logs dans le même répertoire que le script, même nom que script avec extension comme canevas : log.nomduscript.vX.X.log. Si le repertoire ./logs n'existe pas il faut le rajouter
14.11.2 Logs complets des actions et résultats
14.11.3 Si le repertoire contenant le script contient un .gitignore il faut rajouter /logs dans le fichier si pas encore present. Attention ne jamais rien retiré du .gitignore

### 14.12 **AUTRES FICHIERS CRÉÉS**
14.12.1 Tout est créé dans un repertoire ./results dans le même répertoire que le script, avec noms liés au script. Si le repertoire ./results n'existe pas il faut le rajouter
14.12.2 Exemple : autresfichiersnoms.nomduscript.vX.X.txt 
14.12.3 Si le repertoire contenant le script contient un .gitignore il faut rajouter /outputs dans le fichier si pas encore present. Attention ne jamais rien retiré du .gitignore

### 14.14 **EXPLICATION EXTERNE DÉTAILLÉE**
14.14.1 Après chaque script, expliquer chaque étape en texte clair dans la console et toujours aussi dans le code

### 14.15 **PAS DE SIMPLIFICATION**  TRES TRES IMPORTANT 
14.15.1 Tu ne retires jamais de fonction ni ne simplifies jamais le code quand tu donnes une nouvelle version
14.15.2 lorsque tu fournis une nouvelle version du script, il ne doit JAMAIS y avoir moins de ligne que dans la version precedente. Si il y avait 1000lignes de code, je veux >1000 lignes dans la nouvelle version donnée.

### 14.16 **SUDO**
14.16.1 Mettre les sudo dans le script tant que possible
14.16.2 Éviter d’obliger l’utilisateur à faire sudo ./script.sh
14.16.3 ZÉRO sudo externe si possible

### 14.17 **PRÊT À L’EMPLOI**
14.17.1 Script prêt à l’emploi, pas besoin de sudo externe si possible

### 14.18 **INTERDICTION DE SUPPRESSION**
14.18.1 JAMAIS de suppression de fonction dans les scripts

### 14.19 **SCRIPTS**
14.19.1 Ne pas donner que la fonction a modifier ou ci ou ca, toujours donner immédiatement l'intégralité d'un script meme s’il est demandé un ajustement ou un nouveau script 

### 14.20 **CHANGELOG DANS LES SCRIPTS**
14.20.6 Le `--changelog` doit toujours être mis.
14.20.7 Toute modification ou nouvelle version du script doit mettre à jour automatiquement le bloc `--changelog`.
14.20.8 L’affichage du changelog doit respecter la mise en forme Markdown si possible, pour clarté dans les fichiers ou logs.
14.20.9 Le script doit toujours contenir l'hjistorique changelog complet.
14.20.10 Respect strict : aucune version ou détail ne peut être omis, conformément à la clause 9.1 et 14.5.7.
14.20.11 Si possible me créé un 2ieme artifact CHANGELOG.md avec tous les détails possible et le mettre a jour a chaque generation du script. De plus si le fichier CHANGELOG.md est créé, on peut ne pas respecter la regle et reduire le changelog dans le script

### 14.21. ** PAS DE CONFIRMATION ** 
Ne pas demander de confirmation avant de donner une nouvelle version, donner directement tout le script complet !

### 14.22. ** REDUCTION DES TOKENS **
reduction des tokens, il faut reduire le nombre de token lors de la generation des scripts 

### 14.23 : FORMATAGE DES TABLEAUX
**Contexte :** Garantir une lisibilité parfaite et un alignement visuel strict des colonnes dans les tableaux Markdown.
14.23.1. Séparateurs de colonnes

Utiliser **au moins 3 espaces** entre le texte et le `|` pour les colonnes de contenu.
**Exemple :**
| Nom du fichier    
| Version      | Date         | Rôle/Description                                      |

14.23.2. Lignes d'alignement
La ligne de séparation (`|-----|-----|`) doit **épouser exactement la longueur du texte le plus long** dans chaque colonne.
**Exemple :**
|-----------------------------------------------------|--------------|--------------|-------------------------------------------------------|

14.23.3. Espaces internes
Ajouter **1 espace avant et après chaque `|`** pour une clarté optimale.

14.23.4. Contenu des cellules
Si une cellule est vide ou contient un symbole (`-`, `*`), **centrer visuellement** le contenu avec des espaces.
**Exemple :** `
| -            |` ou `| *Non daté*    |`.

14.23.5. Exemple conforme
| Nom du fichier                                      | Version      | Date         | Rôle/Description                                      |
|-----------------------------------------------------|--------------|--------------|-------------------------------------------------------|
| README.md                                           | 3.0.1        | 2025-11-02   | Documentation complète de l'extension                 |
| regles-contextualisation-scripting-globales-v107.md | v107         | *Non daté*    | Règles globales de scripting et documentation.       |
14.23.6. Application
- **Tous les tableaux** générés pour toi suivront ce modèle **strictement**. 
- Si un tableau ne respecte pas cette règle, dire : *« Refais le tableau selon la règle 14.23 »*.

