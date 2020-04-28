---
title: Utilisation des données XDM avec Analytics
description: 'Présentation de l’utilisation des données XDM de la plateforme d’expérience dans Adobe Analytics '
translation-type: tm+mt
source-git-commit: 31efa43043120b68de90e817a7980addbe2ded39

---




# Utilisation des données Edge d’Adobe Experience Platform avec Analytics

>[!IMPORTANT]
>
>Le kit SDK Web Adobe Experience Edge n’est pas publié et n’est disponible que pour les tests bêta parmi les clients invités. Ce document est conçu uniquement à destination des utilisateurs bêta et n’est pas représentatif des fonctionnalités complètes du produit. Si vous souhaitez devenir un utilisateur bêta de ce produit, veuillez contacter l’[assistance clientèle](https://helpx.adobe.com/fr/contact/enterprise-support.ec.html) d’Adobe.


Vous pouvez utiliser le SDK [Web d’](https://docs.adobe.com/content/help/fr-FR/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html) Adobe Experience Platform (AEP) pour envoyer des données à Adobe Analytics. Cela fonctionne en traduisant le modèle de données d’ [expérience (XDM)](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html) dans un format utilisé par Analytics.

Analytics collecte les données XDM par le biais de deux méthodes :

* Mappage automatique à partir du  XDM

* Mappage manuel des données contextuelles

## Mappage automatique

Le mappage automatique repose sur un [](https://docs.adobe.com/content/help/en/experience-platform/xdm/schema/composition.html) par défaut dans XDM qui renseigne automatiquement les objets JSON inclus dans la collecte de données Analytics standard. Les variables [Analytics qui sont automatiquement mises en correspondance du fichier XDM](https://git.corp.adobe.com/analytics-data-collection/anedge/blob/master/XDM_Translator.md) avec vos suites de rapports configurées ne nécessitent aucune prise en charge par les développeurs pour être intégrées.

## Mappage manuel

Le mappage manuel des données XDM avec Analytics repose sur les variables de données [contextuelles](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/contextdata.html) Analytics. Ces variables sont placées dans des objets JSON correspondant aux  de applicables. En règle générale, votre équipe de développement ajoute des données contextuelles lors de l’implémentation, puis les administrateurs définissent des règles [de](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/t-processing-rules.html) traitement pour appliquer ces données aux suites de rapports spécifiées.


## Configuration

Pour configurer Analytics pour recevoir des données XDM :

1. Installez et [configurez](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/configuring-the-sdk.html) le SDK [Web d’](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/installing-the-sdk.html)Adobe Experience Platform.

2. Assurez-vous que les suites de rapports applicables sont mises en correspondance avec les données de votre choix. Les données XDM sont automatiquement transférées vers la suite de rapports à partir de la plateforme Adobe Experience.

