---
title: Comparer les méthodes d’implémentation
description: Découvrez les avantages de chaque méthode d’envoi de données à Adobe Analytics.
source-git-commit: 96a5daaf9d8358e4a5222a20f64c381cb8340ab1
workflow-type: ht
source-wordcount: '273'
ht-degree: 100%

---

# Comparer les méthodes d’implémentation

Comparez chaque méthode d’implémentation d’Adobe Analytics. Vous pouvez utiliser ce tableau pour aider votre entreprise à déterminer le meilleur moyen d’envoyer des données à Adobe.

|  | AppMeasurement | Extension Adobe Analytics | SDK Web | Extension SDK Web |
| --- | --- | --- | --- | --- |
| Exigences d’implémentation | Référencez `AppMeasurement.js` sur chaque page, définissez des variables et envoyez des données à l’aide de `s.t()`. | Référencez la balise de chargement sur chaque page, utilisez l’interface utilisateur de collecte de données pour définir des variables et envoyez des données à Adobe. | Référencez `Alloy.js` sur chaque page, utilisez `alloy("sendEvent",{})` pour envoyer un objet JSON contenant les données souhaitées. | Référencez la balise de chargement sur chaque page, utilisez l’interface utilisateur de collecte de données pour établir l’objet JSON afin d’envoyer des données. |
| Destination des données | Envoyées directement à Adobe Analytics | Envoyées directement à Adobe Analytics | Envoyées à Adobe Experience Platform Edge, qui transfère les données à Adobe Analytics | Envoyées à Adobe Experience Platform Edge, qui transfère les données à Adobe Analytics |
| Difficulté à effectuer les ajustements d’implémentation | Nécessite un accès au code du site Web pour chaque modification d’implémentation | Le code du site Web ne doit être modifié qu’une seule fois pour installer la balise de chargement. Toutes les autres mises à jour d’implémentation peuvent être effectuées dans l’interface utilisateur de la collecte de données | Nécessite un accès au code du site Web pour chaque modification d’implémentation | Le code du site Web ne doit être modifié qu’une seule fois pour installer la balise de chargement. Toutes les autres mises à jour d’implémentation peuvent être effectuées dans l’interface utilisateur de la collecte de données |
| Gestion d’A4T | Les appels A4T sont inclus dans les accès envoyés à Adobe | Les appels A4T sont inclus dans les accès envoyés à Adobe | Les appels A4T sont envoyés sous la forme d’accès distincts | Les appels A4T sont envoyés sous la forme d’accès distincts |
| Gestion du référent |