---
title: Utilisation des données XDM avec Analytics
description: Présentation de l’utilisation des données XDM d’Experience Platform dans Adobe Analytics
feature: AEP Edge
exl-id: 6f1282fb-8d4a-4d88-9be0-1c939c22cb92
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 100%

---

# Utilisation des données Adobe Experience Platform Edge avec Analytics

Vous pouvez utiliser le [SDK Web Adobe Experience Platform (AEP)](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html?lang=fr) pour envoyer des données à Adobe Analytics. Cela fonctionne en traduisant le [modèle de données d’expérience (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=fr) dans un format utilisé par Analytics.

Analytics collecte les données XDM de deux manières :

* Mise en correspondance automatique à partir de schémas XDM
* Mise en correspondance manuelle des données contextuelles

## Mise en correspondance automatique

La mise en correspondance automatique repose sur un [schéma](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=fr) par défaut dans XDM qui renseigne automatiquement les objets JSON inclus dans la collecte de données Analytics standard. Les variables Analytics automatiquement mises en correspondance depuis XDM vers vos suites de rapports configurées ne nécessitent aucun support développeur pour être incorporées. Voir [Variables automatiquement mappées dans Analytics](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/adobe-analytics/automatically-mapped-vars.html?lang=fr) dans le guide de lʼutilisateur du SDK Web Platform.

## Mise en correspondance manuelle

[La mise en correspondance manuelle des données XDM avec Analytics](xdm-manual.md) repose sur les [variables de données contextuelles Analytics](../vars/page-vars/contextdata.md). Ces variables sont placées dans des objets JSON correspondant aux schémas applicables. En règle générale, votre équipe de développement ajoute des données contextuelles lors de l’implémentation, puis les administrateurs définissent des [règles de traitement](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md) pour appliquer ces données à des suites de rapports spécifiées.

## Configuration

Pour configurer Analytics pour recevoir des données XDM :

1. Installez et [configurez](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=fr) le [SDK Web d’Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=fr).

2. Assurez-vous que les suites de rapports applicables sont mises en correspondance avec les données de votre choix. Les données XDM sont automatiquement transférées à la suite de rapports depuis la plateforme Adobe Experience.
