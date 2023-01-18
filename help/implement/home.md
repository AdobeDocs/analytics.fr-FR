---
title: Mise en œuvre d’Adobe Analytics
description: Mettez en œuvre Adobe Analytics sur votre site, propriété ou application.
feature: Implementation Basics
exl-id: 2b629369-2d69-4dc6-861a-ff21a46d39e0
source-git-commit: d2c291f7db465034ffadc4a2c1caf9639caf2a1d
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 79%

---

# Mise en œuvre d’Adobe Analytics

![Bannière](../../assets/doc_banner_implement.png)

Voici un aperçu vidéo dʼAdobe Analytics :

>[!VIDEO](https://video.tv.adobe.com/v/27429/?quality=12)

Adobe requiert du code sur votre site ou application pour envoyer des données aux serveurs de collecte de données d’Adobe. Les étapes suivantes indiquent le fonctionnement d’une mise en œuvre type.

1. Quand un visiteur arrive sur votre site, une demande est envoyée à votre serveur web.
2. Le serveur web de votre site envoie les informations du code de la page, puis la page s’affiche dans le navigateur.
3. La page se charge et le code JavaScript Analytics s’exécute.
4. Le code JavaScript envoie une demande d’image de 1x1 pixel aux serveurs de collecte de données d’Adobe. Les données de page que vous avez définies dans votre mise en œuvre sont envoyées dans le cadre d’une chaîne de requête dans cette demande d’image.
5. Les serveurs de collecte de données d’Adobe renvoient l’image demandée.
6. Les serveurs Adobe analysent et stockent les données collectées dans une suite de rapports.
7. Les données de la suite de rapports renseignent les rapports auxquels vous avez accès dans un navigateur web.


Adobe propose plusieurs méthodes pour implémenter ce code, en fonction de la plateforme et des besoins de votre entreprise.

* **Extension SDK Web**: Méthode actuelle, normalisée et recommandée pour implémenter Adobe Analytics. Installez l’extension SDK Web dans la collecte de données Adobe Experience Platform, utilisez une balise de chargement sur chaque page et envoyez les données à Adobe Experience Platform Edge dans un format adapté à votre organisation. Experience Edge transfère les données entrantes vers Adobe Analytics dans le format approprié.
* **SDK Web**: Si vous ne souhaitez pas utiliser de balises, vous pouvez charger manuellement les bibliothèques du SDK Web sur votre site. Référencez la bibliothèque SDK Web sur chaque page et envoyez les appels de suivi de votre choix à Adobe Experience Edge.
* **Extension Adobe Analytics** : installez l’extension Adobe Analytics dans la collecte de données Adobe Experience Platform. Placez une balise de chargement sur chaque page et utilisez l’extension Analytics pour déterminer comment chaque variable est définie.
* **Code JavaScript hérité** : méthode manuelle historique pour mettre en œuvre Adobe Analytics. Décrit les variables et les paramètres utilisés dans une implémentation, ce qui peut s’avérer utile pour les implémentations utilisant des règles avec du code personnalisé.
* **SDK mobile :** bibliothèques dédiées pour envoyer facilement des données à Adobe depuis votre application mobile.

## Principaux articles sur l’importation Analytics

* [Prise en charge d’une implémentation Adobe Analytics existante](/help/implement/prepare/existing-implementation.md)
* [Adobe Debugger](validate/debugger.md)
* [Création d’une propriété de balise dans Experience Platform](launch/create-analytics-property.md)
* [Mises à jour d’AppMeasurement](appmeasurement-updates.md)

## Plus de guides d’utilisation d’Analytics

[Guides d’utilisation d’Analytics](https://experienceleague.adobe.com/docs/analytics.html?lang=fr)

## Principales ressources Analytics

* [Contacter l’assistance clientèle](https://experienceleague.adobe.com/?support-solution=Analytics&amp;lang=fr#support)
* [Forum de la communauté Analytics](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics)
* [Ressources Adobe Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/adobe-analytics-resources/m-p/276666?profile.language=fr)
* [Experience League](https://experienceleague.adobe.com/?lang=fr#dashboard/learning)
