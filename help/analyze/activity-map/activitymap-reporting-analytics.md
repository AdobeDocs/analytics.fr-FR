---
description: Décrit la façon de définir les autorisations ainsi que les dimensions disponibles dans Analytics.
seo-description: Décrit la façon de définir les autorisations ainsi que les dimensions disponibles dans Analytics.
seo-title: Création de rapports [!Carte d’activités DNL] dans Analytics
solution: Analytics
title: Création de rapports [!Carte d’activités DNL] dans Analytics
topic: Activity Map
uuid: 057c6ab2-aa06-4779-ac16-f9b367d9ea43
translation-type: tm+mt
source-git-commit: 36637b76b8026fbf87ad48adcfa47386c530e732

---


# [!DNL Activity Map] création de rapports dans Analytics

Décrit la façon de définir les autorisations ainsi que les dimensions disponibles dans Analytics.

## Set permissions {#section_BDCD9914B31A4066A50D23DDDF1ABB37}

Before users can report on [!DNL Activity Map] dimensions, you as the Admin need to

* [Ajoutez des utilisateurs au groupe](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)d’accès [!DNL Activity Map].
* Ajouter à ce groupe les suites de rapports auxquelles vous souhaitez accéder. Navigate to **[!UICONTROL Admin]** &gt; **[!UICONTROL User Management]** &gt; **[!UICONTROL Groups]** &gt; **[!UICONTROL [!DNL Activity Map]Access]** &gt; **[!UICONTROL Edit]**.
* Personnaliser l’accès des utilisateurs aux dimensions. Voir la section suivante.

## Dimensions Analytics [!DNL Activity Map]{#section_9395A7A5585F4ABE9F7C6CD0124B02A5}

Vous pouvez [personnaliser l’accès des utilisateurs aux dimensions](https://marketing.adobe.com/resources/help/en_US/reference/groups-dimensions.html) à un niveau granulaire. Here are the [!DNL Activity Map] dimensions available in Analytics:

| Dimension | Description |
|---|---|
| [!DNL Activity Map] Activity Map | Répertorie les pages sur lesquelles un utilisateur a cliqué sur un lien. |
| [!DNL Activity Map] Région | Répertorie toutes les régions de lien collectées sur l’ensemble du site web. Notez que si une région apparaît sur plusieurs pages, la mesure sera intégrée à chacune d’entre elles. |
| [!DNL Activity Map] Liens | Répertorie tous les liens collectés sur l’ensemble du site web. |
| [!DNL Activity Map] Liens et région | Répertorie tous les liens collectés avec leur région sur l’ensemble du site web. |
| [!DNL Activity Map] XY | Non utilisée |

* Ces dimensions doivent être disponibles dans Analysis Workspace, Reports &amp; Analytics et Report Builder, à condition que la mise en œuvre d’Analytics soit [enabled for [!DNL Activity Map]](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md).
* In Reports &amp; Analytics, navigate to **[!UICONTROL View All Reports]** &gt; **[!UICONTROL [!DNL Activity Map]]**.

* To look at a link and region for a specific page, all you need to do is create a breakdown from the desired [!DNL Activity Map] page into the [!DNL Activity Map] Links &amp; Region.

