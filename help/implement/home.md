---
title: Mise en œuvre d’Adobe Analytics
description: Mettez en œuvre Adobe Analytics sur votre site, propriété ou application.
feature: Implementation Basics
exl-id: 2b629369-2d69-4dc6-861a-ff21a46d39e0
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: ht
source-wordcount: '430'
ht-degree: 100%

---

# Mise en œuvre d’Adobe Analytics

![Bannière](../../assets/doc_banner_implement.png)

Voici un aperçu vidéo dʼAdobe Analytics :

>[!VIDEO](https://video.tv.adobe.com/v/27429/?quality=12)

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

* **SDK Web** : la méthode normalisée et recommandée pour implémenter Adobe Analytics. Installez l’extension SDK Web dans la collecte de données Adobe Experience Platform, utilisez une balise de chargement sur chaque page et envoyez les données à Adobe Experience Platform Edge dans un format adapté à votre organisation. Experience Edge transfère les données entrantes vers Adobe Analytics dans le format approprié.
* **Extension Adobe Analytics** : installez l’extension Adobe Analytics dans la collecte de données Adobe Experience Platform. Placez une balise de chargement sur chaque page et utilisez l’extension Analytics pour déterminer comment chaque variable est définie.
* **Code JavaScript hérité :** méthode manuelle historique pour mettre en œuvre Adobe Analytics. Décrit les variables et les paramètres utilisés dans une implémentation, ce qui peut s’avérer utile pour les implémentations de balises à l’aide de règles avec du code personnalisé.
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
* [Experience League](https://experienceleague.adobe.com/?lang=fr#home)
