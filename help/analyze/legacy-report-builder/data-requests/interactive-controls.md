---
description: Les contrôles interactifs vous permettent de modifier des segments et des périodes pour une ou plusieurs requêtes directement à partir de la feuille de calcul. Vous bénéficiez ainsi d’une plus grande flexibilité lors de la mise à jour des requêtes Report Builder.
title: Contrôles interactifs
feature: Report Builder
role: User, Admin
exl-id: 2340ff31-1478-4a54-a4c3-c51e73c39109
TQID: https://experienceleague.adobe.com/I1Lw6gp33QByF6J9SZRgTdn30CpdhJH3yWZ5XwOkBqc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 603
ht-degree: 31%

---

# Contrôles interactifs

{{legacy-arb}}

Les contrôles interactifs vous permettent de modifier des segments et des périodes pour une ou plusieurs requêtes directement à partir de la feuille de calcul. Vous bénéficiez ainsi d’une plus grande flexibilité lors de la mise à jour des requêtes Report Builder.

Les contrôles interactifs ont été créés en réponse à un workflow commun où les analystes créent des classeurs et partagent ces classeurs avec l’organisation marketing. Les contrôles interactifs permettent aux spécialistes marketing de modifier et d’actualiser les requêtes sans avoir à connaître en profondeur le fonctionnement de Report Builder. (Notez que pour actualiser une demande, le destinataire du classeur doit être un utilisateur Report Builder.) Ces commandes fonctionnent dans les classeurs planifiés. Deux types de contrôles interactifs sont actuellement disponibles :

* Période variable
* Segments

>[!IMPORTANT]
>
>La version 5.0 du Report Builder doit être installée pour que les contrôles interactifs fonctionnent. >
>* Si vous exécutez Microsoft Excel sous Windows, mais que vous utilisez une version antérieure de Report Builder, ou si Report Builder n’est pas installé : vous pouvez modifier la valeur dans le contrôle interactif, mais cela n’actualisera pas la requête associée, ni ne mettra à jour les paramètres associés à la requête.
>* Si vous exécutez Excel sous Mac, la modification de la valeur dans le contrôle déclenche l’affichage du message suivant : « Macro ’Adobe.ReportBuilder.Bridge.FormControlClick.Event&#39;. »
>

>[!WARNING]
>
>Ne modifiez pas le nom du contrôle. (Pour afficher le nom, définissez la mise au point sur le contrôle et le nom du contrôle s’affiche juste au-dessus de la grille Excel, dans le coin supérieur gauche.)

## Implémenter le contrôle interactif des périodes {#section_39B228F2D2C44985863D31424C953280}

1. À la première étape de l’Assistant Requête, sélectionnez, par exemple, le rapport **[!UICONTROL Page]**.
1. En regard du menu déroulant **[!UICONTROL Dates courantes]**, cliquez sur l’icône **[!UICONTROL Paramètres de commande]** :

   ![Capture d’écran de l’étape 1 de l’Assistant Requête mettant en surbrillance l’icône Paramètres de contrôle. ](assets/date_range_control.png)

1. Dans la boîte de dialogue Paramètres de contrôle, sélectionnez tous les éléments de période que vous souhaitez afficher dans le contrôle interactif. Spécifiez également l&#39;emplacement de la cellule supérieure gauche du contrôle.

   ![Capture d’écran affichant les éléments de période sélectionnés et l’emplacement de la cellule supérieure gauche.](assets/control_settings.png)

1. Notez l’option permettant d’« Actualiser automatiquement les requêtes liées lors de la sélection ».

   * Si cette case est cochée, toutes les requêtes qui utilisent ce contrôle sont actualisées.
   * Si cette option n’est pas cochée, les paramètres de requête associés sont mis à jour, mais la requête n’est pas actualisée.

1. Cliquez sur **[!UICONTROL OK]**. Le contrôle s&#39;affiche à l&#39;emplacement de la cellule que vous avez spécifiée :

1. Vous pouvez désormais modifier la période, et la requête s’actualisera avec cette période.

   ![Capture d’écran affichant la période sélectionnée.](assets/date_range_control_interactive.png)

1. Vous pouvez également copier la requête et effectuer un clic droit pour utiliser l’une des deux options de Coller la requête :

   * **[!UICONTROL Coller la demande]** > **[!UICONTROL Utiliser la cellule d’entrée absolue]**. Cela signifie que la requête copiée pointe vers le même contrôle interactif de période que la requête d’origine.

   * **[!UICONTROL Coller la requête]** > **[!UICONTROL Utiliser la cellule d’entrée relative]**. Cela signifie que la requête copiée pointe vers son propre contrôle.

     >[!NOTE]
     >
     >Vous pouvez utiliser la fonctionnalité de contrôle Couper/Copier/Coller native de Microsoft Excel. Le Créateur de rapports reconnaît automatiquement les contrôles nouvellement ajoutés.

## Implémenter le contrôle interactif des segments {#section_5003D3F724644280BF1BCD6E1B0CB784}

L’implémentation du contrôle interactif des segments est similaire à l’implémentation du contrôle des périodes.

1. À l’étape 1 de l’Assistant Requête, en regard de la liste déroulante **[!UICONTROL Segment]**, sélectionnez l’icône Paramètres de contrôle des segments :

   ![Capture d’écran de l’icône Paramètres de contrôle des segments.](assets/segment_interactive_1.png)

1. Dans la boîte de dialogue Paramètres de commande, sélectionnez les segments que vous souhaitez inclure dans la liste déroulante. Spécifiez également l&#39;emplacement de la cellule supérieure gauche du contrôle.

   ![Capture d’écran affichant les paramètres de contrôle des segments avec les segments sélectionnés et l’emplacement de la cellule.](assets/segment_drop_down_properties.png)

1. La nouvelle commande interactive apparaît désormais dans le classeur :

   ![Capture d&#39;écran affichant le nouveau contrôle interactif sélectionné.](assets/segment_interactive_3.png)
