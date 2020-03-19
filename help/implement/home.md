---
title: Mise en œuvre d’Adobe Analytics
description: Mettez en œuvre Adobe Analytics sur votre site, propriété ou application.
translation-type: ht
source-git-commit: 8a090574a6822a76366343ad5c657280bf7475eb

---


# Mise en œuvre d’Adobe Analytics

![Bannière](../../assets/doc_banner_implement.png)

Adobe requiert du code sur votre site ou application pour envoyer des données aux serveurs de collecte de données d’Adobe. Les étapes suivantes indiquent le fonctionnement d’une mise en œuvre type.

1. Quand un visiteur arrive sur votre site, une demande est envoyée à votre serveur web.
2. Le serveur web de votre site envoie les informations du code de la page, puis la page s’affiche dans le navigateur.
3. La page se charge et le code JavaScript Analytics s’exécute.
Le code JavaScript envoie une demande d’image aux serveurs de collecte de données Adobe. Les données de page que vous avez définies dans votre mise en œuvre sont envoyées dans le cadre d’une chaîne de requête dans cette demande d’image.

4. Adobe renvoie une image pixel transparente.
5. Les serveurs Adobe stockent les données collectées dans une *suite de rapports*.
6. Les données de la suite de rapports renseignent les rapports auxquels vous avez accès dans un navigateur web.

   L’exécution du code JavaScript survient rapidement et n’affecte pas le temps de chargement de la page de manière notable. Grâce à cette méthode, vous pouvez comptabiliser les pages affichées quand un visiteur a cliqué sur **[!UICONTROL Recharger]** ou **[!UICONTROL Précédent]** pour atteindre une page, puisque le code JavaScript s’exécute même quand la page est récupérée dans la mémoire cache.

Adobe Analytics exige du code sur votre site web, votre application mobile ou toute autre application pour envoyer des données aux serveurs de collecte de données. Il existe plusieurs méthodes de mise en œuvre de ce code, selon la plateforme et les besoins de votre entreprise.

* **Adobe Experience Platform Launch :** méthode normalisée et recommandée pour mettre en œuvre Adobe Analytics. Placez une balise de chargement sur chaque page et utilisez l’interface de Launch pour déterminer la définition de chaque variable.
* **Dynamic Tag Management :** le prédécesseur de Launch. DTM utilise une interface similaire pour implémenter Analytics, mais n’est plus mise à jour et n’est pas aussi flexible. Adobe recommande d’utiliser Launch pour implémenter Adobe Analytics.
* **Code JavaScript hérité :** méthode manuelle historique pour mettre en œuvre Adobe Analytics. Décrit les variables et les paramètres utilisés dans une mise en œuvre, ce qui peut s’avérer utile pour les mises en œuvre de Launch utilisant des règles avec du code personnalisé.
* **SDK mobile :** bibliothèques dédiées pour envoyer facilement des données à Adobe depuis votre application mobile.

## Principaux articles sur l’importation Analytics

* [Adobe Debugger](validate/debugger.md)
* [Création d’une propriété dans Experience Platform Launch](launch/create-analytics-property.md)
* [Mises à jour d’AppMeasurement](appmeasurement-updates.md)

## Plus de guides d’utilisation d’Analytics

[Guides d’utilisation d’Analytics](/help/landing/home.md)

## Principales ressources Analytics

* [Contacter l’assistance clientèle](https://helpx.adobe.com/fr/contact/enterprise-support.ec.html)
* [Forum de la communauté Analytics](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics)
* [Ressources Adobe Analytics](https://forums.adobe.com/message/10660755)
* [Experience League](https://landing.adobe.com/experience-league/)
