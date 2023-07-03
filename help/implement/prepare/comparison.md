---
title: Comparer les méthodes d’implémentation
description: Découvrez les avantages de chaque méthode d’envoi de données à Adobe Analytics.
exl-id: 19353255-6356-4426-a2ef-5a2672a00eca
feature: Implementation Basics
source-git-commit: d9948fbb63d44c851e08745c77af5618de84a89c
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 76%

---

# Comparer les méthodes d’implémentation

Comparez chaque méthode d’implémentation d’Adobe Analytics. Vous pouvez utiliser ce tableau pour aider votre entreprise à déterminer le meilleur moyen d’envoyer des données à Adobe.

| | AppMeasurement | Extension Adobe Analytics | SDK Web | Extension SDK Web |
| --- | --- | --- | --- | --- |
| Exigences d’implémentation | Référencez `AppMeasurement.js` sur chaque page, définissez des variables et envoyez des données à l’aide de `s.t()`. | Référencez la balise de chargement sur chaque page, utilisez l’interface utilisateur de collecte de données pour définir des variables et envoyez des données à Adobe. | Référencez `Alloy.js` sur chaque page, utilisez `alloy("sendEvent",{})` pour envoyer un objet JSON contenant les données souhaitées. | Référencez la balise de chargement sur chaque page, utilisez l’interface utilisateur de collecte de données pour établir l’objet JSON afin d’envoyer des données. |
| Destination des données | Envoyées directement à Adobe Analytics | Envoyées directement à Adobe Analytics | Envoyées à Adobe Experience Platform Edge, qui transfère les données à Adobe Analytics | Envoyées à Adobe Experience Platform Edge, qui transfère les données à Adobe Analytics |
| Difficulté à effectuer les ajustements d’implémentation | Nécessite un accès au code du site Web pour chaque modification d’implémentation | Modifiez une fois le code du site web pour installer la balise de chargeur ; toutes les autres mises à jour de mise en oeuvre peuvent être effectuées dans l’interface utilisateur de la collecte de données. | Nécessite un accès au code du site Web pour chaque modification d’implémentation | Modifiez une fois le code du site web pour installer la balise de chargeur ; toutes les autres mises à jour de mise en oeuvre peuvent être effectuées dans l’interface utilisateur de la collecte de données. |
| Gestion d’A4T | Les appels A4T sont inclus dans les accès envoyés à Adobe | Les appels A4T sont inclus dans les accès envoyés à Adobe | Les appels A4T sont envoyés sous la forme d’accès distincts | Les appels A4T sont envoyés sous la forme d’accès distincts |
| Données contextuelles | Sélectionnez l’option   `s.contextData`. | Utilisation `s.contextData` dans les blocs de code personnalisé | Tous les champs non mappés sont automatiquement envoyés comme `a.x.*` variables de données contextuelles. | Tous les champs non mappés sont automatiquement envoyés comme `a.x.*` variables de données contextuelles. |

{style="table-layout:auto"}
