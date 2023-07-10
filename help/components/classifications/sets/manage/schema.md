---
title: Schéma du jeu de classifications
description: Affichez et modifiez le schéma d’un jeu de classifications individuel.
exl-id: 0fc12a0c-c1cf-4159-9d8b-492ebcaa8ea1
feature: Classifications
source-git-commit: 6cc7f491340ec7c36252f7ae53de07b0ab8f3b6f
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 42%

---

# Schéma

Affichez les dimensions de classification actuellement configurées pour ce jeu de classifications.

**[!UICONTROL Composants]** > **[!UICONTROL Jeux de classifications]** > **[!UICONTROL Visionneuses]** > Cliquez sur le nom du jeu de classifications de votre choix > **[!UICONTROL Schéma]**

Les boutons suivants sont disponibles :

<!--* **[!UICONTROL Add]**: Adds an empty row so that you can add a classification dimension to the schema.-->
* **[!UICONTROL Charger]** : chargez manuellement des données de classification pour une ou plusieurs dimensions de classification. `JSON`, `CSV`, `TSV`, et `TAB` Les fichiers sont pris en charge. Le chargement d’un fichier valide affiche un aperçu sous forme de tableau des données à classer.
   * **[!UICONTROL Encodage des fichiers]**: Sélectionnez le codage de fichier correct à l’aide de cette liste déroulante. Les options valides comprennent [!UICONTROL UTF-8] et [!UICONTROL Latin1].
   * **[!UICONTROL Délimiteur de liste]** : sélectionnez le délimiteur de liste approprié. Si vous utilisez un fichier téléchargé ou un fichier modèle, assurez-vous que le [!UICONTROL Délimiteur de liste] correspond au [!UICONTROL Délimiteur de liste] utilisé lors du téléchargement du fichier.
   * **[!UICONTROL Appliquer]**: Enregistrez les données de classification chargées dans le jeu de classifications.

  ![Chargement d’un jeu de classifications](../../assets/classification-set-upload.png)

* **[!UICONTROL Télécharger]** : téléchargez les valeurs clés et leurs colonnes de classification.
   * **[!UICONTROL Lignes]** : le nombre maximum de lignes à inclure dans le fichier de téléchargement.
   * **[!UICONTROL Télécharger les lignes reçues entre]** : sélecteur de date de calendrier qui vous permet de filtrer les valeurs clés en fonction du moment où elles apparaissent dans les rapports. Si une valeur de clé n’a pas été collectée au cours de cette période, elle n’apparaît pas dans le fichier téléchargé.
   * **[!UICONTROL Données renvoyées]**: Liste déroulante qui vous permet de filtrer les valeurs clés incluses dans le fichier téléchargé en fonction des données de classification associées.
      * **[!UICONTROL Toutes les valeurs classées]** : inclut les lignes où les données de classifications sont incluses dans au moins une colonne.
      * **[!UICONTROL Toutes les valeurs non classées]** : inclut les lignes où il manque des données de classifications dans au moins une colonne.
   * **[!UICONTROL Format du fichier]**: Liste déroulante qui détermine le format de fichier dans lequel se trouve le fichier de téléchargement. Les options incluent [!UICONTROL JSON], les [!UICONTROL valeurs séparées par des virgules] et les [!UICONTROL valeurs séparées par des tabulations Excel].
   * **[!UICONTROL Encodage des fichiers]**: Liste déroulante qui détermine le codage du fichier. Les options comprennent [!UICONTROL UTF-8] et [!UICONTROL Latin1]. UTF-8 est recommandé.

  ![Téléchargement du jeu de classifications](../../assets/classification-set-download.png)

* **[!UICONTROL Modèle]** : téléchargez un fichier modèle. Ce fichier est similaire au bouton [!UICONTROL Télécharger], sauf qu’il ne contient pas de données de classification ni de valeurs clés.
   * **[!UICONTROL Format du fichier]**: Liste déroulante qui détermine le format de fichier dans lequel se trouve le fichier de modèle. Les options comprennent les [!UICONTROL valeurs séparées par des virgules] et les [!UICONTROL valeurs séparées par des tabulations Excel].
   * **[!UICONTROL Encodage des fichiers]**: Liste déroulante qui détermine le codage du fichier. Les options comprennent [!UICONTROL UTF-8] et [!UICONTROL Latin1]. UTF-8 est recommandé.
   * **[!UICONTROL Délimiteurs de liste]**: Liste déroulante qui détermine le délimiteur de liste séparant les colonnes de classification de chaque ligne.

  ![Modèle de jeu de classifications](../../assets/classification-set-template.png)

* **[!UICONTROL Historique des tâches]**: Un lien de raccourci permettant d’accéder à la variable [Job manager](../job-manager.md), affichant les tâches uniquement pour ce jeu de classifications.
* **[!UICONTROL Automatiser]**: ingérer automatiquement des données à partir d’emplacements de stockage externes ;
   * **[!UICONTROL Compte d’emplacement]**: Liste déroulante présentant les comptes d’emplacement que votre entreprise a configurés. Si votre organisation n’a pas encore configuré de compte d’emplacement, vous pouvez en configurer un en sélectionnant [!UICONTROL **Création d’un compte**].

     Pour plus d’informations sur la configuration du compte d’emplacement, voir [Configuration des emplacements d’importation dans le cloud](/help/components/classifications/importer/configure-import-accounts.md).

   * **[!UICONTROL Emplacement]**: Liste déroulante présentant les emplacements existants configurés par votre organisation. Si votre organisation n’a pas encore configuré d’emplacement, vous pouvez en configurer un en sélectionnant [!UICONTROL **Création d’un emplacement**].

     Pour plus d’informations sur la configuration d’un emplacement, voir [Configuration des emplacements d’importation dans le cloud](/help/components/classifications/importer/configure-import-accounts.md).

   * **[!UICONTROL Délimiteur]**: Délimiteur de colonne pour les fichiers chargés. Les options incluent [!UICONTROL Virgule], [!UICONTROL Point-virgule], [!UICONTROL deux points], [!UICONTROL Barre verticale], [!UICONTROL Espace], [!UICONTROL Barre oblique], [!UICONTROL Barre oblique inverse], [!UICONTROL Dash]ou [!UICONTROL Soulignement].

   * **[!UICONTROL Encodage]**: Liste déroulante qui détermine le codage du fichier. Les options comprennent [!UICONTROL UTF-8] et [!UICONTROL Latin1]. UTF-8 est recommandé.
