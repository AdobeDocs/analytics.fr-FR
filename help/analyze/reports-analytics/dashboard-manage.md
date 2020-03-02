---
description: Utilisez le Gestionnaire de tableaux de bord pour copier, partager, archiver et programmer la remise des tableaux de bord.
subtopic: Dashboards
title: Gestionnaire de tableaux de bord
topic: Reports and analytics
uuid: 380fd148-2ed9-43bf-9d42-46e373e788e4
translation-type: tm+mt
source-git-commit: 92eaaeafdd587febcfe7fe60f696baca0691b4bc

---


# Gestionnaire de tableaux de bord

Utilisez le Gestionnaire de tableaux de bord pour copier, partager, archiver et programmer la remise des tableaux de bord.

>[!IMPORTANT]
>
>Lors de l’utilisation du Gestionnaire de tableaux de bord, il est recommandé de ne pas avoir plus de 300 tableaux de bord pour un seul utilisateur. Notez également que le gestionnaire charge tous les tableaux de bord partagés ci-dessous. Soyez donc judicieux lorsque vous partagez des tableaux de bord.

## Gestionnaire de tableaux de bord

Utilisez le Gestionnaire de tableaux de bord pour copier, partager, archiver et programmer la remise des tableaux de bord.

Cliquez sur **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Dashboards]**.

| Élément | Description |
|--- |--- |
| Partagé | Indique si le tableau de bord est partagé. |
| Programmé | Permet de programmer la remise du tableau de bord. |
| Afficher l’archive | Cette fonctionnalité n’est plus disponible. |
| Envoyer aux utilisateurs | Permet de partager un tableau de bord. |
| Gérer | Permet de modifier, de copier et de supprimer un tableau de bord.  |

## Gestion des tableaux de bord partagés

Étapes décrivant comment utiliser les options de gestion du tableau de bord partagé.

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
  <td class="chdesc stentry"> <p>Les serveurs SiteCatalyst 14 ne répondront désormais plus aux requêtes de données du lecteur de tableau de bord. Tous les tableaux de bord actuellement affichés dans le lecteur du tableau de bord peuvent être accessibles depuis l’interface Reports &amp; Analytics standard ou recréés en tant que tableaux de bord en temps réel. Les tableaux de bord en temps réel ont été spécifiquement conçus pour un affichage en continu et incluent un mode plein écran qui vous permet d’afficher l’écran sur des télévisions ou d’autres périphériques avec un grand écran. </p> <p>Action utilisateur requise : vous devez arrêter l’utilisation du lecteur de tableau de bord. </p> </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Mettez-moi en copie</strong></td> 
  <td class="chdesc stentry"> Ajoute une copie à la liste des tableaux de bord, en utilisant le même nom que pour l’original. Néanmoins, vous ne pouvez pas afficher les mises à jour/modifications effectuées par le propriétaire du tableau de bord. La copie d’un tableau de bord hérité ouvre un tableau de bord vierge, dans lequel vous pouvez ajouter du contenu hérité. <p>Important : Si les utilisateurs partagés de votre tableau de bord ne voient pas les modifications que vous avez apportées au tableau de bord, consultez votre Gestionnaire de tableaux de bord pour savoir si les utilisateurs ont activé l’option <span class="uicontrol">Mettez-moi en copie</span>. Si tel est le cas, ils ne peuvent pas voir les mises à jour ou changements que vous avez apportés. Pour afficher tous les changements ou modifications, les utilisateurs partagés doivent cocher l’option <span class="uicontrol">Au menu</span> dans le Gestionnaire de tableaux de bord. </p> </td> 
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

## Migration d’un tableau de bord hérité

Les tableaux de bord hérités existants continueront à être exécutés et vous serez toujours en mesure de les modifier, télécharger et programme. Toutefois, vous ne pourrez plus créer de nouveaux tableaux de bord hérités. Nous vous recommandons fortement de mettre à niveau les tableaux de bord hérités existants vers le format de tableau de bord plus récent.

> [!NOTE] À partir de maintenant, pensez à utiliser les projets [](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/) Analysis Workspace et à leur capacité à être téléchargés et planifiés.

Lorsque vous copiez le tableau de bord hérité, le système l’ouvre pour modification et vous pouvez y ajouter du contenu hérité ou du nouveau contenu. Lorsque vous copiez un tableau de bord hérité, l’original est préservé dans la liste des tableaux de bord hérités.

> [!NOTE] L’ajout de contenu hérité à un tableau de bord crée un tableau de bord basé sur la dernière fonctionnalité du tableau de bord. Le mini-rapport hérité peut toutefois contenir des données reposant sur la plateforme de données précédentes.

**Pour migrer un tableau de bord hérité version 14.x**

1. Cliquez sur **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Manage Dashboards]**.
1. Dans la [!UICONTROL Manage] colonne, sous [!UICONTROL Legacy Dashboards], cliquez sur **[!UICONTROL Copy to New Dashboard]**.

   Le tableau de bord copié s’ouvre dans l’éditeur de présentation des tableaux de bord.

   Reportez-vous à la section [Modification des données d’un tableau de bord et d’un petit rapport](/help/analyze/reports-analytics/dashboard.md).

## Partage d’un tableau de bord

Cette section explique comment un administrateur peut partager (ou pousser) un tableau de bord vers plusieurs utilisateurs. When you push dashboards to users, the dashboards become available in user&#39;s [!UICONTROL Shared Dashboards] menu.

1. Dans la [!UICONTROL Dashboard Manager]section, recherchez le tableau de bord, puis activez **[!UICONTROL Shared]**.
1. Cliquez sur **[!UICONTROL Push To Users]**.  ![](assets/push.png)

1. Sur la [!UICONTROL Push Dashboard] page, sélectionnez les utilisateurs cible ou cliquez sur **[!UICONTROL Check All]**.
1. Cliquez sur **[!UICONTROL Save]**.

If shared users of your dashboard cannot see changes you made in the dashboard, check your Dashboard Manager to see if the users have chosen the **[!UICONTROL Copy Me]** option. Si tel est le cas, ils ne peuvent pas voir les mises à jour ou changements que vous avez apportés. To see all the changes/updates, shared users need to select the **[!UICONTROL On Menu]** option in the Dashboard Manager.

## Planification de la remise d’un tableau de bord

In the [!UICONTROL Dashboard Manager], you can see whether a dashboard is scheduled for delivery, and edit the schedule. Les options de remise du tableau de bord sont identiques aux options de remise d’un rapport.

1. Ouvrez un tableau de bord.
1. Cliquez sur **[!UICONTROL More]** > **[!UICONTROL Send]**.

   See [Schedule and Distribution](/help/analyze/reports-analytics/scheduling.md) for more information.

## Archivage d’un tableau de bord

> [!NOTE] Cette fonctionnalité ne sera plus disponible en janvier 2020.

Cette section décrit comment archiver n’importe quel tableau de bord envoyé en tant que fichier PDF. Le système conserve le fichier archivé pendant deux ans ou jusqu’à ce que vous ayez atteint la limite maximum de 4 Go de rapports archivés, le premier événement à survenir prévalant.

1. Ouvrez un tableau de bord.
1. Cliquez sur **[!UICONTROL More]** > **[!UICONTROL Send]**.
1. Dans le [!UICONTROL Email Report] groupe, activez **[!UICONTROL Archive]**.
1. Specify delivery options, then click **[!UICONTROL Send]**.

   Vous pouvez afficher les tableaux de bord archivés dans le Gestionnaire de tableaux de bord. Vous pouvez également ouvrir un tableau de bord et cliquer sur **[!UICONTROL More]** > **[!UICONTROL View Archive]**.
