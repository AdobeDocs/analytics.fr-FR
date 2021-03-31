---
description: Décrit la façon de définir les autorisations ainsi que les dimensions disponibles dans Analytics.
title: Création de rapports Activity Map dans Analytics
uuid: 057c6ab2-aa06-4779-ac16-f9b367d9ea43
feature: Activity Map
role: Professionnel, Administrateur
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 98%

---


# Création de rapports Activity Map dans Analytics

Décrit la façon de définir les autorisations ainsi que les dimensions disponibles dans Analytics.

## Définition des autorisations {#section_BDCD9914B31A4066A50D23DDDF1ABB37}

Pour que les utilisateurs puissent créer des rapports sur les dimensions Activity Map, vous devez, en tant qu’administrateur :

* [Ajouter des utilisateurs au groupe d’accès d’Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md).
* Ajouter à ce groupe les suites de rapports auxquelles vous souhaitez accéder. Sélectionnez **[!UICONTROL Admin]** > **[!UICONTROL Gestion utilisateur]** > **[!UICONTROL Groupes]** > **[!UICONTROL Accès à Activity Map]** > **[!UICONTROL Modifier]**.
* Personnaliser l’accès des utilisateurs aux dimensions. Voir la section suivante.

## Dimensions Activity Map dans Analytics {#section_9395A7A5585F4ABE9F7C6CD0124B02A5}

Vous pouvez [personnaliser l’accès des utilisateurs aux dimensions](https://docs.adobe.com/content/help/fr-FR/analytics/admin/user-product-management/customize-report-access/groups-dimensions.html) à un niveau granulaire. Les dimensions Activity Map suivantes sont disponibles dans Analytics :

| Dimension | Description |
|---|---|
| Activity Map Page | Répertorie les pages sur lesquelles un utilisateur a cliqué sur un lien. |
| Région d’Activity Map | Répertorie toutes les régions de lien collectées sur l’ensemble du site web. Notez que si une région apparaît sur plusieurs pages, la mesure sera intégrée à chacune d’entre elles. |
| Liens d’Activity Map | Répertorie tous les liens collectés sur l’ensemble du site web. |
| Liens et région d’Activity Map | Répertorie tous les liens collectés avec leur région sur l’ensemble du site web. |
| Coordonnées d’Activity Map | Non utilisée |

* Ces dimensions doivent être disponibles dans Analysis Workspace, Reports &amp; Analytics et Report Builder, à condition que la mise en œuvre d’Analytics soit [activée pour Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md).
* Dans Reports &amp; Analytics, sélectionnez **[!UICONTROL Afficher tous les rapports]** > **[!UICONTROL Activity Map]**.

* Pour consulter un lien ou une région d’une page spécifique, il suffit de créer une ventilation à partir de la page Activity Map souhaitée dans Liens et région d’Activity Map.

