---
description: Les contrôles interactifs vous permettent de modifier des segments et des périodes pour une ou plusieurs requêtes directement depuis la feuille de calcul. Ainsi, vous disposez d’une plus grande souplesse lors de la mise à jour des requêtes du Créateur de rapports.
title: Contrôles interactifs
topic: Report builder
uuid: 5f324b61-e032-455e-9947-5037f013e0fa
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Contrôles interactifs

Les contrôles interactifs vous permettent de modifier des segments et des périodes pour une ou plusieurs requêtes directement depuis la feuille de calcul. Ainsi, vous disposez d’une plus grande souplesse lors de la mise à jour des requêtes du Créateur de rapports.

Les contrôles interactifs ont été créés en réponse à un processus courant dans lequel les analystes créent des classeurs et partagent ces classeurs avec l’entité marketing. Les contrôles interactifs permettent aux responsables du marketing de modifier et d’actualiser les requêtes sans devoir posséder une connaissance approfondie du fonctionnement du Créateur de rapports. (Notez qu’afin d’actualiser une requête, le destinataire du classeur doit être un utilisateur du Créateur de rapports.) Ces contrôles fonctionnent dans des classeurs planifiés. Deux types de contrôles interactifs sont actuellement disponibles :

* Période variable
* Segments

>[!IMPORTANT]
>
>Vous devez avoir installé la version 5.0 du créateur de rapports pour que les contrôles interactifs fonctionnent. &gt;
>* Si vous exécutez Microsoft Excel sous Windows mais exécutez une version inférieure du créateur de rapports ou si le créateur de rapports n’est pas installé sur votre ordinateur : Vous pouvez modifier la valeur du contrôle interactif, mais elle n’actualisera pas la requête associée, ni ne mettra à jour les paramètres associés à la requête.
>* Si vous exécutez Excel sous Mac, la modification de la valeur du contrôle entraîne l’affichage du message suivant : "La macro "Adobe.ReportBuilder.Bridge.FormControlClick.Event" est introuvable."
>



>[!IMPORTANT]
>
>Ne modifiez pas le nom du contrôle. (Pour afficher le nom, définissez la mise au point sur le contrôle et le nom du contrôle s’affiche juste au-dessus de la grille Excel, dans le coin supérieur gauche.)

## Implement interactive date range control {#section_39B228F2D2C44985863D31424C953280}

1. À la première étape de l’Assistant Requête, sélectionnez, par exemple, le rapport **[!UICONTROL Page].**
1. En regard du menu déroulant **[!UICONTROL Dates courantes]**, cliquez sur l’icône **Paramètres de commande[!UICONTROL  :]**

   ![](assets/date_range_control.png)

1. Dans la boîte de dialogue Paramètres de commande, sélectionnez tous les éléments de la période que vous souhaitez afficher dans le contrôle interactif. En outre, indiquez l’emplacement de la cellule supérieure gauche du contrôle.

   ![](assets/control_settings.png)

1. Notez l’option "Actualiser automatiquement les requêtes liées lors de la sélection d’un élément".

   * Si cette case est cochée, toutes les requêtes qui utilisent ce contrôle sont actualisées.
   * Si elle n’est pas cochée, les paramètres de requête associés sont mis à jour mais la requête n’est pas actualisée.

1. Cliquez sur **[!UICONTROL OK]**. Le contrôle s’affiche dans l’emplacement de la cellule que vous avez indiqué :

   ![](assets/date_range_control_interactive.png)

1. Vous pouvez à présent modifier la période et la requête s’actualise avec cette période.
1. Vous pouvez également copier la requête et cliquer avec le bouton droit afin d’utiliser une des deux options Coller la requête :

   * **[!UICONTROL Coller la requête]** &gt; **[!UICONTROL Utiliser la cellule]** d’entrée absolue. Cela signifie que la requête copiée pointe vers le même contrôle interactif de périodes que la requête d’origine.

   * **[!UICONTROL Coller la requête]**&gt; **[!UICONTROL Utiliser la cellule]** d’entrée relative. Cela signifie que la requête copiée pointe vers son propre contrôle.

      >[!NOTE]
      >
      >Vous pouvez utiliser la fonctionnalité native de contrôle Couper/Copier/Coller de Microsoft Excel. Le Créateur de rapports reconnaît automatiquement les contrôles nouvellement ajoutés.

## Implement interactive segment control {#section_5003D3F724644280BF1BCD6E1B0CB784}

L’implémentation du contrôle interactif de segments est similaire à l’implémentation du contrôle de périodes.

1. À l’étape 1 de l’Assistant Requête, en regard de la liste déroulante **[!UICONTROL Segment], cliquez sur l’icône des paramètres de commande de segments :**

   ![](assets/segment_interactive_1.png)

1. Dans la boîte de dialogue Paramètres de commande, sélectionnez les segments que vous souhaitez inclure dans la liste déroulante. En outre, indiquez l’emplacement de la cellule supérieure gauche du contrôle.

   ![](assets/segment_drop_down_properties.png)

1. Le nouveau contrôle interactif s’affiche à présent dans le classeur :

   ![](assets/segment_interactive_3.png)

