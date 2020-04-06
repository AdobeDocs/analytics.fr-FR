---
description: Comment ajouter, modifier, appliquer et filtrer des segments Adobe Analytics dans le Report Builder.
title: Gestion des segments
topic: Report builder
uuid: 4e4edc39-ed93-498f-913d-7b231b10e7a0
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Gestion des segments

Comment ajouter, modifier, appliquer et filtrer des segments Adobe Analytics dans le Report Builder.

Le Report Builder inclut un panneau de segmentation à l’étape 1 de l’Assistant Requête qui permet de créer et gérer des segments.

![](assets/seg_dialog.png)

## Ajouter ou modifier des segments {#section_B2BC136F9A53498D90C7C2ECC5DB892B}

>[!NOTE] Pour ajouter ou modifier des segments, l’interface de segments du Report Builder lance le Créateur de segments d’Analytics dans une fenêtre Microsoft Internet Explorer. Votre session du créateur de rapports restera active. Les navigateurs autres qu’Internet Explorer ne sont pas pris en charge pour cette opération.

1. Dans le panneau de segments de l’étape 1 de l’Assistant Requête, cliquez sur **[!UICONTROL Add]**.
1. Une fenêtre Internet Explorer s’ouvre et ouvre l’interface du créateur de segments d’Analytics. Pour plus d’informations sur la création de segments, voir [https://marketing.adobe.com/resources/help/en_US/analytics/segment/](https://marketing.adobe.com/resources/help/fr_FR/analytics/segment/).
1. Après avoir défini et enregistré le segment, revenez à l’Assistant Requête.
1. Cliquez sur l’icône Actualiser pour actualiser le de segments.

>[!IMPORTANT]
>
>Cette liste est placée en mémoire cache ; le segment nouvellement créé s’affichera uniquement si vous actualisez la page.

## Créer des segments dans le contexte {#section_6DD2C663B2854469AA1075438F907678}

Vous souhaitez peut-être transformer en segments des associations spécifiques de dimensions de rapport. Vous pouvez créer ces segments depuis l’interface du Report Builder. Par exemple, sélectionnez quelques pages dans une sortie de requête de page et créez un segment basé sur ces valeurs.

1. Sélectionnez les éléments de sortie du rapport que vous souhaitez transformer en segment.
1. Right-click to select **[!UICONTROL Create In-Context Segment in]** and specify the right container (Hits Container, Visits Container, Visitor Container).

   ![](assets/seg_in_context.png)

   Pour plus d’informations sur les  de, consultez le Guide [de](https://marketing.adobe.com/resources/help/fr_FR/analytics/segment/)segmentation.

1. L’interface utilisateur du créateur de segments sera désormais lancée dans Internet Explorer. L’interface utilisateur du créateur de segments sera initialisée avec le  de et le filtre que vous avez spécifiés.
1. Après avoir ajouté un nom et une description au segment, enregistrez-le.
1. Revenez au créateur de rapports et cliquez sur l’icône Actualiser pour actualiser le  des segments.
1. Vous êtes maintenant prêt à appliquer ce segment.

## Recherche et application de segments {#section_CACA269B48E94CFD91C2D5A15E9C77B7}

Chaque segment créé dans les Reports &amp; Analytics, dans Ad Hoc Analysis, dans Report Builder ou dans Data Warehouse est répertorié dans cette liste de segments. Pour actualiser la liste, cliquez sur l’icône Actualiser ( ![](assets/refresh_icon.png).

Vous pouvez appliquer un ou plusieurs segments à toute requête donnée. Cela inclut les segments séquentiels.

1. Go to the **[!UICONTROL Segment]** drop-down list and click the small down arrow in the **[!UICONTROL Choose Segment]** box to display all the segments.

   ![](assets/seg_list.png)

1. Cochez le ou les segments que vous souhaitez appliquer.

>[!NOTE] Dans le Report Builder, que vous soyez administrateur ou non, vous ne pouvez consulter que les segments que vous possédez et ceux qui ont été partagés avec vous. (Dans l’interface utilisateur de Reports &amp; Analytics marketing, l’administrateur peut consulter tous les segments de l’entreprise.)

## Filtrage des segments {#section_376E986D3E684999A7CDB08E53854159}

**Filtrez** les segments en cliquant sur l’icône Filtrer : ![](assets/segment_filter.png)

 de disponibles :

| Nom du filtre | Description |
|---|---|
| Balises | Permet de filtrer les segments selon des balises spécifiques balises. Notez que le de balises  utilise l’opérateur ET. Si vous cochez deux balises, le volet de droite affiche les segments qui ont été balisés avec **les deux** balises. |
| Propriétaires | Permet de filtrer les segments par propriétaire. Notez que les propriétaires  utilisent l’opérateur OU. Si vous cochez deux propriétaires, le volet de droite affiche les segments qui appartiennent à **l’un ou l’autre** des propriétaires. |
| Autres  > Nom de la suite de *rapports uniquement* | Si vous appliquez le filtre « Uniquement *le nom de la suite de rapports* » dans le Créateur de segments dans [!DNL marketing reports & analytics], puis affichez le filtre avancé dans [!DNL report builder], le filtre avancé affiche uniquement le segment correspondant à la suite de rapports sélectionnée. |
| Autres filtres > À moi | Affiche tous les segments que vous possédez. |
| Autres filtres > Partagés avec moi | Affiche tous les segments que d’autres ont partagé avec vous. |
| Autres filtres > Favoris | Affiche tous les segments que vous avez marqués comme Favoris. |
| Autres filtres > Approuvés | Affiche toutes les mesures approuvés. |

## Ajouter un contrôle de segments à un classeur {#section_E3E5149A8464441FA5445A98DBD520AC}

L’ajout d’un contrôle de segments vous permet de basculer entre les segments dans un classeur au lieu d’avoir à accéder à l’Assistant Requête.

1. Cliquez sur l’icône de contrôle ![](assets/control_icon.png) en regard de la liste déroulante de segments.

   ![](assets/seg_control.png)

1. Vérifiez tous les segments que vous souhaitez voir apparaître dans le contrôle de segments ou cochez **[!UICONTROL Select All]**.
1. Remarquez l&#39;option **[!UICONTROL Automatically refresh linked requests upon item selection]**.

   * Si cette option est cochée, toutes les requêtes qui utilisent ce contrôle sont actualisées.
   * Si elle n’est pas cochée, les paramètres de requête associés sont mis à jour, mais les requêtes ne sont pas actualisées.

1. Spécifiez l’emplacement de la cellule supérieure gauche du contrôle de segment.
1. Cliquez sur **[!UICONTROL OK]** et le contrôle de segment s’affiche à l’emplacement spécifié.

   ![](assets/seg_control2.png)

## Actualisation de la liste de segments {#section_22E4A86789444B4A998532396B476EFB}

Chaque fois que vous ajoutez un nouveau segment ou en modifiez un existant, vous devez cliquer sur l’icône Actualiser (![](assets/refresh_icon.png) afin d’actualiser la liste mise en cache de segments.

## Gérer les segments à travers les requêtes {#section_C3D63FCBE1A94369A319243313B03C93}

Avant la version 5.4, les utilisateurs pouvaient modifier les segments pour plusieurs demandes dans le Report Builder. Toutefois, ce processus remplaçait systématiquement les segments existants. Les utilisateurs qui souhaitaient ajouter un nouveau segment à chaque requête ne pouvaient pas le faire, car l’ajout du segment supprimait le jeu précédent de segments déjà affectés à chaque requête.

Dans la version 5.4 du Report Builder, vous pouvez ajouter, supprimer et remplacer un ou tous les segments dans plusieurs demandes :

1. Sélectionnez plusieurs requêtes dans un classeur.
1. Cliquez avec le bouton droit de la souris et sélectionnez **[!UICONTROL Edit Requests]** > **[!UICONTROL By Segment]**.

   ![](assets/edit_by_segment.png)

1. Dans la boîte de dialogue Modifier le groupe, sélectionnez l’une des quatre options suivantes :

   | Option | Description |
   |---|---|
   | Ajouter Segment | Vous permet de choisir un ou plusieurs segments à ajouter au  du ou des segments actuels. |
   | Remplacer les segments | Permet de choisir le ou les segments à remplacer par un ou plusieurs segments. |
   | Remplacer tous les segments par | Permet de choisir un ou plusieurs segments par lesquels remplacer le ou les segments actuels. |
   | Supprimer le ou les segments | Permet de supprimer des segments des requêtes. |

