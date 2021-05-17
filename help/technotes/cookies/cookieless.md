---
title: Options permettant d’atténuer l’effet des limitations des cookies du navigateur
description: Découvrez comment atténuer l’effet des limitations des cookies de navigateur afin d’améliorer la collecte de données pour Adobe Analytics.
source-git-commit: 6c354a343648162ce2951c52a70a688970e1304d
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 5%

---


# Options permettant d’atténuer l’effet des limitations des cookies du navigateur

Ce document présente les options permettant de préserver l’identification persistante des visiteurs entre les propriétés et les solutions lorsque les principaux navigateurs mettent en oeuvre des mesures de prévention du suivi pour les cookies.

Adobe Analytics s’appuie sur des cookies propriétaires pour enregistrer une activité d’visiteur sur le site. Analytics s’appuie également sur des cookies tiers pour comprendre l’activité d’un visiteur hors site, telle que l’activité sur d’autres domaines que vous détenez. Les cookies tiers sont bloqués sur de nombreux navigateurs et seront largement indisponibles avec la suppression prochaine de la prise en charge de Chrome (prévue pour 2022). Les cookies propriétaires sont autorisés sur tous les navigateurs, mais ont une expiration limitée sur Safari et d’autres navigateurs en vertu des mesures de [prévention du suivi ITP](https://webkit.org/tracking-prevention) d’Apple. Pour plus d’informations sur les limitations actuelles des cookies de navigateur, voir [Cookies Adobe Analytics et de navigateur](cookies.md).

Ces limitations de navigateur reflètent une évolution plus large du suivi anonyme par des tiers vers le partage explicite d’informations entre les utilisateurs et les marques en qui ils ont confiance. Pour soutenir cette démarche, l’Adobe offre aux clients des moyens de compléter les cookies traditionnels en incluant des identifiants durables collectés par l’intermédiaire de leurs relations propriétaires.

## Analyses de Customer Journey Analytics et de périphériques croisés

[Adobe des utilisateurs d’](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html) Analyses de Parcours client et d’ [ ](/help/components/cda/overview.md) Analyses multipériphériques afin d’inclure des identifiants durables, tels que les connexions hachées, en plus des cookies. Cela vous permet de comprendre le parcours client sur les différents périphériques et, dans le cas des Customer Journey Analytics, sur les canaux en ligne et hors ligne :

* **L’** analyse du Parcours client est basée sur Adobe Experience Platform et offre la possibilité de combiner des données en ligne et hors ligne dans Analysis Workspace, en fonction de n’importe quel ID client commun. Vous pouvez spécifier l’ID à utiliser pour une analyse donnée et explorer les données dans Analysis Workspace. Les clients Analytics Select, Prime et Ultimate peuvent acheter ce produit en tant que complément.

* **L’** analyse entre plusieurs périphériques améliore l’Adobe Analytics traditionnel, qui permet aux clients d’utiliser d’autres identifiants pour les visiteurs. Cette fonctionnalité vous permet de passer d’une vue axée sur un périphérique à une vue axée sur une personne. Analytics sur plusieurs périphériques est disponible pour les clients Analytics Ultimate.

## Collecte de données côté serveur

La collecte côté serveur offre la possibilité de fournir votre propre identifiant plutôt que de compter sur les mécanismes du navigateur pour définir les cookies.

Vous pouvez envoyer des données côté serveur d’Analytics à l’aide de l’[API d’insertion de données](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/data-insertion-api/index.md) ou de l’[API d’insertion de données en bloc](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md). L&#39;API d&#39;insertion de données en bloc est recommandée pour les nouvelles implémentations côté serveur. Pour une comparaison des deux API, voir &quot;[Quel outil Adobe Analytics dois-je utiliser](https://experienceleague.adobe.com/docs/analytics/admin/admin-overview/which-analytics-tool.html)&quot;.

## Informations supplémentaires

Pour connaître les mesures pratiques que votre entreprise peut prendre pour éviter les cookies tiers, voir [Acquérir et garder les clients dans un monde sans cookie avec Adobe](https://business.adobe.com/solutions/cookieless.html) et la [pensée en profondeur au-delà du cookie tiers : Votre guide complet pour un monde sans cookies tiers](https://business.adobe.com/content/dam/www/us/en/pdfs/Adobe_Thinking_Beyond_the_Third_Party_Cookie.pdf).&quot;

>[!MORELIKETHIS]
[Adobe Analytics et les cookies de navigateur](cookies.md)>
>
