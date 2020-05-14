---
title: Utilisation des données XDM avec Analytics
description: 'Présentation de l’utilisation des données XDM de la plate-forme d’expérience dans Adobe Analytics '
translation-type: tm+mt
source-git-commit: 717c3e23eb2c3fb2477bd77ea92a1dce744f02df
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 4%

---


# Utilisation des données Edge de la plate-forme Adobe Experience avec Analytics


Vous pouvez utiliser le SDK [Web d’](https://docs.adobe.com/content/help/fr-FR/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html) Adobe Experience Platform (AEP) pour envoyer des données à Adobe Analytics. Cela fonctionne en traduisant le modèle de données d’ [expérience (XDM)](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html) dans un format utilisé par Analytics.

Analytics collecte les données XDM de deux manières :

* Mappage automatique à partir de schémas XDM

* Mappage manuel des données contextuelles

## Mappage automatique

Le mappage automatique repose sur un [schéma](https://docs.adobe.com/content/help/en/experience-platform/xdm/schema/composition.html) par défaut dans XDM qui renseigne automatiquement les objets JSON inclus dans la collecte de données Analytics standard. Les variables [Analytics automatiquement mises en correspondance depuis XDM](https://git.corp.adobe.com/analytics-data-collection/anedge/blob/master/XDM_Translator.md) avec les suites de rapports configurées ne nécessitent aucune prise en charge de développeur pour être incorporées.

## Mappage manuel

Le mappage manuel des données XDM avec Analytics repose sur les variables de données [contextuelles](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/contextdata.html) Analytics. Ces variables sont placées dans des objets JSON correspondant aux schémas applicables. En règle générale, votre équipe de développement ajoute des données contextuelles lors de l’implémentation, puis les administrateurs définissent des règles [de](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/t-processing-rules.html) traitement pour appliquer ces données à des suites de rapports spécifiées.


## Configuration

Pour configurer Analytics pour recevoir des données XDM :

1. Installez et [configurez](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/configuring-the-sdk.html) le SDK [Web](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/installing-the-sdk.html)Adobe Experience Platform.

2. Assurez-vous que les suites de rapports applicables sont mises en correspondance avec les données de votre choix. Les données XDM sont automatiquement transférées à la suite de rapports depuis la plateforme Adobe Experience.

