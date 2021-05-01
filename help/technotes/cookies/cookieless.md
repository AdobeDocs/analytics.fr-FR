---
title: Options permettant d’atténuer l’effet des limitations des cookies du navigateur
description: Découvrez comment atténuer l’effet des limitations des cookies de navigateur afin d’améliorer la collecte de données pour Adobe Analytics.
translation-type: tm+mt
source-git-commit: 07c76cea1f6fd64957fd4fd20bc5187976f3c14c
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 6%

---


# Options permettant d’atténuer l’effet des limitations des cookies du navigateur

Ce document explique comment préserver l’identification persistante des visiteurs entre les propriétés et les solutions lorsque les principaux navigateurs mettent en oeuvre des mesures de prévention du suivi pour les cookies.

Adobe Analytics s’appuie sur des cookies propriétaires pour enregistrer une activité d’visiteur sur le site. Analytics s’appuie également sur des cookies tiers pour comprendre l’activité d’un visiteur hors site, telle que l’activité sur d’autres domaines que vous détenez. Les cookies tiers sont bloqués sur de nombreux navigateurs et seront largement indisponibles avec la suppression prochaine de la prise en charge de Chrome (prévue pour 2022). Les cookies propriétaires sont autorisés sur tous les navigateurs, mais ont une expiration limitée sur Safari et d’autres navigateurs en vertu des mesures de [prévention du suivi ITP](https://webkit.org/tracking-prevention) d’Apple. Pour plus d’informations sur les limitations actuelles des cookies de navigateur, voir &quot;[Cookies Adobe Analytics et de navigateur](cookies.md).

Ces limitations de navigateur reflètent une évolution plus large du suivi anonyme par des tiers vers le partage explicite d’informations entre les utilisateurs et les marques en qui ils ont confiance. Pour soutenir cette démarche, l’Adobe offre aux clients des moyens de compléter les cookies traditionnels en incluant des identifiants durables collectés par l’intermédiaire de leurs relations propriétaires.

## Analyses de Customer Journey Analytics et de périphériques croisés

[Adobe des utilisateurs d’](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html) Analyses de Parcours client et d’ [ ](/help/components/cda/overview.md) Analyses multipériphériques afin d’inclure des identifiants durables, tels que les connexions hachées, en plus des cookies :

* **Parcours client** Analytics peut effectuer une analyse entre canaux à Analysis Workspace par le biais d’une intégration avec Adobe Experience Platform. Il consolide les données client en ligne et hors ligne disponibles dans l’Experience Platform au moment de la requête, à l’aide de n’importe quel ID.

* **L’** analyse sur plusieurs périphériques identifie la manière dont les périphériques numériques correspondent aux personnes et sélectionne le parcours utilisateur sur n’importe quel ID à l’aide du service d’identité Adobe Experience Platform. Il utilise soit le graphique Adobe Experience Cloud Device Co-op, soit un graphique de périphérique privé, soit l’assemblage sur le terrain.

## Collecte de données côté serveur

La collecte côté serveur offre la possibilité de fournir votre propre identifiant plutôt que de compter sur les mécanismes du navigateur pour définir les cookies.

Vous pouvez importer des données côté serveur dans Analytics à l’aide de l’[API d’insertion de données](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/data-insertion-api/index.md) ou de l’[API d’insertion de données en bloc](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md). Pour une comparaison des deux API, voir &quot;[Quel outil Adobe Analytics dois-je utiliser](https://experienceleague.adobe.com/docs/analytics/admin/admin-overview/which-analytics-tool.html)&quot;.

## Informations supplémentaires

Pour connaître les mesures pratiques que votre entreprise peut prendre pour éviter les cookies tiers, consultez &quot;[Acquérir et garder les clients dans un monde sans cookie avec Adobe](https://business.adobe.com/solutions/cookieless.html)&quot; et la section plus détaillée &quot;[Penser au-delà du cookie tiers : Votre guide complet pour un monde sans cookies tiers](https://business.adobe.com/content/dam/www/us/en/pdfs/Adobe_Thinking_Beyond_the_Third_Party_Cookie.pdf).&quot;

>[!MORELIKETHIS]
>
>[Adobe Analytics et les cookies de navigateur](cookies.md)
