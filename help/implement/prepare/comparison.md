---
title: Comparer les méthodes d’implémentation
description: Découvrez les avantages de chaque méthode d’envoi de données à Adobe Analytics.
exl-id: 19353255-6356-4426-a2ef-5a2672a00eca
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 40%

---

# Comparer les méthodes d’implémentation

Comparez chaque méthode d’implémentation d’Adobe Analytics. Vous pouvez utiliser ces tableaux pour aider votre entreprise à déterminer le meilleur moyen d’envoyer des données à Adobe. Cliquez sur chaque colonne pour obtenir des informations plus spécifiques.

## Web

| | [AppMeasurement](/help/implement/js/overview.md) | [Extension Adobe Analytics](/help/implement/launch/overview.md) | [SDK Web](/help/implement/aep-edge/web-sdk/overview.md#web-sdk) | [Extension SDK web](/help/implement/aep-edge/web-sdk/overview.md#web-sdk-extension) |
| --- | --- | --- | --- | --- |
| Exigences d’implémentation | Référencez des `AppMeasurement.js` sur chaque page, définissez des variables et envoyez des données à Adobe Analytics à l’aide de `s.t()` | Référencez la balise de chargement sur chaque page, utilisez l’interface utilisateur de collecte de données pour définir des variables et envoyez des données à Adobe Analytics | Référencez des `Alloy.js` sur chaque page, utilisez des `alloy("sendEvent",{})` pour composer des objets XDM et envoyer les données de votre choix à l’aide d’Edge Network à Adobe Analytics | Référencez la balise de chargement sur chaque page, utilisez l’interface utilisateur de collecte de données pour composer des objets XDM et envoyez les données de votre choix à l’aide d’Edge Network à Adobe Analytics |
| Destination des données | Envoyées directement à Adobe Analytics | Envoyées directement à Adobe Analytics | Envoyées à Adobe Experience Platform Edge, qui transfère les données à Adobe Analytics | Envoyées à Adobe Experience Platform Edge, qui transfère les données à Adobe Analytics |
| Difficulté à effectuer les ajustements d’implémentation | Nécessite un accès au code du site Web pour chaque modification d’implémentation | Modifiez le code du site web une fois pour installer la balise de chargement. Toutes les autres mises à jour d’implémentation peuvent être effectuées dans l’interface utilisateur de la collecte de données | Nécessite un accès au code du site Web pour chaque modification d’implémentation | Modifiez le code du site web une fois pour installer la balise de chargement. Toutes les autres mises à jour d’implémentation peuvent être effectuées dans l’interface utilisateur de la collecte de données |
| Gestion d’A4T | Les appels A4T sont inclus dans les accès envoyés à Adobe | Les appels A4T sont inclus dans les accès envoyés à Adobe | Les appels A4T sont envoyés sous la forme d’accès distincts | Les appels A4T sont envoyés sous la forme d’accès distincts |
| Données contextuelles | Utilisez `s.contextData`. | Utilisation de `s.contextData` dans les blocs de code personnalisés | Tous les champs non mappés sont automatiquement envoyés en tant que variables de données contextuelles `a.x.*`. | Tous les champs non mappés sont automatiquement envoyés en tant que variables de données contextuelles `a.x.*`. |

{style="table-layout:auto"}

## Mobile et autres

>[!CAUTION]
>
>La prise en charge des SDK mobiles version 4 a pris fin le 31 août 2021. Consultez la [FAQ sur la fin de vie d’Adobe Mobile Services](https://experienceleague.adobe.com/docs/discontinued/using/mobile-services.html) pour plus d’informations.


| | [SDK mobile](/help/implement/aep-edge/mobile-sdk/overview.md) | [API Edge Network](/help/implement/aep-edge/api/overview.md) |
| --- | --- | --- |
| Exigences d’implémentation | Référencez la balise de chargement dans l’application, puis utilisez des appels ou des règles d’API directs dans l’interface utilisateur de collecte de données pour composer des objets XDM et envoyer les données de votre choix à l’aide d’Edge Network à Adobe Analytics | Utilisez l’API Edge Network pour composer des objets XDM et envoyer les données de votre choix à l’aide d’Edge Network vers Adobe Analytics |
| Destination des données | Envoyées à Adobe Experience Platform Edge, qui transfère les données à Adobe Analytics | Envoyées à Adobe Experience Platform Edge, qui transfère les données à Adobe Analytics |
| Difficulté à effectuer les ajustements d’implémentation | Modifier le code de l’application dans laquelle les appels API directs sont effectués ou apporter des modifications à l’interface utilisateur de la collecte de données | Nécessite un accès au code de l’application pour chaque modification d’implémentation |
| Gestion d’A4T | Les appels A4T sont envoyés sous la forme d’accès distincts | Les appels A4T sont envoyés sous la forme d’accès distincts |
| Données contextuelles | Tous les champs non mappés sont automatiquement envoyés en tant que variables de données contextuelles `a.x.*`. | Tous les champs non mappés sont automatiquement envoyés en tant que variables de données contextuelles `a.x.*` |

{style="table-layout:auto"}
