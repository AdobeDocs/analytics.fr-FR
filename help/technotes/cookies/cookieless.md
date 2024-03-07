---
title: Options pour atténuer l’effet des restrictions des cookies de navigateur
description: Découvrez comment atténuer l’effet des restrictions des cookies de navigateur afin d’améliorer la collecte de données pour Adobe Analytics.
feature: Data Configuration and Collection
exl-id: 81cf3f0c-4871-435d-bcc9-bcff5c682f05
role: Admin
source-git-commit: 43c39b99cbae3e714b7f017dec14dd02fa350790
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 99%

---

# Options pour atténuer l’effet des restrictions des cookies de navigateur

Ce document présente les options permettant de préserver l’identification persistante des visiteurs dans les propriétés et les solutions alors que les principaux navigateurs implémentent des mesures de prévention du suivi des cookies.

Adobe Analytics s’appuie sur des cookies propriétaires pour enregistrer l’activité sur site d’un visiteur. Analytics s’appuie également sur des cookies tiers pour comprendre l’activité hors site d’un visiteur, telle que l’activité sur d’autres domaines que vous détenez. Les cookies tiers sont bloqués sur de nombreux navigateurs et seront pour la plupart indisponibles en raison de la fin prochaine de leur prise en charge par Chrome (actuellement prévue pour fin 2024). Les cookies propriétaires sont autorisés sur tous les navigateurs, mais leur expiration est limitée dans Safari et les autres navigateurs sous les [mesures de prévention du suivi ITP](https://webkit.org/tracking-prevention) d’Apple. Pour plus d’informations sur les restrictions actuelles des cookies de navigateur, consultez [Adobe Analytics et les cookies de navigateur](cookies.md).

Ces restrictions de navigateur reflètent une évolution plus large du suivi tiers anonyme vers le partage explicite d’informations entre les utilisateurs et les marques en qui ils ont confiance. Pour prendre en charge cette évolution, Adobe permet aux clients de compléter les cookies traditionnels en incluant des identifiants durables collectés via leurs relations propriétaires.

## Customer Journey Analytics et analyses entre appareils

[Adobe Customer Journey Analyticst](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=fr) et [Analyses entre appareils](/help/components/cda/overview.md) permet aux utilisateurs d’inclure des identifiants durables, tels que des connexions hachées, en plus des cookies. Vous pouvez ainsi comprendre le parcours du client sur plusieurs appareils et, dans le cas de Customer Journey Analytics, sur différents canaux en ligne et hors ligne :

* **Customer Journey Analytics** repose sur Adobe Experience Platform et offre la possibilité de combiner des données en ligne et hors ligne dans Analysis Workspace, en fonction de n’importe quel identifiant d’un client type. Vous pouvez spécifier l’identifiant que vous souhaitez utiliser pour une analyse déterminée et parcourir les données dans Analysis Workspace. Les clients Analytics Select, Prime et Ultimate peuvent l’acheter en tant que produit additionnel.

* **L’analyse entre appareils** est une amélioration d’Adobe Analytics traditionnel qui permet aux clients d’utiliser d’autres identifiants pour les visiteurs. Cette fonctionnalité vous permet de passer d’une vision centrée sur l’appareil à une vision centrée sur la personne. Les analyses entre appareils sont disponibles pour les clients Analytics Ultimate.

## Collecte de données côté serveur

La collecte de données côté serveur offre la possibilité de fournir votre propre identifiant plutôt que de compter sur les mécanismes du navigateur pour définir les cookies.

Vous pouvez envoyer des données à Analytics côté serveur à l’aide de l’[API Data Insertion](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/data-insertion-api/index.md) ou de l’[API Bulk Data Insertion](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md). L’API Bulk Data Insertion est recommandée pour les nouvelles implémentations côté serveur. Pour une comparaison des deux API, voir « [Quel outil Adobe Analytics dois-je utiliser ?](/help/analyze/get-started/which-analytics-tool.md) ».

## Identifiant d’appareil interne (FPID) avec SDK Web

Le SDK Web Adobe Experience Platform vous permet de définir et de gérer vos propres identifiants d’appareil au lieu des Experience Cloud ID générés par Adobe (ECID). Il s’agit d’identifiants d’appareil interne (FPID). En savoir plus [ici](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html).

## Informations supplémentaires

Pour obtenir des instructions pratiques pour que votre entreprise puisse abandonner les cookies tiers, reportez-vous à la section [Obtenir et conserver des clients dans un monde sans cookies avec Adobe](https://business.adobe.com/fr/solutions/cookieless.html) et pour des informations plus détaillées, consultez le guide suivant [Thinking beyond the third-party cookie: Your complete guide to a world without third-party cookies](https://business.adobe.com/content/dam/www/us/en/pdfs/Adobe_Thinking_Beyond_the_Third_Party_Cookie.pdf) (en anglais ; Voir au-delà du cookie tiers : votre guide complet vers un monde sans cookies tiers).

>[!MORELIKETHIS]
>
>[Adobe Analytics et les cookies de navigateur](cookies.md)
