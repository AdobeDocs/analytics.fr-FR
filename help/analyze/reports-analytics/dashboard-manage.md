---
description: Utilisez le Gestionnaire de tableaux de bord pour copier, partager, archiver et programmer la remise des tableaux de bord.
subtopic: Dashboards
title: Gestionnaire de tableaux de bord
topic: Reports and analytics
uuid: 380fd148-2ed9-43bf-9d42-46e373e788e4
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 100%

---


# Gestionnaire de tableaux de bord

Utilisez le Gestionnaire de tableaux de bord pour copier, partager, archiver et programmer la remise des tableaux de bord.

>[!IMPORTANT]
>
>Lorsque vous utilisez le gestionnaire de tableaux de bord, l’une des bonnes pratiques consiste à ne pas avoir plus de 300 tableaux de bord pour un utilisateur unique. Notez également que le gestionnaire charge tous les tableaux de bord partagés ci-dessous, soyez donc judicieux lorsque vous partagez les tableaux de bord.

## Gestionnaire de tableaux de bord

Utilisez le Gestionnaire de tableaux de bord pour copier, partager, archiver et programmer la remise des tableaux de bord.

Cliquez sur **[!UICONTROL Analytics]** > **[!UICONTROL Composants]** > **[!UICONTROL Tableaux de bord]**.

| Élément | Description |
|--- |--- |
| Partagé | Indique si le tableau de bord est partagé. |
| Planifié | Permet de programmer la remise du tableau de bord. |
| Afficher l’archive | Cette fonctionnalité n’est plus disponible. |
| Envoyer aux utilisateurs | Permet de partager un tableau de bord. |
| Gérer | Permet de modifier, de copier et de supprimer un tableau de bord. |

## Gestion des tableaux de bord partagés

Étapes décrivant comment utiliser les options de gestion du tableau de bord partagé.

1. Sélectionnez **[!UICONTROL Analytics]** > **[!UICONTROL Composants]** > **[!UICONTROL Tableaux de bord]**.
1. Sous [!UICONTROL Tableaux de bord partagés], localisez le tableau de bord partagé (ou le tableau de bord hérité) que vous souhaitez gérer et sélectionnez une ou plusieurs des options suivantes :

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
  <td class="chdesc stentry"> Ajoute une copie à la liste des tableaux de bord, en utilisant le même nom que pour l’original. Néanmoins, vous ne pouvez pas afficher les mises à jour/modifications effectuées par le propriétaire du tableau de bord. La copie d’un tableau de bord hérité ouvre un tableau de bord vierge, dans lequel vous pouvez ajouter du contenu hérité. <p>Important : si les utilisateurs partagés de votre tableau de bord ne voient pas les modifications que vous avez apportées au tableau de bord, consultez votre Gestionnaire de tableaux de bord pour savoir si les utilisateurs ont activé l’option <span class="uicontrol">Mettez-moi en copie</span>. Si tel est le cas, ils ne peuvent pas voir les mises à jour ou changements que vous avez apportés. Pour afficher tous les changements ou modifications, les utilisateurs partagés doivent cocher l’option <span class="uicontrol">Au menu</span> dans le Gestionnaire de tableaux de bord. </p> </td> 
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

>[!NOTE]
>
>Désormais, nous vous invitons à utiliser les [projets d’Analysis Workspace](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/home.html) et leurs fonctionnalités de téléchargement et de planification.

Lorsque vous copiez le tableau de bord hérité, le système l’ouvre pour modification et vous pouvez y ajouter du contenu hérité ou du nouveau contenu. Lorsque vous copiez un tableau de bord hérité, l’original est préservé dans la liste des tableaux de bord hérités.

>[!NOTE]
>
>L’ajout à un tableau de bord d’un contenu hérité crée un tableau de bord reposant sur la dernière fonctionnalité du tableau de bord. Le mini-rapport hérité peut toutefois contenir des données reposant sur la plateforme de données précédentes.

**Pour migrer un tableau de bord hérité version 14.x**

1. Cliquez sur **[!UICONTROL Analytics]** > **[!UICONTROL Composants]** > **[!UICONTROL Gérer les tableaux de bord]**.
1. Dans la colonne [!UICONTROL Gérer], sous [!UICONTROL Tableaux de bord hérités], cliquez sur **[!UICONTROL Copier vers le nouveau tableau de bord]**.

   Le tableau de bord copié s’ouvre dans l’éditeur de présentation des tableaux de bord.

   Reportez-vous à la section [Modification des données d’un tableau de bord et d’un petit rapport](/help/analyze/reports-analytics/dashboard.md).

## Partage d’un tableau de bord

Cette section explique comment un administrateur peut partager (ou pousser) un tableau de bord vers plusieurs utilisateurs. Dans ce cas, les tableaux de bord deviennent disponibles dans le menu [!UICONTROL Tableaux de bord partagés] des utilisateurs concernés.

1. Dans le [!UICONTROL Gestionnaire de tableaux de bord], recherchez le tableau de bord et activez l’option **[!UICONTROL Partagé]**.
1. Cliquez sur **[!UICONTROL Envoyer aux utilisateurs]**.  ![](assets/push.png)

1. Sur la page [!UICONTROL Envoyer le tableau de bord], sélectionnez les utilisateurs cibles ou cliquez sur **[!UICONTROL Cocher tout]**.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

Si les utilisateurs partagés de votre tableau de bord ne voient pas les modifications que vous avez apportées au tableau de bord, consultez le Gestionnaire de tableaux de bord pour savoir si les utilisateurs ont activé l’option **[!UICONTROL Mettez-moi en copie]**. Si tel est le cas, ils ne peuvent pas voir les mises à jour ou changements que vous avez apportés. Pour afficher tous les changements ou modifications, les utilisateurs partagés doivent cocher l’option **[!UICONTROL Au menu]** dans le Gestionnaire de tableaux de bord.

## Planification de la remise d’un tableau de bord

Le [!UICONTROL Gestionnaire de tableaux de bord] permet de vérifier si la remise d’un tableau de bord est programmée et de modifier cette programmation. Les options de remise du tableau de bord sont identiques aux options de remise d’un rapport.

1. Ouvrez un tableau de bord.
1. Cliquez sur **[!UICONTROL Plus]** > **[!UICONTROL Envoyer]**.

   Pour en savoir plus, reportez-vous à la section [Planification et distribution](/help/analyze/reports-analytics/scheduling.md)

## Archivage d’un tableau de bord

>[!NOTE]
>
>Cette fonctionnalité ne sera plus disponible en janvier 2020.

Cette section décrit comment archiver n’importe quel tableau de bord envoyé en tant que fichier PDF. Le système conserve le fichier archivé pendant deux ans ou jusqu’à ce que vous ayez atteint la limite maximum de 4 Go de rapports archivés, le premier événement à survenir prévalant.

1. Ouvrez un tableau de bord.
1. Cliquez sur **[!UICONTROL Plus]** > **[!UICONTROL Envoyer]**.
1. Dans le groupe [!UICONTROL Envoyer le rapport par courriel], activez **[!UICONTROL Archivage]**.
1. Définissez les options de remise, puis cliquez sur **[!UICONTROL Envoyer]**.

   Vous pouvez afficher les tableaux de bord archivés dans le Gestionnaire de tableaux de bord. Vous pouvez également ouvrir un tableau de bord, puis cliquer sur **[!UICONTROL Plus]** > **[!UICONTROL Afficher l’archive]**.
