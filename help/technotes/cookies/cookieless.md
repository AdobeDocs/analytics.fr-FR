---
title: Options pour atténuer l’effet des restrictions des cookies de navigateur
description: Découvrez comment atténuer l’effet des restrictions des cookies de navigateur afin d’améliorer la collecte de données pour Adobe Analytics.
feature: Data Configuration and Collection
exl-id: 81cf3f0c-4871-435d-bcc9-bcff5c682f05
role: Admin
TQID: https://experienceleague.adobe.com/f6gcSRLmsupsIVKYH-bF1T7vuVhoj9Ef8zVh3t6vU2Q
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 590
ht-degree: 98%

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

Vous pouvez envoyer des données à Analytics côté serveur à l’aide de l’[API Data Insertion](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-insertion/) ou de l’[API Bulk Data Insertion](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/). L’API Bulk Data Insertion est recommandée pour les nouvelles implémentations côté serveur. Pour une comparaison des deux API, voir « [Quel outil Adobe Analytics dois-je utiliser ?](/help/analyze/get-started/which-analytics-tool.md) ».

## Identifiant d’appareil interne (FPID) avec SDK Web

Le SDK Web Adobe Experience Platform vous permet de définir et de gérer vos propres identifiants d’appareil au lieu des Experience Cloud ID générés par Adobe (ECID). Il s’agit d’identifiants d’appareil interne (FPID). En savoir plus [ici](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html?lang=fr).

## Informations supplémentaires

Pour obtenir des instructions pratiques pour que votre entreprise puisse abandonner les cookies tiers, reportez-vous à la section [Obtenir et conserver des clients dans un monde sans cookies avec Adobe](https://business.adobe.com/fr/solutions/cookieless.html) et pour des informations plus détaillées, consultez le guide suivant [Thinking beyond the third-party cookie: Your complete guide to a world without third-party cookies](https://business.adobe.com/content/dam/www/us/en/pdfs/Adobe_Thinking_Beyond_the_Third_Party_Cookie.pdf) (en anglais ; Voir au-delà du cookie tiers : votre guide complet vers un monde sans cookies tiers).

>[!MORELIKETHIS]
>
>[Adobe Analytics et les cookies de navigateur](cookies.md)
