---
title: Utilisation des données XDM avec Analytics
description: 'Présentation de l’utilisation des données XDM d’Experience Platform dans Adobe Analytics '
translation-type: tm+mt
source-git-commit: 01e9a456dece2a7c3f96bb2c6c9625f654a05059
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 96%

---


# Utilisation des données Adobe Experience Platform Edge avec Analytics

Vous pouvez utiliser le [SDK Web Adobe Experience Platform (AEP)](https://docs.adobe.com/content/help/fr-FR/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html) pour envoyer des données à Adobe Analytics. Cela fonctionne en traduisant le [modèle de données d’expérience (XDM)](https://docs.adobe.com/content/help/fr-FR/experience-platform/xdm/home.html) dans un format utilisé par Analytics.

Analytics collecte les données XDM de deux manières :

* Mise en correspondance automatique à partir de schémas XDM
* Mise en correspondance manuelle des données contextuelles

## Mise en correspondance automatique

La mise en correspondance automatique repose sur un [schéma](https://docs.adobe.com/content/help/fr-FR/experience-platform/xdm/schema/composition.html) par défaut dans XDM qui renseigne automatiquement les objets JSON inclus dans la collecte de données Analytics standard. Les variables Analytics automatiquement mises en correspondance depuis XDM vers vos suites de rapports configurées ne nécessitent aucun support développeur pour être incorporées.

## Mise en correspondance manuelle

[](xdm-manual.md)La mise en correspondance manuelle des données XDM avec Analytics repose sur les [variables de données contextuelles Analytics](../vars/page-vars/contextdata.md). Ces variables sont placées dans des objets JSON correspondant aux schémas applicables. En règle générale, votre équipe de développement ajoute des données contextuelles lors de l’implémentation, puis les administrateurs définissent des [règles de traitement](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md) pour appliquer ces données à des suites de rapports spécifiées.

## Configuration

Pour configurer Analytics pour recevoir des données XDM :

1. Installez et [configurez](https://docs.adobe.com/content/help/fr-FR/experience-platform/edge/fundamentals/configuring-the-sdk.html) le [SDK Web d’Adobe Experience Platform](https://docs.adobe.com/content/help/fr-FR/experience-platform/edge/fundamentals/installing-the-sdk.html).

2. Assurez-vous que les suites de rapports applicables sont mises en correspondance avec les données de votre choix. Les données XDM sont automatiquement transférées à la suite de rapports depuis la plateforme Adobe Experience.
