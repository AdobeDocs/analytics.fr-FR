---
title: Mise en œuvre d’Adobe Analytics
description: Mettez en œuvre Adobe Analytics sur votre site, propriété ou application.
feature: Implementation Basics
exl-id: 2b629369-2d69-4dc6-861a-ff21a46d39e0
role: Admin, Developer, Leader, User
TQID: https://experienceleague.adobe.com/c1TZC9k-mu1n95Oq3jhQOvcBXFwx8oK28plhoNcJDK4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: c77ba355-6681-41fe-b719-563d3f507fdb
  - id: c8add8f2-4250-4fd9-9cde-9707036c567d
  - id: df312454-73c4-43f6-a90e-18f5043f074c
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 29d1585ad3d00922a7e39bf1b4da64089d9168c7
workflow-type: tm+mt
source-wordcount: 814
ht-degree: 83%

---

# Mise en œuvre d’Adobe Analytics

![Bannière](../../assets/doc_banner_implement.png)

Adobe Analytics exige du code sur votre site web, votre application mobile ou toute autre application pour envoyer des données aux serveurs de collecte de données. Il existe plusieurs méthodes de mise en œuvre de ce code, selon la plateforme et les besoins de votre entreprise.

## Méthodes de mise en œuvre d’un site Web

Pour votre **site Web**, les méthodes de mise en œuvre suivantes sont disponibles :

### Côté client

* **Extension SDK Web** : la méthode normalisée et recommandée pour mettre en œuvre Adobe Analytics pour les nouveaux clients et les nouvelles clientes. Ajoutez l’**extension SDK Web d’Adobe Experience Platform** dans les **balises** de collecte de données Adobe Experience Platform, puis placez une balise de chargement sur chaque page. La balise envoie des données au **réseau Edge** d’Adobe Experience Platform, qui transfère ces données vers Adobe Analytics.
  Extension ![Web SDK](./assets/websdk-extension-implementation.png)
Voir [Comment mettre en œuvre Adobe Analytics à l’aide de l’extension Adobe Experience Platform Web SDK &#x200B;](./aep-edge/overview.md). pour des informations supplémentaires.

* **SDK Web** : si vous ne souhaitez pas utiliser la collecte de données d’Adobe Experience Platform, vous pouvez charger manuellement les bibliothèques du SDK Web sur votre site. Référencez la bibliothèque du SDK Web (`alloy.js`) sur chaque page et envoyez les appels de suivi de votre choix au **réseau Edge** d’Adobe Experience Platform dans un format adapté à votre organisation. Le réseau Edge transfère ces données à Adobe Analytics.
  ![Web SDK](./assets/websdk-implementation.png)
Pour plus d’informations, consultez [Comment mettre en œuvre Adobe Analytics à l’aide de Adobe Experience Platform Web SDK &#x200B;](./aep-edge/overview.md).

* **Extension Analytics** : ajoutez l’**extension Adobe Analytics** dans les **balises** de collecte de données Adobe Experience Platform, puis placez une balise de chargement sur chaque page. La balise envoie des données directement à Adobe Analytics. Utilisez cette méthode d’implémentation si vous souhaitez profiter de la commodité des balises sans utiliser l’infrastructure du réseau Edge.
  Extension ![Adobe Analytics](./assets/analytics-extension-implementation.png)
Pour plus d’informations, consultez [Comment mettre en œuvre Adobe Analytics à l’aide de l’extension Analytics &#x200B;](launch/overview.md).

* **Code JavaScript hérité** : méthode manuelle historique pour implémenter Adobe Analytics. Référencez la bibliothèque AppMeasurement (`AppMeasurement.js`) sur chaque page, puis définissez les paramètres et variables dans JavaScript.
  ![Comment mettre en œuvre Adobe Analytics à l’aide de l’ancien JavaScript](./assets/appmeasurement-implementation.png)
Cette méthode d’implémentation peut s’avérer utile pour les implémentations utilisant du code personnalisé. Elle est idéale pour les types d’implémentation non proposés ailleurs, par exemple pour les pages [AMP](other/amp.md).

Le flux de décision suivant peut vous aider à sélectionner une méthode d’implémentation côté client :

![Arborescence de décision permettant de sélectionner une méthode d’implémentation, comme décrit dans cette section.](./assets/decision-tree.png)


>[!TIP]
>
>Contactez l’équipe Adobe en charge des comptes pour obtenir des conseils et connaître les bonnes pratiques relatives à l’implémentation à choisir en fonction de votre situation actuelle.

### Côté serveur

Pour implémenter Adobe Analytics côté serveur, vous disposez des options suivantes :

* **API Edge Network** : vous implémentez du code sur le serveur qui utilise l’API Edge Network d’Adobe Experience Platform pour communiquer avec Adobe Analytics par le biais d’un train de données.
  ![Implémentation côté serveur](assets/edge-network-server-api.png)
Pour plus d’informations, voir [Implémentation d’Adobe Analytics à l’aide de l’API Adobe Experience Platform Edge Network](/help/implement/aep-edge/api/overview.md).

* **API d’insertion de données (en bloc)** : vous utilisez les API d’insertion de données (en bloc) Adobe Analytics pour collecter les données côté serveur directement dans Adobe Analytics.
  ![API d’insertion de données](assets/analytics-apis.png)
Voir [API d’insertion de données](../import/c-data-insertion-api/c-data-insertion-api.md) pour plus d’informations.

## Méthodes d’implémentation des applications mobiles

Pour votre **application mobile**, les méthodes d’implémentation suivantes sont disponibles :

* **Extension SDK mobile** : méthode normalisée et recommandée pour implémenter Adobe Analytics dans votre application mobile. Utilisez des bibliothèques dédiées pour envoyer facilement des données à Adobe depuis votre application mobile. Ajoutez l’**extension SDK Mobile d’Adobe Experience Platform** dans les **balises** de collecte de données Adobe Experience Platform, puis implémentez la bibliothèque SDK Mobile dans votre application. Vous pouvez utiliser le SDK pour importer des bibliothèques, enregistrer des extensions et charger la configuration des balises. Envoyez les données au **réseau Edge** d’Adobe Experience Platform ; Edge transfère ensuite ces données à Adobe Analytics.
  ![Extension SDK mobile.](./assets/mobilesdk-extension.png)

  Voir [Implémenter Adobe Analytics à l’aide du SDK mobile Adobe Experience Platform](../implement/aep-edge/mobile-sdk/overview.md) pour plus d’informations.

* **Extension Analytics** : ajoutez l’**extension Adobe Analytics** aux **balises** de collecte de données Adobe Experience Platform et implémentez la bibliothèque SDK Mobile dans votre application. Vous pouvez utiliser le SDK pour importer des bibliothèques, enregistrer des extensions et charger la configuration des balises. Cette méthode d’implémentation envoie directement des données à Adobe Analytics. Elle est recommandée si vous souhaitez profiter de la collecte de données d’Adobe Experience Platform sans utiliser l’infrastructure de réseau Edge Experience Platform d’Adobe.
  ![Extension Analytics](./assets/mobilesdk-analytics-extension.png)

  Voir [Implémenter Adobe Analytics à l’aide de l’extension Analytics](../implement/aep-edge/mobile-sdk/overview.md) pour plus d’informations.


>[!CAUTION]
>
>Pour la prise en charge des anciennes versions des SDK mobiles d’Adobe, voir [Annonces de fin de prise en charge des SDK](https://developer.adobe.com/client-sdks/resources/sdks-end-of-support/).

## Principaux articles sur l’implémentation d’Analytics

* [Prise en charge d’une implémentation Adobe Analytics existante](/help/implement/prepare/existing-implementation.md)
* [Adobe Debugger](validate/debugger.md)
* [Création d’une propriété de balise dans Experience Platform](launch/create-analytics-property.md)
* [Mises à jour d’AppMeasurement](appmeasurement-updates.md)
* [Tutoriel sur la configuration d’Adobe Analytics avec Platform Web SDK](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/applications-setup/setup-analytics.html?lang=fr)
* [Tutoriel sur l’implémentation d’Adobe CX Enterprise dans les applications mobiles](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/overview.html?lang=fr)


## Principales ressources Analytics

* [Contactez l&#39;Assistance clientèle](https://experienceleague.adobe.com/fr?support-solution=Analytics?lang=fr#support)
* [Communauté Adobe Analytics sur Experience League](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community?profile.language=fr)
* [Ressources Adobe Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/adobe-analytics-resources/m-p/276666?profile.language=fr)
* [Dernières notes de mise à jour](../release-notes/latest.md)
