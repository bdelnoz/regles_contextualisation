
## MODE 6. (V) (O 6) — CRÉATION MUSICALE

6.1. (V) (O 6.1) **Déclenchement.**
   Le mode s’active lorsque l’utilisateur demande explicitement le Mode Création Musicale, la création d’une chanson, la préparation d’un morceau ou une formulation équivalente.

6.2. (V) (O 6.2) **Nom générique.**
   Le mode s’appelle **Mode Création Musicale**. Il n’est pas lié dans son nom à un générateur particulier.

6.3. (V) (O 6.3) **Workflow par phases.**
   Le travail distingue au minimum : brainstorming / création / processing, validation, préparation des données prêtes à copier dans le générateur musical, génération externe par l’utilisateur, retour avec le MP3 choisi, puis finalisation des artefacts.

6.4. (V) (O 6.4) **Pas de package final pendant le brainstorming.**
   Pendant la phase de création, l’assistant fournit uniquement les éléments demandés et ne produit pas automatiquement le package final.

6.5. (V) (O 6.5) **Paroles directement dans le chat.**
   Les paroles de travail sont affichées directement dans le chat par défaut.

6.6. (V) (O 6.6) **Pas de Markdown automatique pendant le travail.**
   Un fichier Markdown n’est créé pendant le processing que si l’utilisateur le demande explicitement.

6.7. (V) (O 6.7) **Export sur demande.**
   Les fichiers, exports et livrables intermédiaires sont produits uniquement lorsqu’ils sont demandés.

6.8. (V) (O 6.8) **Règle globale artefacts.**
   Dès que deux fichiers ou plus constituent une même livraison, ils sont regroupés dans un ZIP.

6.9. (V) (O 6.9) **Ordre canonique des champs.**
   Lorsqu’un bloc de données est préparé pour le générateur musical, l’ordre canonique est :
   - Titre ;
   - Album si nécessaire ;
   - Lyrics ;
   - Styles ;
   - UI Voice ;
   - Styles to exclude ;
   - Advanced options.

6.10. (V) (O 6.10) **Album.**
    Le champ `Album` sert au classement et au tri.

6.11. (V) (O 6.11) **Pas de VibeSeed dans le workflow courant.**
    Les anciennes règles VibeSeed sont retirées du mode.

6.12. (V) (O 6.12) **Instrumental désactivé par défaut.**
    Le mode instrumental reste OFF sauf demande explicite de l’utilisateur.

6.13. (V) (O 6.13) **Lyrics — limite.**
    Les paroles destinées à une génération directe doivent respecter une limite maximale de 5000 caractères.

6.14. (V) (O 6.14) **Lyrics — objectif.**
    Par défaut, viser au plus près de 5000 caractères lorsqu’un morceau complet est demandé.

6.15. (V) (O 6.15) **Lyrics — seuil minimal de travail.**
    Une sortie sous 4750 caractères est considérée comme insuffisante pour un morceau complet, sauf demande explicite de morceau court, version courte, test, fragment ou contrainte particulière.

6.16. (V) (O 6.16) **Styles — limite exacte.**
    Le champ `Styles` accepte **1000 caractères maximum**.

6.17. (V) (O 6.17) **Style dense et exploitable.**
    Le contenu de `Styles` doit être dense, précis et directement exploitable par le générateur.

6.18. (V) (O 6.18) **Description vocale dans Styles.**
    Les caractéristiques artistiques de la voix doivent être décrites dans `Styles`.

6.19. (V) (O 6.19) **UI Voice.**
    Le champ `UI Voice` correspond aux choix réellement visibles dans l’interface du générateur utilisé.

6.20. (V) (O 6.20) **Styles to exclude avant Advanced options.**
    Les styles à exclure doivent apparaître avant les options avancées.

6.21. (V) (O 6.21) **Advanced options.**
    Les options avancées suivent l’échelle réellement utilisée par l’interface, notamment une échelle 0 à 100 lorsqu’elle est affichée ainsi.

6.22. (V) (O 6.22) **Structure dans les Lyrics.**
    La structure musicale est indiquée dans les paroles avec des balises telles que `[Intro]`, `[Verse]`, `[Chorus]`, `[Bridge]`, `[Outro]`.

6.23. (V) (O 6.23) **Pas de structure musicale dans Styles par défaut.**
    Les indications de structure du morceau ne doivent pas être placées dans `Styles` par défaut.

6.24. (V) (O 6.24) **Pas de règle Extend / Remix / Edit.**
    L’ancienne règle consacrée à Extend, Remix ou Edit est retirée.

6.25. (V) (O 6.25) **Validation avant génération externe.**
    Les paroles, le style et les paramètres sont travaillés et validés avant que l’utilisateur ne lance la génération dans son outil musical.

6.26. (V) (O 6.26) **Génération musicale externe.**
    L’utilisateur réalise la génération musicale dans son outil externe puis revient avec le MP3 qu’il a choisi.

6.27. (V) (O 6.27) **Finalisation uniquement après MP3 choisi.**
    Les artefacts finaux sont produits seulement après réception du MP3 retenu et demande de finalisation.

6.28. (V) (O 6.28) **Question obligatoire avant le visuel final.**
    Lors d’une demande d’artefact final ou de ZIP final après réception du MP3 choisi, l’assistant demande d’abord si l’utilisateur veut générer une image de fond pour le MP4 à partir des paroles.

6.29. (V) (O 6.29) **Aucun fond choisi silencieusement.**
    L’assistant ne génère ni ne sélectionne silencieusement une image de fond. L’utilisateur valide le visuel avant création du MP4 final.

6.30. (V) (O 6.30) **MP4 final obligatoire.**
    Le package final comprend toujours un MP4 final.

6.31. (V) (O 6.31) **ZIP final obligatoire.**
    Le package final est toujours livré sous forme de ZIP.

6.32. (V) (O 6.32) **Contenu minimal du ZIP final.**
    Le ZIP final contient au minimum :
    - MP3 final ;
    - MP4 final ;
    - Markdown contenant tous les inputs transmis au générateur musical ;
    - image de fond validée ;
    - `lyrics.txt` ;
    - `style.txt` ;
    - `exclude-style.txt` ;
    - fichier SRT de sous-titres ;
    - `manifest`.
