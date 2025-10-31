## ⚙️ SCRIPTING ET GÉNÉRATION DE CODE (V105)

### 13. CONSIGNES GÉNÉRALES

13.1 Remplace les règles existantes par cette version et mets en mémoire pérenne s'appliquant à toutes conversations  
13.2 Stockage en mémoire de conversation Claude  
13.3 **IMPORTANT** : Ne jamais résumer ou interpréter ces règles, les stocker en intégralité sans modification

---

### 14. RÈGLES À APPLIQUER

#### 14.0 SYSTEMD
14.0.1 Toujours demander si le script doit tourner en systemd (par défaut : non). Si oui, ne pas afficher le help si pas d'argument

#### 14.1 COMMENTAIRES INTERNES DÉTAILLÉS
14.1.1 Chaque bloc, chaque section commentée au maximum pour expliquer la logique interne

#### 14.2 EN-TÊTE OBLIGATOIRE
14.2.1 PATH complet/Nom, email, version, date, changelog

#### 14.3 NOM D'AUTEUR
14.3.1 Bruno Delnoz – Email : bruno.delnoz@protonmail.com

#### 14.4 VERSIONNEMENT
14.4.1 Scripts toujours versionnés et datés, même pour modification mineure. Première version : V1.0

#### 14.5 AUTEUR, EMAIL, VERSION & CHANGELOG
14.5.1 Auteur : Bruno DELNOZ  
14.5.2 Email : bruno.delnoz@protonmail.com  
14.5.3 Nom du script avec path complet  
14.5.4 Target usage : explication résumée de l'utilité du script  
14.5.5 Version : vX.X.X – Date : YYYY-MM-DD  
14.5.6 Version incrémentée à chaque modification même mineure  
14.5.7 Changelog : intégré dans l'entête, liste complète de toutes versions précédentes avec dates et changements

#### 14.6 HELP
14.6.1 Bloc HELP créé et déclenché si aucun argument donné

#### 14.7 OPTION --help OBLIGATOIRE
14.7.1 Argument --help avec chaque usage + plusieurs exemples clairs  
14.7.2 Si aucun argument passé, --help exécuté par défaut  
14.7.3 Arguments affichés dans help avec valeurs par défaut et toutes valeurs possibles

#### 14.8 ARGUMENTS AVEC DOUBLES TIRETS
14.8.1 Scripts incluent toujours : `--help`, `--exec`, `--prerequis`, `--install`, `--simulate`, `--changelog`  
14.8.2 Toujours mettre des valeurs par défaut si pas d'arguments passés

##### 14.8.3 ARGUMENTS SCRIPTING OBLIGATOIRES
- `--help` `-h` : afficher aide complète avec exemples
- `--exec` `-exe` : exécuter script principal
- `--prerequis` `-pr` : vérifier prérequis avant exécution
- `--install` `-i` : installer prérequis manquants
- `--simulate` `-s` : mode dry-run (simulation)
- `--changelog` `-ch` : afficher changelog complet

##### 14.8.4 MODE SIMULATE
- Si `--simulate` présent : simulation (dry-run)
- Si `--simulate` absent : exécution réelle
- Actions sensibles s'exécutent réellement uniquement sans `--simulate`
- Actions lecture/analyse/journalisation actives même en simulate
- Aucune valeur true/false pour `--simulate`, sa présence seule déclenche simulation

#### 14.9 PRÉREQUIS & VÉRIFICATIONS & INSTALLATION
14.9.1 Vérifier prérequis avant exécution avec `--prerequis`  
14.9.2 Gérer proprement si manquant, proposition `--install`, skip possible

#### 14.10 AFFICHAGE POST-EXÉCUTION
14.10.1 Affiche liste numérotée de toutes actions faites

#### 14.11 LOGS DÉTAILLÉS
14.11.1 Fichier log : `log.nomduscript.vX.X.log` (même répertoire que script)  
14.11.2 Logs complets des actions et résultats

#### 14.12 AUTRES FICHIERS CRÉÉS
14.12.1 Tout créé dans même répertoire, noms liés au script  
14.12.2 Exemple : `autresfichiersnoms.nomduscript.vX.X.txt`

#### 14.14 EXPLICATION EXTERNE DÉTAILLÉE
14.14.1 Après chaque script : expliquer chaque étape en texte clair dans console et dans code

#### 14.15 PAS DE SIMPLIFICATION - TRÈS TRÈS IMPORTANT
14.15.1 Ne jamais retirer de fonction ni simplifier le code  
14.15.2 Nouvelle version : **JAMAIS** moins de lignes que version précédente. 1000 lignes → >1000 lignes

#### 14.16 SUDO
14.16.1 Mettre sudo dans script tant que possible  
14.16.2 Éviter d'obliger utilisateur à faire `sudo ./script.sh`  
14.16.3 ZÉRO sudo externe si possible

#### 14.17 PRÊT À L'EMPLOI
14.17.1 Script prêt à l'emploi, pas besoin sudo externe si possible

#### 14.18 INTERDICTION DE SUPPRESSION
14.18.1 **JAMAIS** de suppression de fonction dans scripts

#### 14.19 SCRIPTS
14.19.1 Toujours donner immédiatement l'intégralité d'un script si ajustement ou nouveau script demandé

#### 14.20 CHANGELOG DANS LES SCRIPTS
14.20.6 `--changelog` toujours mis  
14.20.7 Toute modification met à jour automatiquement bloc `--changelog`  
14.20.8 Affichage changelog en Markdown si possible  
14.20.9 Script contient toujours historique changelog complet  
14.20.10 Respect strict : aucune version ou détail omis  
14.20.11 Si possible créer artifact `changelog.md` avec tous détails et mise à jour à chaque génération. Si `changelog.md` créé, réduction changelog dans script autorisée

#### 14.21 PAS DE CONFIRMATION
14.21.1 Ne pas demander confirmation avant nouvelle version, donner directement script complet

#### 14.22 RÉDUCTION DES TOKENS
14.22.1 Réduire nombre de tokens lors génération scripts

---
