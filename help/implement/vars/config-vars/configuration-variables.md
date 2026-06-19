---
title: Variables de configuration
description: Utilisez les variables de configuration pour déterminer le mode de collecte des données.
feature: Appmeasurement Implementation
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
role: Admin, Developer
TQID: https://experienceleague.adobe.com/amtLWIgyADqWBOv38xdJ6AF4IjhJ0aGVrvYqXLckfkI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ccf6c5e3f25f562a3bfffe89b9ff057c28aab409
workflow-type: tm+mt
source-wordcount: 385
ht-degree: 18%

---

# Présentation des variables de configuration

Les variables de configuration contrôlent le mode de collecte et de traitement des données dans les rapports. Elles ne contiennent généralement pas de valeurs de dimension ou de mesure.

## Définition des variables de configuration

Dans les implémentations utilisant l’extension Web SDK ou l’extension Analytics, les variables de configuration se trouvent généralement dans les paramètres de l’extension :

1. Connectez-vous à [Collecte de données &#x200B;](https://experience.adobe.com/data-collection) à l’aide de vos informations d’identification Adobe ID.
1. Cliquez sur la propriété de balise de votre choix.
1. Cliquez sur l’onglet [!UICONTROL Extensions], puis sur [!UICONTROL Configurer] sous l’extension.

Dans les mises en œuvre JavaScript utilisant `AppMeasurement.js` ; les variables de configuration sont généralement définies en haut du fichier JS.

>[!IMPORTANT]
>
>Assurez-vous que toutes les variables de configuration sont définies avant d’appeler une méthode de suivi ([`t()`](../functions/t-method.md) ou [`tl()`](../functions/tl-method.md)). Évitez de définir des variables de configuration dans la fonction [`doPlugins()`](../functions/doplugins.md).

## Variables de configuration retirées

Les variables de configuration suivantes sont retirées. Ils sont documentés ici à titre de référence si vous les rencontrez dans une implémentation héritée.

* **`account`** : a déterminé la suite de rapports à laquelle les données ont été envoyées. La suite de rapports est désormais gérée par l’instanciation de l’objet de suivi (méthode [`s_gi()`](../functions/s-gi.md)). Utilisez la méthode [`s.sa()`](../functions/sa-method.md) si vous devez modifier la suite de rapports après l’instanciation de l’objet de suivi.
* **`cookieDomain`** : Détermination du domaine sur lequel AppMeasurement a défini les cookies. Les versions actuelles d’AppMeasurement détectent automatiquement le domaine de cookie correct, ce qui rend cette variable obsolète.
* **`cookieDomainPeriods`** : aide d’AppMeasurement à déterminer où stocker les cookies lorsqu’un domaine contient plusieurs périodes. Les versions actuelles d’AppMeasurement détectent automatiquement le domaine correct, ce qui rend cette variable obsolète.
* **`fpCookieDomainPeriods`** : l’équivalent propriétaire de `cookieDomainPeriods`, utilisé pour définir les cookies à l’emplacement correct lorsque le suffixe d’un domaine propriétaire contient un délai supplémentaire (par exemple, `example.co.uk`). Les versions actuelles d’AppMeasurement détectent automatiquement le domaine correct, ce qui rend cette variable obsolète.
* **`trackingServer`** : domaine utilisé pour envoyer des données à Adobe via HTTP. Elle est obsolète et remplacée par la collecte de données sécurisée via HTTPS. Utilisez [`trackingServerSecure`](trackingserversecure.md) à la place.
* **`trackInlineStats`** : activation ou désactivation des versions précédentes d’[Activity Map](/help/analyze/activity-map/overview.md).
* **`visitorMigrationKey`** : possédait une clé utilisée pour migrer les visiteurs de cookies tiers vers des cookies propriétaires. Il est supprimé, car les bibliothèques modernes définissent un cookie de secours propriétaire (`fid`) et s’appuient sur le service Experience Cloud ID pour l’identité.
* **`visitorMigrationServer`** : indique le serveur utilisé lors de la migration des cookies tiers vers les cookies propriétaires.
* **`visitorMigrationServerSecure`** : équivalent HTTPS de `visitorMigrationServer`.
* **`visitorNameSpace`** : aide à déterminer le domaine du cookie tiers. Elle est supprimée au profit de l’utilisation de la variable [`trackingServerSecure`](trackingserversecure.md) pour les implémentations qui n’utilisent pas le service Experience Cloud ID.
