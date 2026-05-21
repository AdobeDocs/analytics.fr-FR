---
description: Filtres qui s’appliquent à des termes de dimension spécifiques.
title: Filtres spécifiques
uuid: b3a8187a-3d59-4da0-abca-e933664332e3
feature: Report Builder
role: User, Admin
exl-id: e5f2d67c-3add-4d51-8a76-ee3b2a6eef94
TQID: https://experienceleague.adobe.com/yNIeTJwwWtjXkbi47lX1Ve-Rbz6lF1PazD4YxxXa0Ac
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 336
ht-degree: 46%

---

# Filtres spécifiques

{{legacy-arb}}

Filtres qui s’appliquent à des termes de dimension spécifiques.

Vous pouvez rechercher des éléments de dimension spécifiques en créant un filtre qui correspond à des critères exacts. Vous pouvez, par exemple, créer le type de filtre suivant : page dans [!DNL homepage.htm], [!DNL contact_us.html], [!DNL corporate_info.html].

**Pour créer un filtre spécifique :**

1. Créez ou modifiez une requête, puis passez au formulaire [!UICONTROL Assistant Requête : Étape 2].

   ![Capture d’écran affichant les options Filtrer par : Application, Utilisateur et Projet.](/help/admin/tools/assets/filter.png)

1. Dans la fenêtre [!UICONTROL Assistant Requête : Étape 2], cliquez sur le lien en regard de la dimension dans la grille, puis sélectionnez **[!UICONTROL Filtrer]**.

1. Activez **[!UICONTROL Spécifique]**.

   ![Copie d’écran de la boîte de dialogue Choisir la page avec l’option Spécifique sélectionnée.](assets/choose_page_specific01.png)

1. Activez l’une des options spécifiques suivantes :

   * **À partir d’une plage de cellules :** permet de sélectionner des données à partir de cellules. Vous pouvez sélectionner :
      * **Toutes les cellules de la plage :** permet de mapper chaque cellule de la plage. Le texte descriptif explique le nombre de groupes de cellules que vous devez sélectionner. Pour mapper plusieurs groupes de cellules, appuyez sur la touche Ctrl pendant que vous effectuez des sélections successives. Si la plage qui doit être mappée contient une seule cellule, il s&#39;agit de la seule option disponible
      * **Première cellule de la plage :** il vous suffit de sélectionner la cellule supérieure gauche de la plage, puis de choisir la direction des données. En outre, si la demande comporte plusieurs périodes, vous choisissez la direction des périodes et choisissez si vous souhaitez ignorer un nombre défini de cellules entre les périodes.
   * **De la liste :** permet de sélectionner des données dans une liste à laquelle vous pouvez ajouter des données.
1. Si vous activez l’option **[!UICONTROL À partir de la liste]**, sélectionnez tout élément disponible dans la liste ou cliquez sur **[!UICONTROL Ajouter]**.

   Lorsque vous cliquez sur **[!UICONTROL Ajouter]**, le formulaire [!UICONTROL Sélectionner dans la liste] affiche la liste des éléments de dimension disponibles pour la plage de dates de la requête actuelle, à concurrence des 10 000 premiers éléments. Vous pouvez effectuer une recherche dans ces éléments ou cliquer sur **[!UICONTROL Plus…]** afin d’afficher le [!UICONTROL Formulaire de recherche] dans lequel vous pouvez créer une recherche plus détaillée pour les dimensions.
1. Cliquez sur **[!UICONTROL OK]** dans le formulaire [!UICONTROL Sélectionner dans la liste].
1. Dans le formulaire [!UICONTROL Sélectionner les pages], enregistrez votre filtre spécifique, le cas échéant, puis cliquez sur **[!UICONTROL OK]**.
