---
title: server
description: Renseignez la dimension "Serveurs".
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# server

La `server` variable stocke généralement le nom d’hôte de votre site. Il est généralement utilisé dans les suites de rapports qui contiennent des données provenant de plusieurs domaines. Fonctionnellement identique à une prop.

## Serveur dans Adobe Experience Platform Launch

Vous pouvez définir le serveur lors de la configuration de l’extension Analytics (variables globales) ou sous des règles.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur une propriété.
3. Accédez à l’onglet [!UICONTROL Règles] , puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une action existante [!UICONTROL Adobe Analytics - Définir des variables] ou cliquez sur l’icône &quot;+&quot;.
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics et le type [!UICONTROL d’] action sur [!UICONTROL Définir des variables].
6. Recherchez la section [!UICONTROL Serveur] .

Vous pouvez définir le serveur sur n’importe quelle valeur de chaîne ou élément de données.

## s.server dans l’éditeur de code personnalisé AppMeasurement et Lancement

La `s.server` variable est une chaîne qui contient généralement le nom d’hôte de votre site. Il a une valeur maximale de 100 octets ; les valeurs plus longues sont tronquées.

```js
// Set the server variable to a static string
s.server = "Example server";

// Automatically set the server variable to the site's hostname
s.server = window.location.hostname;
```
