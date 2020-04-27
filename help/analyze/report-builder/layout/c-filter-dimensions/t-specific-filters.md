---
description: Filtres qui s’appliquent à des termes de dimension spécifiques.
title: Filtres spécifiques
topic: Report builder
uuid: b3a8187a-3d59-4da0-abca-e933664332e3
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Filtres spécifiques

Filtres qui s’appliquent à des termes de dimension spécifiques.

Vous pouvez effectuer une recherche sur des éléments de dimension spécifiques en créant un fichier correspondant exactement aux critères. Vous pouvez, par exemple, créer le type de filtre suivant : page dans [!DNL homepage.htm], [!DNL contact_us.html], [!DNL corporate_info.html].

**Pour créer un filtre spécifique :**

1. Créez ou modifiez une requête, puis accédez au dossier [!UICONTROL Request Wizard: Step 2].

   ![Résultat de l’étape](assets/dimension_filter.png)

1. On the [!UICONTROL Request Wizard: Step 2], click the link next to the dimension in the grid, then choose **[!UICONTROL Filter]**.

   ![Résultat de l’étape](assets/choose_page_specific01.png)

1. Enable **[!UICONTROL Specific]**, then enable one of the following options:

   * **À partir de la plage de cellules** : vous permet de sélectionner des données à partir de cellules. Vous pouvez sélectionner :
   * **Toutes les cellules dans la plage** : vous permet de mapper chaque cellule pour la plage. Un texte descriptif indique le nombre de groupes de cellules à sélectionner. Pour mapper plusieurs groupes de cellules, sélectionnez les éléments de votre choix tout en maintenant la touche Ctrl enfoncée. Si la plage à mapper ne contient qu’une seule cellule, il s’agit de l’unique option disponible.
   * **Première cellule de la plage** : il vous suffit de sélectionner la cellule supérieure gauche de la plage, puis de choisir le sens des données. Si la requête se compose de plusieurs périodes, vous pouvez, en outre, choisir le sens d’affichage et indiquer si vous souhaitez ignorer un nombre défini de cellules entre les périodes.
   * **À partir de la liste** : vous permet de sélectionner, dans une liste, des données auxquelles vous pouvez en ajouter d’autres.
1. If you enable **[!UICONTROL From List]**, select any available listed items or click **[!UICONTROL Add]**.

   When you click **[!UICONTROL Add]**, the [!UICONTROL Select From List] form displays a list of available dimension values for the current request date range, limited to the first 10,000 items. You can search across these items or click **[!UICONTROL More ...]**, which displays the [!UICONTROL Search Form], so that you can create a more detailed search for dimensions.
1. Sur la [!UICONTROL Select From List]page, cliquez sur **[!UICONTROL OK]**.
1. On the [!UICONTROL Choose Page] form, save your Specific filter if you want, then click **[!UICONTROL OK]**.
