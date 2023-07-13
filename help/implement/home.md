---
title: Mise en œuvre d’Adobe Analytics
description: Mettez en œuvre Adobe Analytics sur votre site, propriété ou application.
feature: Implementation Basics
exl-id: 2b629369-2d69-4dc6-861a-ff21a46d39e0
source-git-commit: bef853934683f647e05d42e1a751217c8f9b5dc4
workflow-type: tm+mt
source-wordcount: '925'
ht-degree: 85%

---

# Mise en œuvre d’Adobe Analytics

![Bannière](../../assets/doc_banner_implement.png)

Adobe requiert du code sur votre site ou application pour envoyer des données aux serveurs de collecte de données d’Adobe. Les étapes suivantes indiquent le fonctionnement d’une mise en œuvre type.

1. Quand un visiteur arrive sur votre site, une demande est envoyée à votre serveur web.
2. Le serveur web de votre site envoie les informations du code de la page, puis la page s’affiche dans le navigateur.
3. La page se charge et le code JavaScript Analytics s’exécute.
Le code JavaScript envoie une demande d’image aux serveurs de collecte de données Adobe. Les données de page que vous avez définies dans votre mise en œuvre sont envoyées dans le cadre d’une chaîne de requête dans cette demande d’image.

4. Adobe renvoie une image pixel transparente.
5. Les serveurs Adobe stockent les données collectées dans une ou plusieurs *suites de rapports*.
6. Les données de la suite de rapports renseignent les rapports auxquels vous avez accès dans un navigateur web.

L’exécution du code JavaScript survient rapidement et n’affecte pas le temps de chargement de la page de manière notable. Grâce à cette méthode, vous pouvez comptabiliser les pages affichées quand un visiteur a cliqué sur **[!UICONTROL Recharger]** ou **[!UICONTROL Précédent]** pour atteindre une page, puisque le code JavaScript s’exécute même quand la page est récupérée dans la mémoire cache.

Adobe Analytics exige du code sur votre site web, votre application mobile ou toute autre application pour envoyer des données aux serveurs de collecte de données. Il existe plusieurs méthodes de mise en œuvre de ce code, selon la plateforme et les besoins de votre entreprise.

## Méthodes de mise en œuvre d’un site Web

Pour votre **site Web**, les méthodes de mise en œuvre suivantes sont disponibles :

* **Extension SDK Web** : la méthode normalisée et recommandée pour mettre en œuvre Adobe Analytics pour les nouveaux clients et les nouvelles clientes. Installez le **Extension SDK Web Adobe Experience Platform** dans la collecte de données Adobe Experience Platform **Balises**, utilisez une balise de chargement sur chaque page et envoyez des données à Adobe Experience Platform. **Edge Network** dans un format adapté à votre entreprise. Le réseau Edge transfère les données entrantes vers Adobe Analytics dans le format approprié.
  ![Extension SDK Web](./assets/websdk-extension-implementation.png)
Voir [Comment mettre en oeuvre Adobe Analytics à l’aide de l’extension SDK Web Adobe Experience Platform.](./aep-edge/overview.md).

* **SDK Web** : si vous ne souhaitez pas utiliser la collecte de données d’Adobe Experience Platform, vous pouvez charger manuellement les bibliothèques du SDK Web sur votre site. Référencez la bibliothèque du SDK Web (`alloy.js`) sur chaque page et envoyez les appels de suivi de votre choix au **réseau Edge** d’Adobe Experience Platform dans un format adapté à votre organisation. Le réseau Edge transfère les données entrantes vers Adobe Analytics dans le format approprié.
  ![SDK Web](./assets/websdk-implementation.png)
Voir [Comment mettre en oeuvre Adobe Analytics à l’aide du SDK Web de Adobe Experience Platform](./aep-edge/overview.md) pour plus d’informations.


* **Extension Analytics** : installez l’**extension Adobe Analytics** dans les **balises** de la collecte de données d’Adobe Experience Platform. Placez une balise de chargement sur chaque page et utilisez l’extension Adobe Analytics pour déterminer comment est définie chaque variable. Utilisez cette méthode d’implémentation si vous souhaitez profiter de la commodité des balises sans utiliser l’infrastructure du réseau Edge.
  ![Extension Adobe Analytics](./assets/analytics-extension-implementation.png)
Voir [Comment mettre en oeuvre Adobe Analytics à l’aide de l’extension Analytics](launch/overview.md) pour plus d’informations.

* **Code JavaScript hérité** : méthode manuelle historique pour implémenter Adobe Analytics. Référencez la bibliothèque AppMeasurement (`AppMeasurement.js`) sur chaque page, puis définissez les paramètres et variables de contour utilisés dans une implémentation.
  ![Comment mettre en oeuvre Adobe Analytics à l’aide du code JavaScript hérité](./assets/appmeasurement-implementation.png)
Cette méthode d’implémentation peut s’avérer utile pour les implémentations utilisant du code personnalisé. Elle est toujours recommandée lorsque vous (souhaitez) utiliser :

   * [données d’Activity Map](../analyze/activity-map/activity-map.md),

     >[!INFO]
     >
     >Activity Map est pris en charge à l’aide du dernier SDK Web. Pour plus d’informations, voir la section [Activer Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md).

   * [des mesures de médias en continu](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=fr),

   * [une API LiveStream ou des déclencheurs LiveStream](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md).

   * [Suivi des pages AMP](./other/amp.md)

  Voir [Implémentation d’Adobe Analytics avec AppMeasurement pour JavaScript](js/overview.md) pour plus d’informations.

Le flux de décision suivant peut vous aider à sélectionner une méthode d’implémentation :

![Arborescence de décision permettant de sélectionner une méthode de mise en oeuvre, comme décrit dans cette section.](./assets/decision-tree.png)


>[!TIP]
>
>Veuillez contacter Adobe pour obtenir des conseils et connaître les bonnes pratiques sur l’mplémentation à choisir en fonction de votre situation actuelle.

## Méthodes d’implémentation des applications mobiles

Pour votre **application mobile**, les méthodes d’implémentation suivantes sont disponibles :

* **Extension SDK mobile** : méthode normalisée et recommandée pour implémenter Adobe Analytics dans votre application mobile. Utilisez des bibliothèques dédiées pour envoyer facilement des données à Adobe depuis votre application mobile. Installez l’**Extension SDK mobile Adobe Experience Platform** dans les **balises** de la collecte de données d’Adobe Experience Platform et implémentez le code correct dans votre application pour importer des bibliothèques, enregistrer des extensions et charger la configuration de balise. Ceci envoie des données au **réseau Edge** d’Adobe Experience Platform dans un format adapté à votre organisation. Experience Edge transfère les données entrantes vers Adobe Analytics dans le format approprié.
  ![Extension SDK mobile.](./assets/mobilesdk-extension.png)

  Voir [Implémenter Adobe Analytics à l’aide du SDK mobile Adobe Experience Platform](../implement/aep-edge/mobile-sdk/overview.md) pour plus d’informations.

* **Extension Analytics** : installez l’**extension Adobe Analytics** dans les **balises** de la collecte de données d’Adobe Experience Platform, et implémentez le code correct dans votre application pour importer des bibliothèques, enregistrer des extensions et charger la configuration de balise. Utilisez l’extension Analytics pour déterminer comment chaque variable est définie. Utilisez cette méthode d’implémentation si vous souhaitez profiter de la collecte de données d’Adobe Experience Platform sans utiliser l’infrastructure de réseau Edge Experience Platform d’Adobe.
  ![Extension Analytics](./assets/mobilesdk-analytics-extension.png)

  Voir [Implémenter Adobe Analytics à l’aide de l’extension Analytics](../implement/aep-edge/mobile-sdk/overview.md) pour plus d’informations.


>[!CAUTION]
>
>La prise en charge des SDK mobiles version 4 a pris fin le 31 août 2021. Pour plus d’informations, voir la [FAQ sur la fin de prise en charge des SDK mobiles version 4](https://developer.adobe.com/client-sdks/documentation/v4-end-of-life-faq/).

## Principaux articles sur l’implémentation d’Analytics

* [Prise en charge d’une implémentation Adobe Analytics existante](/help/implement/prepare/existing-implementation.md)
* [Adobe Debugger](validate/debugger.md)
* [Création d’une propriété de balise dans Experience Platform](launch/create-analytics-property.md)
* [Mises à jour d’AppMeasurement](appmeasurement-updates.md)

## Plus de guides d’utilisation d’Analytics

[Guides d’utilisation d’Analytics](https://experienceleague.adobe.com/docs/analytics.html?lang=fr)

## Principales ressources Analytics

* [Contacter l’assistance clientèle](https://experienceleague.adobe.com/?support-solution=Analytics&amp;lang=fr#support)
* [Forum de la communauté Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community?profile.language=fr)
* [Ressources Adobe Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/adobe-analytics-resources/m-p/276666?profile.language=fr)
