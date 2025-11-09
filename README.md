# 📘 Règles Officielles de Contextualisation Générale

**Version actuelle : V110 (Master)**  
**Auteur : Bruno Delnoz**  
**Email : bruno.delnoz@protonmail.com**  
**Date : 2025-11-09**

---

## 📋 Table des matières

- [Vue d'ensemble](#vue-densemble)
- [Installation](#installation)
- [Structure du projet](#structure-du-projet)
- [Utilisation](#utilisation)
- [Sections principales](#sections-principales)
- [Règles de scripting (Master)](#règles-de-scripting-master)
- [Contribution](#contribution)
- [Historique des versions](#historique-des-versions)
- [Support](#support)

---

## 🎯 Vue d'ensemble

Ce projet contient l'ensemble des **règles officielles de contextualisation** pour les conversations avec Claude. Ces règles définissent les comportements, les standards et les pratiques à appliquer dans tous les contextes d'interaction.

### Objectifs

✅ **Cohérence** : Garantir une expérience uniforme dans toutes les conversations  
✅ **Qualité** : Maintenir des standards élevés de génération de code et contenu  
✅ **Traçabilité** : Versionner et documenter toutes les modifications  
✅ **Automatisation** : Simplifier les tâches répétitives via des scripts standardisés

### Caractéristiques principales

- **98 règles principales** organisées en 8 sections
- **520+ sous-règles** détaillées
- **Section Scripting Master** (V110) avec 50+ règles avancées
- **Élimination complète des doublons**
- **Documentation automatique** intégrée
- **Gestion automatique** du .gitignore
- **Formatage standardisé** des tableaux

---

## 📦 Installation

### Prérequis

- Git
- Éditeur Markdown (VS Code, Typora, etc.)
- Python 3.x (optionnel, pour scripts de validation)
- Pandoc (optionnel, pour conversion en PDF/DOCX)

### Clonage du repository

```bash
git clone https://github.com/votre-username/regles-contextualisation.git
cd regles-contextualisation
```

### Installation de Pandoc (optionnel)

Pour la conversion des fichiers Markdown :

```bash
# Ubuntu/Debian
sudo apt-get install pandoc

# macOS
brew install pandoc

# Windows
# Télécharger depuis https://pandoc.org/installing.html
```

---

## 📁 Structure du projet

```
regles-contextualisation/
│
├── regles-contextualisation-globales-v110.md    # Fichier principal des règles
├── CHANGELOG.md                                  # Historique détaillé des versions
├── README.md                                     # Ce fichier
│
├── archives/                                     # Versions précédentes
│   ├── v106/
│   ├── v100/
│   └── ...
│
├── scripts/                                      # Scripts utilitaires
│   ├── validate-rules.py                        # Validation de la cohérence
│   ├── generate-docs.sh                         # Génération documentation
│   └── check-duplicates.py                      # Détection doublons
│
├── docs/                                        # Documentation additionnelle
│   ├── usage-guide.md                          # Guide d'utilisation
│   ├── contributing.md                         # Guide de contribution
│   └── migration-guide.md                      # Guide migration versions
│
└── examples/                                    # Exemples d'application
    ├── script-template.sh                      # Template de script
    └── conversation-examples.md                # Exemples de conversations
```

---

## 🚀 Utilisation

### Lecture des règles

Le fichier principal est `regles-contextualisation-globales-v110.md`. Il contient toutes les règles numérotées et organisées par section.

### Consultation du CHANGELOG

Pour voir l'historique complet des modifications :

```bash
cat CHANGELOG.md
```

ou consultez directement sur GitHub.

### Conversion en PDF

```bash
pandoc regles-contextualisation-globales-v110.md \
  -o regles-v110.pdf \
  --standalone \
  --metadata title="Règles de Contextualisation V110" \
  --toc \
  --number-sections
```

### Conversion en DOCX

```bash
pandoc regles-contextualisation-globales-v110.md \
  -o regles-v110.docx \
  --standalone \
  --metadata title="Règles de Contextualisation V110" \
  --toc \
  --number-sections
```

---

## 📚 Sections principales

Le document V110 est organisé en **8 sections principales** :

### 1. 🧩 SOCLE GLOBAL (Règles 1-12)
Règles fondamentales d'application, priorité absolue, inaltérabilité.

**Règles clés :**
- Entrée en vigueur immédiate
- Inaltérabilité absolue
- Priorité sur toute autre directive

### 2. 🔊 MODE VOCAL (Règles 13-22)
Gestion des conversations vocales, contrôle du flux, validation des réponses.

**Règles clés :**
- Attendre "A TOI" avant de parler
- Réponses progressives (4 mots → 2 phrases → 4-5 phrases)
- Réponses sûres à 100%

### 3. 💬 MODE TEXTE (Règles 23-32)
Standards pour les interactions textuelles, gestion de l'historique.

**Règles clés :**
- Ne jamais retirer de contenu
- Toujours inclure exemples dans --help
- Exécution immédiate

### 4. 🎯 TON, STYLE ET LANGAGE (Règles 33-45)
Directives de communication, vocabulaire, ton professionnel.

**Règles clés :**
- Ton clair et direct
- Pas de politesse superflue
- Pas d'excuses mais explications

### 5. ⚙️ SCRIPTING ET GÉNÉRATION DE CODE - V110 MASTER (Règles 46-76)
**Section MASTER** - Règles détaillées pour la génération de scripts et code.

**Sous-sections :**
- Consignes générales (46-49)
- Systemd (50)
- Commentaires (51)
- En-tête et versionnement (52-55)
- Arguments obligatoires (56-61)
- Logs et fichiers (62-64)
- Qualité du code (65-69)
- Changelog (70-73)
- **Formatage tableaux** (74)
- **Gestion .gitignore** (75)
- **Documentation automatique** (76)

### 6. 💡 CLARTÉ ET STRUCTURE (Règles 77-85)
Organisation des réponses, concision, élimination des répétitions.

### 7. 🧩 FILTRES ET RÈGLES SPÉCIALES (Règles 86-88)
Règles transversales, filtrage de contenu.

### 8. 🧾 MÉMOIRE, VERSION ET CONTRÔLE (Règles 89-98)
Gestion des versions, traçabilité, changelog automatique.

---

## ⚙️ Règles de Scripting (Master)

La **section 5** (règles 46-76) est la version **MASTER** des règles de scripting. Elle fait autorité pour toute génération de code.

### Highlights V110

#### 🆕 Gestion automatique du .gitignore (Règle 75)
- Création automatique si inexistant
- Ajout des entrées : `/logs`, `/outputs`, `/results`, `/resume`
- Commentaires d'identification
- Protection contre les duplications
- Journalisation complète

**Exemple de sortie :**
```
# Section ajoutée automatiquement par mon-script.sh
/logs
/outputs
/results
/resume
```

#### 🆕 Documentation automatique (Règle 76)
- Génération auto de `README.md`, `CHANGELOG.md`, `USAGE.md`
- Structure hiérarchique sur 4 niveaux
- Conversion Markdown → PDF/DOCX via pandoc
- Historique intégral préservé
- Synchronisation GitHub

**Fichiers générés :**
```
README.<nom_du_script>.md
CHANGELOG.<nom_du_script>.md
USAGE.<nom_du_script>.md
INSTALL.<nom_du_script>.md (si nécessaire)
```

#### 🆕 Formatage des tableaux (Règle 74)
Standards stricts pour tableaux Markdown :
- Minimum 3 espaces entre texte et `|`
- Alignement visuel des colonnes
- 1 espace avant/après chaque `|`

**Exemple conforme :**
```markdown
| Nom du fichier     | Version | Date       | Rôle/Description           |
|--------------------|---------|------------|----------------------------|
| README.md          | 3.0.1   | 2025-11-02 | Documentation complète     |
```

### Arguments obligatoires

Tout script doit supporter :

- `--help` / `-h` : Aide complète avec exemples
- `--exec` / `-exe` : Exécution principale
- `--prerequis` / `-pr` : Vérification prérequis
- `--install` / `-i` : Installation prérequis
- `--simulate` / `-s` : Mode dry-run
- `--changelog` / `-ch` : Affichage changelog

### Structure standard d'un script

```bash
#!/bin/bash
# Script: /chemin/complet/mon-script.sh
# Auteur: Bruno Delnoz
# Email: bruno.delnoz@protonmail.com
# Version: v1.0.0
# Date: 2025-11-09
# Target usage: Description du script
#
# Changelog:
# v1.0.0 - 2025-11-09 - Version initiale

# ... code ...
```

---

## 🤝 Contribution

### Comment contribuer

1. **Fork** le projet
2. Créer une **branche** pour votre fonctionnalité (`git checkout -b feature/AmazingFeature`)
3. **Commit** vos changements (`git commit -m 'Add some AmazingFeature'`)
4. **Push** vers la branche (`git push origin feature/AmazingFeature`)
5. Ouvrir une **Pull Request**

### Standards de contribution

- Respecter la numérotation existante
- Documenter toute nouvelle règle
- Mettre à jour le CHANGELOG.md
- Tester la cohérence avec les règles existantes
- Fournir des exemples d'application

### Processus de validation

1. Revue par les mainteneurs
2. Vérification de non-duplication
3. Test de cohérence
4. Intégration et mise à jour version

---

## 📜 Historique des versions

| Version | Date       | Règles | Changements majeurs                                    |
|---------|------------|--------|--------------------------------------------------------|
| V110    | 2025-11-09 | 98     | Section scripting master, .gitignore auto, docs auto   |
| V106    | 2025-11-09 | 471    | Consolidation 28 fichiers, élimination doublons        |
| V105    | 2025-10-22 | -      | Remplacement règles scripting section 14               |
| V100    | 2025-10-07 | -      | Version 100 (lite + PERMIT)                            |
| V82     | 2025-10-07 | -      | Fusion V66 + V81                                       |
| V66     | 2025-10-22 | -      | Restructuration complète                               |
| V45     | 2025-09-29 | -      | Version initiale identifiée                            |

Consulter [CHANGELOG.md](CHANGELOG.md) pour l'historique complet.

---

## 📊 Statistiques

### Version actuelle (V110)
- **Règles principales** : 98
- **Sous-règles** : 520+
- **Sections** : 8
- **Taille** : ~45 Ko
- **Réduction vs V106** : -60%

### Couverture
- ✅ Mode vocal : 100%
- ✅ Mode texte : 100%
- ✅ Scripting : 100% (Master)
- ✅ Documentation : 100% (Auto)
- ✅ Gestion Git : 100% (Auto)

---

## 🆘 Support

### Questions fréquentes

**Q: Quelle version utiliser ?**  
R: Toujours utiliser la dernière version (V110). Les versions précédentes sont archivées.

**Q: Comment appliquer les règles ?**  
R: Les règles s'appliquent automatiquement dans les conversations Claude configurées.

**Q: Puis-je modifier les règles ?**  
R: Oui, via Pull Request. Respecter le processus de contribution.

**Q: Les règles sont-elles rétroactives ?**  
R: Oui, elles s'appliquent à tous les chats (anciens, nouveaux, futurs).

### Contact

**Auteur** : Bruno Delnoz  
**Email** : bruno.delnoz@protonmail.com  
**GitHub** : [Lien vers votre profil]

### Signalement de bugs

Ouvrir une **Issue** sur GitHub avec :
- Description du problème
- Règle(s) concernée(s)
- Comportement attendu vs observé
- Exemples reproductibles

---

## 📄 Licence

Ce projet est sous licence [MIT](LICENSE) - voir le fichier LICENSE pour plus de détails.

---

## 🙏 Remerciements

- Communauté Claude
- Contributeurs du projet
- Testeurs et reviewers

---

**Dernière mise à jour** : 2025-11-09  
**Version du document** : V110  
**Statut** : ✅ Production
