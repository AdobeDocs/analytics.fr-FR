---
title: Schéma du jeu de classifications
description: Affichez et modifiez le schéma d’un ensemble de classifications individuel.
exl-id: 4a7c5bfe-ff2b-4380-af46-435801d73c1e
feature: Classifications
source-git-commit: de12253f6db798f49d0cae34bf9cb6b7a3de17db
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 43%

---

# Schéma

Affichez les dimensions de classification actuellement configurées pour cet ensemble de classifications.

**[!UICONTROL Composants]** > **[!UICONTROL Ensembles de classifications]** > **[!UICONTROL Ensembles]** > Cliquez sur le nom de l’ensemble de classifications souhaité > **[!UICONTROL Schéma]**

![interface utilisateur du schéma du jeu de classifications](../../assets/classification-set-schema.png)

Les boutons suivants sont disponibles :

<!--* **[!UICONTROL Add]**: Adds an empty row so that you can add a classification dimension to the schema.-->
* **[!UICONTROL Charger]** : chargez manuellement des données de classification pour une ou plusieurs dimensions de classification. `JSON` fichiers `CSV`, `TSV` et `TAB` sont pris en charge. Le chargement d’un fichier valide affiche un aperçu sous forme de tableau des données à classer.
   * **[!UICONTROL Encodage du fichier]** : sélectionnez l’encodage du fichier approprié à l’aide de cette liste déroulante. Les options valides comprennent [!UICONTROL UTF-8] et [!UICONTROL Latin1].
   * **[!UICONTROL Délimiteur de liste]** : sélectionnez le délimiteur de liste approprié. Si vous utilisez un fichier téléchargé ou un fichier modèle, assurez-vous que le [!UICONTROL Délimiteur de liste] correspond au [!UICONTROL Délimiteur de liste] utilisé lors du téléchargement du fichier.
   * **[!UICONTROL Appliquer]** : enregistrez les données de classification chargées dans l’ensemble de classifications.

  ![Chargement de l’ensemble de classifications](../../assets/classification-set-upload.png)

* **[!UICONTROL Télécharger]** : téléchargez les valeurs clés et leurs colonnes de classification.
   * **[!UICONTROL Lignes]** : le nombre maximum de lignes à inclure dans le fichier de téléchargement.
   * **[!UICONTROL Télécharger les lignes reçues entre]** : sélecteur de date de calendrier qui vous permet de filtrer les valeurs clés en fonction du moment où elles apparaissent dans les rapports. Si une valeur de clé n’a pas été collectée au cours de cette période, elle n’apparaît pas dans le fichier téléchargé.
   * **[!UICONTROL Données renvoyées]** : liste déroulante qui vous permet de filtrer les valeurs clés incluses dans le fichier téléchargé en fonction des données de classification qui leur sont associées.
      * **[!UICONTROL Toutes les valeurs classées]** : inclut les lignes où les données de classifications sont incluses dans au moins une colonne.
      * **[!UICONTROL Toutes les valeurs non classées]** : inclut les lignes où il manque des données de classifications dans au moins une colonne.
   * **[!UICONTROL Format du fichier]** : liste déroulante qui détermine le format de fichier dans lequel se trouve le fichier de téléchargement. Les options incluent [!UICONTROL JSON], les [!UICONTROL valeurs séparées par des virgules] et les [!UICONTROL valeurs séparées par des tabulations Excel].
   * **[!UICONTROL Encodage du fichier]** : liste déroulante qui détermine l’encodage du fichier. Les options comprennent [!UICONTROL UTF-8] et [!UICONTROL Latin1]. UTF-8 est recommandé.

  ![Téléchargement du jeu de classifications](../../assets/classification-set-download.png)

* **[!UICONTROL Modèle]** : téléchargez un fichier modèle. Ce fichier est similaire au bouton [!UICONTROL Télécharger], sauf qu’il ne contient pas de données de classification ni de valeurs clés.
   * **[!UICONTROL Format de fichier]** : liste déroulante qui détermine le format de fichier du fichier modèle. Les options comprennent les [!UICONTROL valeurs séparées par des virgules] et les [!UICONTROL valeurs séparées par des tabulations Excel].
   * **[!UICONTROL Encodage du fichier]** : liste déroulante qui détermine l’encodage du fichier. Les options comprennent [!UICONTROL UTF-8] et [!UICONTROL Latin1]. UTF-8 est recommandé.
   * **[!UICONTROL Délimiteurs de liste]** : liste déroulante qui détermine le délimiteur de liste séparant les colonnes de classification de chaque ligne.

  ![Modèle d’ensemble de classifications](../../assets/classification-set-template.png)

* **[!UICONTROL Historique des tâches]** : un lien de raccourci qui vous mène au [Gestionnaire des tâches](../job-manager.md), affichant les tâches uniquement pour cet ensemble de classifications.
* **[!UICONTROL Automatiser]** : ingérer automatiquement des données à partir d’emplacements de stockage externes.
   * **[!UICONTROL Compte d’emplacement]** : liste déroulante affichant les comptes d’emplacement existants que votre organisation a configurés. Si votre organisation n’a pas encore configuré de compte d’emplacement, vous pouvez en configurer un en sélectionnant [!UICONTROL **Créer un compte**].

     Pour plus d’informations sur la configuration du compte d’emplacement, voir [Configuration des comptes d’import et d’export cloud](/help/components/locations/configure-import-accounts.md).

   * **[!UICONTROL Emplacement]** : liste déroulante affichant les emplacements existants configurés par votre organisation. Si votre organisation n’a pas encore configuré d’emplacement, vous pouvez en configurer un en sélectionnant [!UICONTROL **Créer un emplacement**].

     Pour plus d’informations sur la configuration d’un emplacement, voir [Configuration des emplacements d’importation et d’exportation cloud](/help/components/locations/configure-import-locations.md).

   * **[!UICONTROL Délimiteur]** : délimiteur de colonne pour les fichiers chargés. Les options incluent [!UICONTROL virgule], [!UICONTROL point-virgule], [!UICONTROL deux-points], [!UICONTROL barre verticale], [!UICONTROL espace], [!UICONTROL Barre oblique], [!UICONTROL Barre oblique], [!UICONTROL Dash] ou [!UICONTROL Underscore].

   * **[!UICONTROL Encodage]** : liste déroulante qui détermine l’encodage du fichier. Les options comprennent [!UICONTROL UTF-8] et [!UICONTROL Latin1]. UTF-8 est recommandé.
