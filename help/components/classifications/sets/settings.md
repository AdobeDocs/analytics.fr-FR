---
title: Paramètres des ensembles de classifications
description: Créez ou modifiez un ensemble de classifications.
exl-id: abf00508-5dde-4669-bf94-5eb4754888cc
source-git-commit: 34ba0e09cd909951a777b0ad3da080958633f97e
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 100%

---

# Paramètres des ensembles de classifications

Configurez un ensemble de classifications, chargez des données ou téléchargez des données.

**[!UICONTROL Composants]** > **[!UICONTROL Ensembles de classifications]** > **[!UICONTROL Ensembles]** > Cliquez sur le nom de l’ensemble de classifications de votre choix.

Lorsque vous modifiez un ensemble de classifications, deux onglets sont disponibles : **[!UICONTROL Schéma]** et **[!UICONTROL Paramètres]**.

## Paramètres

Les champs suivants sont disponibles dans l’onglet [!UICONTROL Paramètres] et peuvent être modifiés :

* **[!UICONTROL Nom]** : le nom de l’ensemble de classifications.
* **[!UICONTROL Description]** : la description de l’ensemble de classifications.
* **[!UICONTROL Nom du propriétaire]** : le nom du propriétaire.
* **[!UICONTROL E-mail du propriétaire]** : l’adresse électronique du propriétaire.
* **[!UICONTROL Notifier des problèmes]** : une liste, séparée par des virgules, d’adresses électroniques qui sont notifiées des problèmes de cet ensemble de classifications.
* **[!UICONTROL Balises]** : ajoutez une ou plusieurs balises aux ensembles de classifications sélectionnés, ce qui vous permet d’organiser ou de regrouper les ensembles de classifications afin de les retrouver plus facilement à l’avenir.

Les champs supplémentaires sont disponibles à titre d’information et ne peuvent pas être modifiés :

* **[!UICONTROL Type]** : le type de classification entre [!UICONTROL Principal] et [!UICONTROL Recherche]. Les classifications principales sont généralement utilisées.
* **[!UICONTROL Abonnements]** : la suite de rapports et la variable à laquelle l’ensemble de classifications s’applique. Pour l’instant, une seule suite de rapports est prise en charge pour un ensemble de classifications donné ; la prise en charge de plusieurs suites de rapports est prévue.

## Schéma

Affichez les dimensions de classifications actuellement configurées pour cet abonnement. Les boutons suivants sont disponibles :

* **[!UICONTROL Charger]** : chargez manuellement des données de classification pour une ou plusieurs dimensions de classification. Les fichiers JSON, CSV, TSV et TAB sont pris en charge. Le chargement d’un fichier valide affiche un aperçu sous forme de tableau des données à classer.
   * **[!UICONTROL Encodage du fichier]** : sélectionnez l’encodage du fichier adapté à l’aide de cette liste déroulante. Les options valides comprennent [!UICONTROL UTF-8] et [!UICONTROL Latin1].
   * **[!UICONTROL Délimiteur de liste]** : sélectionnez le délimiteur de liste approprié. Si vous utilisez un fichier téléchargé ou un fichier modèle, assurez-vous que le [!UICONTROL Délimiteur de liste] correspond au [!UICONTROL Délimiteur de liste] utilisé lors du téléchargement du fichier.
   * **[!UICONTROL Appliquer]** : enregistrez les données de classification chargées dans l’ensemble de classifications.

   ![Chargement des ensembles de classifications](../assets/classification-set-upload.png)

* **[!UICONTROL Télécharger]** : téléchargez les valeurs clés et leurs colonnes de classification.
   * **[!UICONTROL Lignes]** : le nombre maximum de lignes à inclure dans le fichier de téléchargement.
   * **[!UICONTROL Télécharger les lignes reçues entre]** : sélecteur de date de calendrier qui vous permet de filtrer les valeurs clés en fonction du moment où elles apparaissent dans les rapports. Si une valeur de clé n’a pas été collectée au cours de cette période, elle n’apparaît pas dans le fichier téléchargé.
   * **[!UICONTROL Données retournées]** : une liste déroulante qui vous permet de filtrer les valeurs clés incluses dans le fichier téléchargé en fonction des données de classifications qui leur sont associées.
      * **[!UICONTROL Toutes les valeurs classées]** : inclut les lignes où les données de classifications sont incluses dans au moins une colonne.
      * **[!UICONTROL Toutes les valeurs non classées]** : inclut les lignes où il manque des données de classifications dans au moins une colonne.
   * **[!UICONTROL Format du fichier]** : liste déroulante qui détermine le format du fichier de téléchargement. Les options incluent [!UICONTROL JSON], les [!UICONTROL valeurs séparées par des virgules] et les [!UICONTROL valeurs séparées par des tabulations Excel].
   * **[!UICONTROL Encodage du fichier]** : liste déroulante qui détermine l’encodage du fichier. Les options comprennent [!UICONTROL UTF-8] et [!UICONTROL Latin1]. UTF-8 est recommandé.
   * **[!UICONTROL Délimiteurs de liste]** : liste déroulante qui détermine le délimiteur de liste séparant les colonnes de classification de chaque ligne.

   ![Téléchargement des ensembles de classifications](../assets/classification-set-download.png)

* **[!UICONTROL Modèle]** : téléchargez un fichier modèle. Ce fichier est similaire au bouton [!UICONTROL Télécharger], sauf qu’il ne contient pas de données de classification ni de valeurs clés.
   * **[!UICONTROL Format de fichier]** : liste déroulante qui détermine le format de fichier du fichier modèle. Les options comprennent les [!UICONTROL valeurs séparées par des virgules] et les [!UICONTROL valeurs séparées par des tabulations Excel].
   * **[!UICONTROL Encodage du fichier]** : liste déroulante qui détermine l’encodage du fichier. Les options comprennent [!UICONTROL UTF-8] et [!UICONTROL Latin1]. UTF-8 est recommandé.
   * **[!UICONTROL Délimiteurs de liste]** : liste déroulante qui détermine le délimiteur de liste séparant les colonnes de classification de chaque ligne.
* **[!UICONTROL Historique des tâches]** : un lien de raccourci qui vous permet d’accéder au [Gestionnaire des tâches](job-manager.md), affichant les tâches uniquement pour cet ensemble de classifications.

   ![Modèle d’ensemble de classifications](../assets/classification-set-template.png)
