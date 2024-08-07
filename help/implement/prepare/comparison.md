---
title: Comparer les méthodes d’implémentation
description: Découvrez les avantages de chaque méthode d’envoi de données à Adobe Analytics.
exl-id: 19353255-6356-4426-a2ef-5a2672a00eca
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: c476a1a19ae514f75fce8bd8e6d447d85de67a84
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 41%

---

# Comparer les méthodes d’implémentation

Comparez chaque méthode d’implémentation d’Adobe Analytics. Vous pouvez utiliser ces tableaux pour aider votre entreprise à déterminer le moyen idéal d’envoyer des données à Adobe. Cliquez sur chaque colonne pour obtenir des informations plus spécifiques.

## Web

| | [AppMeasurement](/help/implement/js/overview.md) | [Extension Adobe Analytics](/help/implement/launch/overview.md) | [SDK Web](/help/implement/aep-edge/web-sdk/overview.md#web-sdk) | [Extension SDK web](/help/implement/aep-edge/web-sdk/overview.md#web-sdk-extension) |
| --- | --- | --- | --- | --- |
| Exigences d’implémentation | Référence `AppMeasurement.js` sur chaque page, définition de variables, envoi de données à l’aide de `s.t()` vers Adobe Analytics | Chargeur de balises de référence sur chaque page, utilisez l’interface utilisateur de collecte de données pour définir des variables et envoyer des données à Adobe Analytics. | Référencez `Alloy.js` sur chaque page, utilisez `alloy("sendEvent",{})` pour composer des objets XDM et envoyer les données souhaitées à l’aide de l’Edge Network à Adobe Analytics. | Chargeur de balises de référence sur chaque page, utilisez l’interface utilisateur de collecte de données pour composer des objets XDM et envoyer les données souhaitées à l’aide de l’Edge Network à Adobe Analytics. |
| Destination des données | Envoyées directement à Adobe Analytics | Envoyées directement à Adobe Analytics | Envoyées à Adobe Experience Platform Edge, qui transfère les données à Adobe Analytics | Envoyées à Adobe Experience Platform Edge, qui transfère les données à Adobe Analytics |
| Difficulté à effectuer les ajustements d’implémentation | Nécessite un accès au code du site Web pour chaque modification d’implémentation | Modifiez une fois le code du site web pour installer la balise de chargeur ; toutes les autres mises à jour de mise en oeuvre peuvent être effectuées dans l’interface utilisateur de la collecte de données. | Nécessite un accès au code du site Web pour chaque modification d’implémentation | Modifiez une fois le code du site web pour installer la balise de chargeur ; toutes les autres mises à jour de mise en oeuvre peuvent être effectuées dans l’interface utilisateur de la collecte de données. |
| Gestion d’A4T | Les appels A4T sont inclus dans les accès envoyés à Adobe | Les appels A4T sont inclus dans les accès envoyés à Adobe | Les appels A4T sont envoyés sous la forme d’accès distincts | Les appels A4T sont envoyés sous la forme d’accès distincts |
| Données contextuelles | Utilisez `s.contextData`. | Utiliser `s.contextData` dans les blocs de code personnalisé | Tous les champs non mappés sont automatiquement envoyés en tant que variables de données contextuelles `a.x.*`. | Tous les champs non mappés sont automatiquement envoyés en tant que variables de données contextuelles `a.x.*`. |

{style="table-layout:auto"}

## Mobile et autres

>[!CAUTION]
>
>La prise en charge des SDK mobiles version 4 a pris fin le 31 août 2021. Pour plus d’informations, voir la [FAQ sur la fin de vie d’Adobe Mobile Services](https://experienceleague.adobe.com/docs/discontinued/using/mobile-services.html) .


| | [SDK Mobile](/help/implement/aep-edge/mobile-sdk/overview.md) | [API serveur](/help/implement/aep-edge/server-api/overview.md) |
| --- | --- | --- |
| Exigences d’implémentation | Chargeur de balises de référence dans l’application, puis utilisez des appels d’API directs ou des règles dans l’interface utilisateur de collecte de données pour composer des objets XDM et envoyer les données souhaitées à l’aide de l’Edge Network à Adobe Analytics. | Utilisez les API de serveur Edge Network pour composer des objets XDM et envoyer les données souhaitées à l’aide de l’Edge Network à Adobe Analytics. |
| Destination des données | Envoyées à Adobe Experience Platform Edge, qui transfère les données à Adobe Analytics | Envoyées à Adobe Experience Platform Edge, qui transfère les données à Adobe Analytics |
| Difficulté à effectuer les ajustements d’implémentation | Modifier le code de l’application dans laquelle des appels API directs sont effectués ou apporter des modifications dans l’interface utilisateur de la collecte de données | Nécessite l’accès au code de l’application pour chaque modification de mise en oeuvre |
| Gestion d’A4T | Les appels A4T sont envoyés sous la forme d’accès distincts | Les appels A4T sont envoyés sous la forme d’accès distincts |
| Données contextuelles | Tous les champs non mappés sont automatiquement envoyés en tant que variables de données contextuelles `a.x.*`. | Tous les champs non mappés sont automatiquement envoyés en tant que variables de données contextuelles `a.x.*` |

{style="table-layout:auto"}
