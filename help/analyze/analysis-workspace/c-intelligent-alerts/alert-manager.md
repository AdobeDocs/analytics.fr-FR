---
description: Création, modification ou suppression des alertes.
title: Gestionnaire d’alertes (Analysis Workspace)
feature: Alerts
role: User, Admin
exl-id: c33a9a30-f53f-443c-96b7-6a87d03573c7
source-git-commit: 58e1d3025b455de7fa07037b3b0659330c8324c7
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 5%

---


# Gestion des alertes

Vous pouvez gérer les alertes existantes dans le gestionnaire d’alertes. Vous pouvez effectuer diverses tâches de gestion sur les alertes, telles que le balisage, le changement de nom, la suppression, etc.

La structure du gestionnaire des alertes ressemble à celle de la fonction [Gestionnaire de segments](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=fr) et la variable [Gestionnaire de mesures calculées](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=fr).

## Créer des alertes

Pour créer des alertes à partir du gestionnaire d’alertes :

1. Sélectionner **[!UICONTROL Composants]** > **[!UICONTROL Alertes]** pour accéder au gestionnaire des alertes dans Adobe Analytics.

   ![](assets/alert-manager.png)

1. Sélectionner [!UICONTROL **Ajouter**] (ou [!UICONTROL **Créer une alerte**] si vous n’avez aucune alerte existante).

1. Sélectionnez le type d&#39;alerte correspondant à l&#39;alerte que vous souhaitez créer :

   * [!UICONTROL **Alerte de données Analytics**]: alerte pour vous avertir lorsque des événements anormaux se produisent dans vos données.

     Si vous sélectionnez cette option, passez à la [Créer des alertes](/help/analyze/analysis-workspace/c-intelligent-alerts/alert-builder.md) pour plus d’informations sur la création d’alertes.

   * [!UICONTROL **Alerte d’utilisation des appels au serveur**]: alerte pour vous avertir du risque ou de l’apparition d’un dépassement dans vos données d’engagement et de consommation d’appels au serveur.

     Si vous sélectionnez cette option, passez à la [Alertes d’utilisation des appels au serveur](/help/admin/admin/c-server-call-usage/scu-alerts.md).

     >[!NOTE]
     >
     >Pour pouvoir accéder à l’utilisation des appels au serveur, vous devez être un administrateur d’Analytics ou un utilisateur disposant de l’autorisation d’utilisation des appels au serveur.




## Gérer les alertes existantes

Pour gérer les alertes existantes dans le gestionnaire d’alertes :

1. Sélectionner **[!UICONTROL Composants]** > **[!UICONTROL Alertes]** pour accéder au gestionnaire des alertes dans Adobe Analytics.

   ![](assets/alert-manager.png)

1. Sélectionnez une ou plusieurs alertes à gérer.

   ![](assets/alert-manager-tasks.png)

1. Dans la barre d’actions, sélectionnez l’une des options suivantes :

   | Action | Fonction |
   |---------|----------|
   | [!UICONTROL **Balise**] | Appliquez une balise à une alerte. Vous pouvez ainsi organiser les alertes pour en faciliter l’utilisation. |
   | [!UICONTROL **Supprimer**] | Supprime l’alerte. |
   | [!UICONTROL **Renommer**] | Renomme l’alerte. |
   | [!UICONTROL **Approuver**] | Marquez l’alerte comme Approuvé. |
   | [!UICONTROL **Copier**] | Crée une copie (en double) de l’alerte. |
   | [!UICONTROL **Désactiver**] | Désactive une alerte actuellement activée. |
   | [!UICONTROL **Activer**] | Active une alerte actuellement désactivée. |
   | [!UICONTROL **Renouveler**] | Renouvelle la date d’expiration de l’alerte. Cela prolonge la date d’expiration d’un an à partir du jour où vous avez sélectionné cette option, quelle que soit la date d’expiration d’origine. |
   | [!UICONTROL **Exporter dans un fichier CSV**] | Exporte l’alerte dans un fichier .CSV. |
