---
title: AppMeasurement pour JavaScript
description: Découvrez comment implémenter Adobe Analytics à l’aide de JavaScript sans système de gestion des balises.
translation-type: tm+mt
source-git-commit: 59956169308291e7607a2712cd63a802d7b8bd11

---


# AppMeasurement pour JavaScript

AppMeasurement pour JavaScript a toujours été une méthode courante pour implémenter Adobe Analytics. Toutefois, avec la popularité croissante des systèmes de gestion des balises, il est recommandé d’utiliser [Adobe Experience Platform Launch](../launch/overview.md) .

## Flux global d’envoi de données à Adobe à l’aide de JavaScript

1. Chargez le `AppMeasurement.js` fichier. Ce fichier contient les bibliothèques requises pour envoyer des données à Adobe.

   ```html
   <script src="AppMeasurement.js"></script>
   ```

2. Définissez des variables de configuration dans `AppMeasurement.js`. Lorsque l’objet Analytics est appelé, ces variables garantissent que les paramètres de collecte de données sont corrects. Voir Variables [de](../vars/config-vars/configuration-variables.md) configuration pour obtenir la liste complète des variables que vous pouvez définir.

   ```js
   // Instantiate the Analytics tracking object with report suite ID
   var s_account = "examplersid";
   var s=s_gi(s_account);
   // Make sure data is sent to the correct location
   s.trackingServer = "example.omtrdc.net";
   ```

3. Définissez des variables de niveau page dans le code de page de votre site. Ces variables déterminent des dimensions et des mesures spécifiques envoyées à Adobe. Voir Variables [de](../vars/page-vars/page-variables.md) page pour obtenir la liste complète des variables que vous pouvez définir.

   ```js
   s.pageName = "Example page";
   s.eVar1 = "Example eVar";
   s.events = "event1";
   ```

4. Lorsque toutes les variables de niveau page sont définies, envoyez les données à Adobe à l’aide de la `t` fonction. Voir [t](../vars/functions/t-method.md) pour plus d’informations.

   ```js
   s.t();
   ```
