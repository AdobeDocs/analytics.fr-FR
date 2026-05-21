---
title: server
description: Permet de renseigner la dimension « Serveurs ».
feature: Appmeasurement Implementation
exl-id: 7904c3c2-9a91-497e-89d0-9eed9ae7a902
role: Admin, Developer
TQID: https://experienceleague.adobe.com/HR37R-XDPYMhGTYxNbavO7utFH9wZgXNLDGdnmm-Gb0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 187
ht-degree: 82%

---

# server

La variable `server` stocke généralement le nom d’hôte de votre site. Elle est généralement utilisée dans les suites de rapports qui contiennent des données provenant de plusieurs domaines. Elle est fonctionnellement identique à une prop.

## Serveur utilisant le SDK Web

Le serveur est mappé aux variables suivantes :

* [Objet XDM](/help/implement/aep-edge/xdm-var-mapping.md) : `xdm.web.webPageDetails.server`
* [Objet de données](/help/implement/aep-edge/data-var-mapping.md) : `data.__adobe.analytics.server`

## Serveur utilisant l’extension Adobe Analytics

Vous pouvez définir le serveur lors de la configuration de l’extension Analytics (variables globales) ou sous des règles.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une action existante [!UICONTROL Adobe Analytics - Définir des variables] ou cliquez sur l’icône « + ».
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics et le [!UICONTROL type d’action] sur [!UICONTROL Définir des variables].
6. Recherchez la section [!UICONTROL Serveur].

Vous pouvez définir le serveur sur n’importe quelle valeur de chaîne ou élément de données.

## s.server dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.server` est une chaîne qui contient généralement le nom d’hôte de votre site. Celle-ci a une valeur maximale de 100 octets ; les valeurs plus longues sont tronquées.

```js
// Set the server variable to a static string
s.server = "Example server";

// Automatically set the server variable to the site's hostname
s.server = window.location.hostname;
```
