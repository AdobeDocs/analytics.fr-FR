---
title: Mise en œuvre d’Adobe Analytics
description: Mettez en œuvre Adobe Analytics sur votre site, propriété ou application.
feature: Implementation Basics
source-git-commit: d9a5d8a15b9e108af795cdfb7ed5481d51311328
workflow-type: tm+mt
source-wordcount: '885'
ht-degree: 40%

---

# Mise en œuvre d’Adobe Analytics

![Bannière](../../assets/doc_banner_implement.png)

Adobe requiert du code sur votre site ou application pour envoyer des données aux serveurs de collecte de données d’Adobe. Les étapes suivantes indiquent le fonctionnement d’une mise en œuvre type.

1. Quand un visiteur arrive sur votre site, une demande est envoyée à votre serveur web.
2. Le serveur web de votre site envoie les informations du code de la page, puis la page s’affiche dans le navigateur.
3. La page se charge et le code JavaScript Analytics s’exécute.
Le code JavaScript envoie une demande d’image aux serveurs de collecte de données d’Adobe. Les données de page que vous avez définies dans votre mise en œuvre sont envoyées dans le cadre d’une chaîne de requête dans cette demande d’image.

4. Adobe renvoie une image pixel transparente.
5. Les serveurs Adobe stockent les données collectées dans une ou plusieurs *suites de rapports*.
6. Les données de la suite de rapports renseignent les rapports auxquels vous avez accès dans un navigateur web.

L’exécution du code JavaScript survient rapidement et n’affecte pas le temps de chargement de la page de manière notable. Grâce à cette méthode, vous pouvez comptabiliser les pages affichées quand un visiteur a cliqué sur **[!UICONTROL Recharger]** ou **[!UICONTROL Précédent]** pour atteindre une page, puisque le code JavaScript s’exécute même quand la page est récupérée dans la mémoire cache.

Adobe Analytics exige du code sur votre site web, votre application mobile ou toute autre application pour envoyer des données aux serveurs de collecte de données. Il existe plusieurs méthodes de mise en œuvre de ce code, selon la plateforme et les besoins de votre entreprise.

## Méthodes de mise en oeuvre de site web

Pour votre **site web**, les méthodes de mise en oeuvre suivantes sont disponibles :

* **Extension SDK Web**: Méthode normalisée et recommandée pour implémenter Adobe Analytics pour les nouveaux clients. Installez le **Extension SDK Web AEP** dans la collecte de données Adobe Experience Platform **Balises**, utilisez une balise de chargement sur chaque page et envoyez des données à Adobe Experience Platform. **Edge Network** dans un format adapté à votre entreprise. Le réseau Edge transfère les données entrantes vers Adobe Analytics au format correct.
   ![Extension SDK Web](./assets/websdk-extension-implementation.png)
Voir [Mise en oeuvre d’Adobe Analytics à l’aide de l’extension du SDK Web de Adobe Experience Platform](./aep-edge/overview.md) pour plus d’informations.

* **SDK Web** : si vous ne souhaitez pas utiliser la collecte de données Adobe Experience Platform, vous pouvez charger manuellement les bibliothèques du SDK Web sur votre site. Référencez la bibliothèque SDK Web (`alloy.js`) sur chaque page et envoyer les appels de suivi de votre choix à Adobe Experience Platform. **Edge Network** dans un format adapté à votre entreprise. Le réseau Edge transfère les données entrantes vers Adobe Analytics au format correct.
   ![SDK Web](./assets/websdk-implementation.png)
Voir [Mise en oeuvre d’Adobe Analytics à l’aide du SDK Web de Adobe Experience Platform](./aep-edge/overview.md) pour plus d’informations.


* **Extension Analytics**: Installez le **Extension Adobe Analytics** dans la collecte de données Adobe Experience Platform **Balises**. Placez une balise de chargement sur chaque page et utilisez l’extension Adobe Analytics pour déterminer comment chaque variable est définie. Utilisez cette méthode d’implémentation si vous souhaitez profiter de la commodité des balises, mais ne souhaitez pas utiliser l’infrastructure réseau Edge.
   ![Extension Adobe Analytics](./assets/analytics-extension-implementation.png)
Voir [Mise en oeuvre d’Adobe Analytics à l’aide de l’extension Analytics](launch/overview.md) pour plus d’informations.

* **Code JavaScript hérité** : méthode manuelle historique pour mettre en œuvre Adobe Analytics. Référencez la bibliothèque AppMeasurement (`AppMeasurement.js`) sur chaque page, puis définissez les variables et les paramètres utilisés dans une implémentation.
   ![Code JavaScript hérité](./assets/appmeasurement-implementation.png)
Cette méthode d’implémentation peut s’avérer utile pour les implémentations utilisant du code personnalisé. Elle est toujours recommandée lorsque vous (souhaitez) utiliser :

   * [données d’Activity Map de niveau clic](../analyze/activity-map/activity-map.md),

   * [mesure des médias en continu](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=fr),

   * [API livestream ou déclencheurs livestream](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md),

   * [Suivi des pages AMP](./other/amp.md)
   Voir [Mise en oeuvre d’Adobe Analytics avec AppMeasurement pour JavaScript](js/overview.md) pour plus d’informations.

Le flux de décision suivant peut vous aider à sélectionner une méthode de mise en oeuvre :

![Arborescence de décision](./assets/decision-tree.png)


>[!TIP]
>
>Veuillez contacter Adobe pour obtenir des conseils et connaître les bonnes pratiques sur la mise en oeuvre à choisir en fonction de votre situation actuelle.

## Méthodes de mise en oeuvre des applications mobiles

Pour votre **application mobile**, les méthodes de mise en oeuvre suivantes sont disponibles :

* **Extension SDK Mobile**: Méthode normalisée et recommandée pour implémenter Adobe Analytics dans votre application mobile. Utilisez des bibliothèques dédiées pour envoyer facilement des données à Adobe depuis votre application mobile. Installez le **Extension SDK Mobile Adobe Experience Platform** dans la collecte de données Adobe Experience Platform **Balises** et implémentez le code correct dans votre application pour importer des bibliothèques, enregistrer des extensions et charger la configuration de balise. Envoi de données à Adobe Experience Platform **Edge Network** dans un format adapté à votre entreprise. Experience Edge transfère les données entrantes vers Adobe Analytics dans le format approprié.
   ![Extension SDK Mobile](./assets/mobilesdk-extension.png)

   Voir [Mise en oeuvre d’Adobe Analytics à l’aide du SDK Adobe Experience Platform Mobile](../implement/aep-edge/mobile-sdk/overview.md) pour plus d’informations.

* **Extension Analytics**: Installez le **Extension Adobe Analytics** dans la collecte de données Adobe Experience Platform **Balises**et implémentez le code correct dans votre application pour importer des bibliothèques, enregistrer des extensions et charger la configuration de balise. Utilisez l’extension Analytics pour déterminer comment chaque variable est définie. Utilisez cette méthode d’implémentation si vous souhaitez profiter de la collecte de données Adobe Experience Platform, mais ne souhaitez pas utiliser l’infrastructure réseau Edge Experience Platform d’Adobe.
   ![Extension Analytics](./assets/mobilesdk-analytics-extension.png)

   Voir [Mise en oeuvre d’Adobe Analytics à l’aide de l’extension Analytics](../implement/aep-edge/mobile-sdk/overview.md) pour plus d’informations.


>[!CAUTION]
>
>La prise en charge des SDK mobiles version 4 a pris fin le 31 août 2021. Pour plus d’informations, voir la [FAQ sur les kits SDK mobiles version 4 (fin de prise en charge)](https://developer.adobe.com/client-sdks/documentation/v4-end-of-life-faq/).

## Principaux articles sur l’importation Analytics

* [Prise en charge d’une implémentation Adobe Analytics existante](/help/implement/prepare/existing-implementation.md)
* [Adobe Debugger](validate/debugger.md)
* [Création d’une propriété de balise dans Experience Platform](launch/create-analytics-property.md)
* [Mises à jour d’AppMeasurement](appmeasurement-updates.md)

## Plus de guides d’utilisation d’Analytics

[Guides d’utilisation d’Analytics](https://experienceleague.adobe.com/docs/analytics.html?lang=fr)

## Principales ressources Analytics

* [Contacter l’assistance clientèle](https://experienceleague.adobe.com/?support-solution=Analytics&amp;lang=fr#support)
* [Forum de la communauté Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community?profile.language=fr)
* [Ressources Adobe Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/adobe-analytics-resources/m-p/276666)
