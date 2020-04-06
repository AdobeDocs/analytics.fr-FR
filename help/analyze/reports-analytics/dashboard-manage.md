---
description: Utilisez le Gestionnaire de tableaux de bord pour copier, partager, archiver et programmer la remise des tableaux de bord.
subtopic: Dashboards
title: Gestionnaire de tableaux de bord
topic: Reports and analytics
uuid: 380fd148-2ed9-43bf-9d42-46e373e788e4
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Gestionnaire de tableaux de bord

Utilisez le Gestionnaire de tableaux de bord pour copier, partager, archiver et programmer la remise des tableaux de bord.

>[!IMPORTANT]
>
>Lorsque vous utilisez le gestionnaire de tableaux de bord, l’une des bonnes pratiques consiste à ne pas avoir plus de 300 tableaux de bord pour un utilisateur unique. Notez également que le gestionnaire charge tous les tableaux de bord partagés ci-dessous, soyez donc judicieux lorsque vous partagez les tableaux de bord.

## Gestionnaire de tableaux de bord

Utilisez le Gestionnaire de tableaux de bord pour copier, partager, archiver et programmer la remise des tableaux de bord.

Cliquez sur **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Dashboards]**.

| Elément | Description |
|--- |--- |
| Partagé | Indique si le  est partagé. |
| Planifié | Vous permet de programmer le  pour les  de. |
| Afficher l’archive | Cette fonctionnalité n’est plus disponible. |
| Envoyer aux utilisateurs | Vous permet de partager un . |
| Gérer | Permet de modifier, copier et supprimer un  de. |

## Gestion des  partagées

Cette section décrit la procédure à suivre pour utiliser les options de gestion des  partagées.

1. Accédez à **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Dashboards]**.
1. Under [!UICONTROL Shared Dashboards], locate the shared dashboard (or legacy dashboard) you want to manage and choose one or more of the following options:

<table id="choicetable_857E0E816D63404683D4E24DC8D7FC69"> 
 <thead class="chhead sthead"> 
  <th class="choptionhd"> Option </th> 
  <th class="chdeschd"> Description </th> 
 </thead> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Afficher l’archive</strong></td> 
  <td class="chdesc stentry"> Cette fonctionnalité n’est plus disponible. </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Lecteur du tableau de bord</strong></td> 
  <td class="chdesc stentry"> <p>Les serveurs SiteCatalyst 14 ne répondront plus aux demandes de données du lecteur . Tout actuellement affiché dans  Player est accessible dans l’interface standard des rapports et analyses ou recréé sous la forme d’un  en temps réel. Les  en temps réel sont spécialement conçues pour un affichage en continu et incluent un mode plein écran pour vous permettre d’afficher sur les télévisions ou d’autres périphériques grand écran. </p> <p>Action utilisateur requise : Vous devez cesser d'utiliser  Player. </p> </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Mettez-moi en copie</strong></td> 
  <td class="chdesc stentry"> Ajoute une copie à votre  de  de, en utilisant le même nom que l’original. Toutefois, vous ne pouvez pas voir les mises à jour/modifications effectuées par le propriétaire du . La copie d’un hérité  ouvre un  vierge dans lequel vous pouvez ajouter du contenu hérité. <p>Important : si les utilisateurs partagés de votre tableau de bord ne voient pas les modifications que vous avez apportées au tableau de bord, consultez votre Gestionnaire de tableaux de bord pour savoir si les utilisateurs ont activé l’option <span class="uicontrol">Mettez-moi en copie</span>. Si tel est le cas, ils ne peuvent pas voir les mises à jour ou changements que vous avez apportés. Pour afficher tous les changements ou modifications, les utilisateurs partagés doivent cocher l’option <span class="uicontrol">Au menu</span> dans le Gestionnaire de tableaux de bord. </p> </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Au menu</strong></td> 
  <td class="chdesc stentry"> Permet d’afficher les modifications/mises à jour effectuées par le propriétaire du tableau de bord. </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Annuler le partage</strong></td> 
  <td class="chdesc stentry"> Supprime le tableau de bord de la liste des tableaux de bord partagés. </td> 
 </tr> 
</table>

## Migration d’un hérité 

Les  héritées existantes continueront à être exécutées et vous pourrez toujours les modifier, les télécharger et les planifier ; toutefois, vous ne pouvez plus créer de nouveaux  hérités. Nous vous encourageons vivement à mettre à niveau les hérités existants vers le nouveau format  de.

>[!NOTE] Désormais, nous vous invitons à utiliser les [projets d’Analysis Workspace](https://marketing.adobe.com/resources/help/fr_FR/analytics/analysis-workspace/) et leurs fonctionnalités de téléchargement et de planification.

Lorsque vous copiez le  de hérité, le système ouvre le hérité pour modification, où vous pouvez ajouter du contenu hérité ou du nouveau contenu. Lorsque vous copiez un hérité, l’original est conservé dans le de l’ de l’ancienne .

>[!NOTE] L’ajout à un tableau de bord d’un contenu hérité crée un tableau de bord reposant sur la dernière fonctionnalité du tableau de bord. Cependant, le petit rapport hérité peut contenir des données basées sur la plateforme de données précédente.

**Pour migrer un hérité version 14.x**

1. Cliquez sur **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Manage Dashboards]**.
1. Dans la [!UICONTROL Manage] colonne, sous [!UICONTROL Legacy Dashboards], cliquez sur **[!UICONTROL Copy to New Dashboard]**.

   Le  copié s’ouvre dans l’éditeur de mise en page  du.

   See [Editing Dashboard and Reportlet Data](/help/analyze/reports-analytics/dashboard.md).

## Partage d’un 

Cette section décrit la procédure à suivre par un administrateur pour partager (ou pousser) un vers plusieurs utilisateurs. Lorsque vous poussez le  vers les utilisateurs, le  devient disponible dans le [!UICONTROL Shared Dashboards] menu de l’utilisateur.

1. Dans la [!UICONTROL Dashboard Manager], recherchez le , puis activez **[!UICONTROL Shared]**.
1. Cliquez sur **[!UICONTROL Push To Users]**.  ![](assets/push.png)

1. Sur la [!UICONTROL Push Dashboard] page, sélectionnez le  utilisateurs ou cliquez sur **[!UICONTROL Check All]**.
1. Cliquez sur **[!UICONTROL Save]**.

If shared users of your dashboard cannot see changes you made in the dashboard, check your Dashboard Manager to see if the users have chosen the **[!UICONTROL Copy Me]** option. Si tel est le cas, ils ne peuvent pas voir les mises à jour ou changements que vous avez apportés. To see all the changes/updates, shared users need to select the **[!UICONTROL On Menu]** option in the Dashboard Manager.

## Planification d’un  pour les

Dans la [!UICONTROL Dashboard Manager], vous pouvez voir si un  est planifié pour l’ et modifier la planification. Les options de  de sont identiques aux options de  de rapport.

1. Ouvrez un tableau de bord.
1. Cliquez sur **[!UICONTROL More]** > **[!UICONTROL Send]**.

   Pour en savoir plus, reportez-vous à la section [Planification et distribution](/help/analyze/reports-analytics/scheduling.md)

## Archivage d’un tableau de bord

>[!NOTE] Cette fonctionnalité ne sera plus disponible en janvier 2020.

Cette section décrit la procédure à suivre pour archiver un envoyé au format PDF. Le système stocke le fichier archivé pendant deux ans ou jusqu’à ce que vous ayez atteint la limite maximale de 4 Go de rapports archivés, selon ce qui survient en premier.

1. Ouvrez un tableau de bord.
1. Cliquez sur **[!UICONTROL More]** > **[!UICONTROL Send]**.
1. Dans le [!UICONTROL Email Report] groupe, activez **[!UICONTROL Archive]**.
1. Specify delivery options, then click **[!UICONTROL Send]**.

   Vous pouvez  archivé  dans le Gestionnaire de  de l’. Vous pouvez également ouvrir un  et cliquer sur **[!UICONTROL More]** > **[!UICONTROL View Archive]**.
