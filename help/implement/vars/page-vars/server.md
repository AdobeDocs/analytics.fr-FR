---
title: server
description: Permet de renseigner la dimension « Serveurs ».
feature: Variables
exl-id: 7904c3c2-9a91-497e-89d0-9eed9ae7a902
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 74%

---

# server

La variable `server` stocke généralement le nom d’hôte de votre site. Elle est généralement utilisée dans les suites de rapports qui contiennent des données provenant de plusieurs domaines. Elle est fonctionnellement identique à une prop.

## Serveur utilisant le SDK Web

Le serveur est [mappé pour Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=fr) sous le champ XDM `web.webPageDetails.server`.

## Serveur utilisant l’extension Adobe Analytics

Vous pouvez définir le serveur lors de la configuration de l’extension Analytics (variables globales) ou sous des règles.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une action existante [!UICONTROL Adobe Analytics - Définir des variables] ou cliquez sur l’icône « + ».
5. Définissez la variable [!UICONTROL Extension] de la liste déroulante vers Adobe Analytics, et de la variable [!UICONTROL Type d’action] to [!UICONTROL Définition de variables].
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
