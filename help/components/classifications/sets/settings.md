---
title: Paramètres du jeu de classifications
description: Créez ou modifiez un jeu de classifications.
source-git-commit: c9465ea0524225494aa5067d00ca5e7aba4bca92
workflow-type: tm+mt
source-wordcount: '286'
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
