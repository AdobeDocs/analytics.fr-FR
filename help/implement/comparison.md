---
title: Comparaison des méthodes de mise en oeuvre
description: Découvrez les avantages de chaque méthode d’envoi de données à Adobe Analytics.
source-git-commit: 96a5daaf9d8358e4a5222a20f64c381cb8340ab1
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 3%

---

# Comparaison des méthodes de mise en oeuvre

Comparez chaque méthode d’implémentation d’Adobe Analytics. Vous pouvez utiliser ce tableau pour aider votre entreprise à déterminer la méthode la plus idéale pour envoyer des données à Adobe.

|  | AppMeasurement | Extension Adobe Analytics | SDK Web | Extension SDK web |
| --- | --- | --- | --- | --- |
| Exigences d’implémentation | Référence `AppMeasurement.js` sur chaque page, définissez des variables, envoyez des données à l’aide de `s.t()` | Chargeur de balises de référence sur chaque page, utilisez l’interface utilisateur de collecte de données pour définir des variables et envoyer des données à Adobe. | Référence `Alloy.js` sur chaque page, utilisez `alloy("sendEvent",{})` pour envoyer un objet JSON contenant les données souhaitées | Chargeur de balises de référence sur chaque page, utilisez l’interface utilisateur de collecte de données pour établir l’objet JSON à envoyer des données. |
| Destination des données | Transmis directement à Adobe Analytics | Transmis directement à Adobe Analytics | Envoyé à Adobe Experience Platform Edge, qui transfère des données vers Adobe Analytics | Envoyé à Adobe Experience Platform Edge, qui transfère des données vers Adobe Analytics |
| Difficulté à effectuer les ajustements de mise en oeuvre | Nécessite un accès au code du site web pour chaque modification de mise en oeuvre | Le code du site web ne doit être modifié qu’une seule fois pour installer la balise de chargeur ; toutes les autres mises à jour de mise en oeuvre peuvent être effectuées dans l’interface utilisateur de la collecte de données. | Nécessite un accès au code du site web pour chaque modification de mise en oeuvre | Le code du site web ne doit être modifié qu’une seule fois pour installer la balise de chargeur ; toutes les autres mises à jour de mise en oeuvre peuvent être effectuées dans l’interface utilisateur de la collecte de données. |
| Gestion de A4T | Les appels A4T sont inclus dans les accès envoyés à Adobe | Les appels A4T sont inclus dans les accès envoyés à Adobe | Les appels A4T sont envoyés sous la forme d’accès distincts. | Les appels A4T sont envoyés sous la forme d’accès distincts. |
| Gestion du référent |