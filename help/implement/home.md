---
title: Mise en œuvre d’Adobe Analytics
description: Mettez en œuvre Adobe Analytics sur votre site, propriété ou application.
exl-id: 2b629369-2d69-4dc6-861a-ff21a46d39e0
translation-type: tm+mt
source-git-commit: f3eb3c024a80d0b65729929960173f8b3a4267b0
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 97%

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
* **Gestion** dynamique des balises : La gestion dynamique des balises est désormais en fin de vie.
* **Code JavaScript hérité :** méthode manuelle historique pour mettre en œuvre Adobe Analytics. Décrit les variables et les paramètres utilisés dans une mise en œuvre, ce qui peut s’avérer utile pour les mises en œuvre de Launch utilisant des règles avec du code personnalisé.
* **SDK mobile :** bibliothèques dédiées pour envoyer facilement des données à Adobe depuis votre application mobile.

## Principaux articles sur l’importation Analytics

* [Prise en charge d’une implémentation Adobe Analytics existante](/help/implement/prepare/existing-implementation.md)
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
