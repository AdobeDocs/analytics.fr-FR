---
title: Mise en oeuvre d’Adobe Analytics avec AppMeasurement pour JavaScript
description: Découvrez comment mettre en œuvre Adobe Analytics à l’aide de JavaScript sans système de gestion des balises.
feature: Implementation Basics
exl-id: 25b9d768-c641-4f6c-a4ae-0d6c238c4776
source-git-commit: 99fc7814eaa12d0d9e8e478629a4c2134a577aaa
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 91%

---

# Mise en oeuvre d’Adobe Analytics avec AppMeasurement pour JavaScript

AppMeasurement pour JavaScript a toujours été une méthode courante de mise en œuvre d’Adobe Analytics. Toutefois, avec la popularité croissante des systèmes de Tag Management, il est recommandé d’utiliser les [balises dans Adobe Experience Platform](../launch/overview.md).

## Processus global d’envoi de données à Adobe à l’aide de JavaScript

1. Chargez le fichier `AppMeasurement.js`. Ce fichier contient les bibliothèques requises pour envoyer des données à Adobe.

   ```html
   <script src="AppMeasurement.js"></script>
   ```

2. Définissez des variables de configuration dans `AppMeasurement.js`. Lorsque l’objet Analytics est appelé, ces variables garantissent que les paramètres de collecte de données sont corrects. Voir [Variables de configuration](../vars/config-vars/configuration-variables.md) pour obtenir la liste complète des variables que vous pouvez définir.

   ```js
   // Instantiate the Analytics tracking object with report suite ID
   var s_account = "examplersid";
   var s=s_gi(s_account);
   // Make sure data is sent to the correct location
   s.trackingServer = "example.data.adobedc.net";
   ```

3. Définissez des variables de niveau page dans le code de page de votre site. Ces variables déterminent des dimensions et des mesures spécifiques envoyées à Adobe. Voir [Variables de page](../vars/page-vars/page-variables.md) pour obtenir la liste complète des variables que vous pouvez définir.

   ```js
   s.pageName = "Example page";
   s.eVar1 = "Example eVar";
   s.events = "event1";
   ```

4. Lorsque toutes les variables de niveau page sont définies, envoyez les données à Adobe à l’aide de la méthode `t()`. Voir [t](../vars/functions/t-method.md) pour plus d’informations.

   ```js
   s.t();
   ```
