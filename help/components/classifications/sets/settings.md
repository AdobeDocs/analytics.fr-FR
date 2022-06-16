---
title: Paramètres du jeu de classifications
description: Créez ou modifiez un jeu de classifications.
exl-id: abf00508-5dde-4669-bf94-5eb4754888cc
source-git-commit: c849f216f8dda83070fc3f8d8b1c25fba4d2786a
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 0%

---

# Paramètres du jeu de classifications

Configurez un jeu de classifications, transférez des données ou téléchargez des données.

**[!UICONTROL Composants]** > **[!UICONTROL Jeux de classifications]** > **[!UICONTROL Visionneuses]** > Cliquez sur le nom du jeu de classifications de votre choix.

Deux onglets sont disponibles lors de la modification d’un jeu de classifications. **[!UICONTROL Schéma]** et **[!UICONTROL Paramètres]**.

## Paramètres 

Les champs suivants sont disponibles dans la variable [!UICONTROL Paramètres] et peut être modifié :

* **[!UICONTROL Nom]**: Nom du jeu de classifications.
* **[!UICONTROL Description]**: Description du jeu de classifications.
* **[!UICONTROL Nom du propriétaire]**: Nom du propriétaire.
* **[!UICONTROL Adresse électronique du propriétaire]**: Adresse électronique du propriétaire.
* **[!UICONTROL Notification des problèmes]**: Liste, délimitée par des virgules, des adresses électroniques qui sont averties des problèmes liés à ce jeu de classifications.
* **[!UICONTROL Balises]**: Ajoutez une ou plusieurs balises au(x) jeu(s) de classifications sélectionné(s), ce qui vous permet d’organiser ou de regrouper des jeux de classifications pour les rendre plus faciles à localiser à l’avenir.

Les champs supplémentaires sont disponibles à titre d’information et ne peuvent pas être modifiés :

* **[!UICONTROL Type]**: Le type de classification entre [!UICONTROL Principal] et [!UICONTROL Recherche]. Les classifications Principal sont généralement utilisées.
* **[!UICONTROL Abonnements]**: Suite de rapports et variable à laquelle s’applique le jeu de classifications. Actuellement, une seule suite de rapports est prise en charge pour un jeu de classifications donné. La prise en charge de plusieurs suites de rapports est prévue.

## Schéma

Afficher les dimensions de classification actuellement configurées pour cet abonnement. Les boutons suivants sont disponibles :

* **[!UICONTROL Télécharger]**: Chargez manuellement des données de classification pour une ou plusieurs dimensions de classification. Les fichiers JSON, CSV, TSV et TAB sont pris en charge. Le téléchargement d’un fichier valide affiche un aperçu du tableau des données à classer.
   * **[!UICONTROL Encodage des fichiers]**: Sélectionnez le codage de fichier correct à l’aide de cette liste déroulante. Les options valides sont les suivantes : [!UICONTROL UTF-8] et [!UICONTROL Latin1].
   * **[!UICONTROL Délimiteur de liste]**: Sélectionnez le délimiteur de liste approprié. Si vous utilisez un fichier téléchargé ou un fichier modèle, assurez-vous que la variable [!UICONTROL Délimiteur de liste] ici correspond à la variable [!UICONTROL Délimiteur de liste] lorsque le fichier a été téléchargé.
   * **[!UICONTROL Appliquer]**: Enregistrez les données de classification chargées dans le jeu de classifications.

   ![Chargement du jeu de classifications](../assets/classification-set-upload.png)

* **[!UICONTROL Télécharger]**: Téléchargez les valeurs clés et leurs colonnes de classification.
   * **[!UICONTROL Lignes]**: Nombre maximal de lignes à inclure dans le fichier de téléchargement.
   * **[!UICONTROL Télécharger les lignes reçues entre]**: Sélecteur de date de calendrier qui vous permet de filtrer les valeurs clés selon le moment où elles apparaissent dans les rapports. Si une valeur de clé n’a pas été collectée au cours de cette période, elle n’apparaît pas dans le fichier téléchargé.
   * **[!UICONTROL Données renvoyées]**: Liste déroulante qui vous permet de filtrer les valeurs clés incluses dans le fichier téléchargé en fonction des données de classification associées.
      * **[!UICONTROL Toutes les valeurs classées]**: Inclut des lignes où des données de classification sont incluses dans au moins une colonne.
      * **[!UICONTROL Toutes les valeurs non classées]**: Inclut les lignes où il manque des données de classification dans au moins une colonne.
   * **[!UICONTROL Format du fichier]**: Liste déroulante qui détermine le format de fichier dans lequel se trouve le fichier de téléchargement. Les options incluent [!UICONTROL JSON], [!UICONTROL Valeurs séparées par des virgules], et [!UICONTROL Valeurs séparées par des tabulations Excel].
   * **[!UICONTROL Encodage des fichiers]**: Liste déroulante qui détermine le codage du fichier. Les options incluent [!UICONTROL UTF-8] et [!UICONTROL Latin1]. UTF-8 est recommandé.
   * **[!UICONTROL Délimiteurs de liste]**: Liste déroulante qui détermine le délimiteur de liste séparant les colonnes de classification de chaque ligne.

   ![Téléchargement du jeu de classifications](../assets/classification-set-download.png)

* **[!UICONTROL Modèle]**: Téléchargez un fichier de modèle. Ce fichier est semblable au fichier [!UICONTROL Télécharger] , sauf qu’elle ne contient aucune donnée de classification ou valeur de clé.
   * **[!UICONTROL Format du fichier]**: Liste déroulante qui détermine le format de fichier dans lequel se trouve le fichier de modèle. Les options incluent [!UICONTROL Valeurs séparées par des virgules], et [!UICONTROL Valeurs séparées par des tabulations Excel].
   * **[!UICONTROL Encodage des fichiers]**: Liste déroulante qui détermine le codage du fichier. Les options incluent [!UICONTROL UTF-8] et [!UICONTROL Latin1]. UTF-8 est recommandé.
   * **[!UICONTROL Délimiteurs de liste]**: Liste déroulante qui détermine le délimiteur de liste séparant les colonnes de classification de chaque ligne.
* **[!UICONTROL Historique des tâches]**: Un lien de raccourci permettant d’accéder à la variable [Job manager](job-manager.md), affichant les tâches uniquement pour ce jeu de classifications.

   ![Modèle de jeu de classifications](../assets/classification-set-template.png)
