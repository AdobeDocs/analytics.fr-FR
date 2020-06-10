---
title: Utilisation des données XDM avec Analytics
description: 'Présentation de l’utilisation des données XDM de la plateforme d’expérience dans Adobe Analytics '
translation-type: tm+mt
source-git-commit: a28a05047e95d12343fd94f7b11e5cabf7fac070
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 4%

---


# Utilisation des données Edge de la plate-forme Adobe Experience avec Analytics

Vous pouvez utiliser le SDK [Web d’](https://docs.adobe.com/content/help/fr-FR/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html) Adobe Experience Platform (AEP) pour envoyer des données à Adobe Analytics. Cela fonctionne en traduisant le modèle de données d’ [expérience (XDM)](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html) dans un format utilisé par Analytics.

Analytics collecte les données XDM de deux manières :

* Mappage automatique à partir de schémas XDM
* Mappage manuel des données contextuelles

## Mappage automatique

[Le mappage](xdm-manual.md) automatique repose sur un [schéma](https://docs.adobe.com/content/help/en/experience-platform/xdm/schema/composition.html) par défaut dans XDM qui renseigne automatiquement les objets JSON inclus dans la collecte de données Analytics standard. Les variables Analytics qui sont automatiquement mises en correspondance entre XDM et vos suites de rapports configurées ne nécessitent aucune prise en charge de développeur pour être incorporées.

## Mappage manuel

Le mappage manuel des données XDM avec Analytics repose sur les variables de données [contextuelles](../vars/page-vars/contextdata.md) Analytics. Ces variables sont placées dans des objets JSON correspondant aux schémas applicables. En règle générale, votre équipe de développement ajoute des données contextuelles lors de l’implémentation, puis les administrateurs définissent des règles [de](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md) traitement pour appliquer ces données à des suites de rapports spécifiées.

## Configuration

Pour configurer Analytics pour recevoir des données XDM :

1. Installez et [configurez](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/configuring-the-sdk.html) le SDK [Web](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/installing-the-sdk.html)Adobe Experience Platform.

2. Assurez-vous que les suites de rapports applicables sont mises en correspondance avec les données de votre choix. Les données XDM sont automatiquement transférées vers la suite de rapports à partir de la plateforme Adobe Experience.
