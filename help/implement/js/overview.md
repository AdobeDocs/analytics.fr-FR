---
title: Mettre en œuvre Adobe Analytics avec AppMeasurement pour JavaScript
description: Découvrez comment mettre en œuvre Adobe Analytics à l’aide de JavaScript sans système de gestion des balises.
feature: Implementation Basics
exl-id: 25b9d768-c641-4f6c-a4ae-0d6c238c4776
role: Developer
TQID: https://experienceleague.adobe.com/QScNJBw6-Xn-gQCJBBxVT6melUpnyy6VIKrzvnDzJyo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 209
ht-degree: 100%

---

# Mettre en œuvre Adobe Analytics avec AppMeasurement pour JavaScript

AppMeasurement pour JavaScript a toujours été une méthode courante de mise en œuvre d’Adobe Analytics. Toutefois, avec la popularité croissante des systèmes de Tag Management, il est recommandé d’utiliser les [balises dans Adobe Experience Platform](../launch/overview.md).

Présentation générale des tâches d’implémentation :

![Comment mettre en œuvre Adobe Analytics avec AppMeasurement pour JavaScript, comme décrit dans cette section.](../assets/appmeasurement-annotated.png)

<table>

<tr>
<th style="width:5%"></th><th style="width:75%"><b>Tâche</b></th><th style="width:20%"><b>Informations supplémentaires</b></th>
</tr>

<tr>
<td>1</td><td>Vérifiez que vous avez <b>défini une suite de rapports</b>.</td><td><a href="../../admin/tools/manage-rs/report-suites-admin.md">Gestionnaire de suites de rapports</a></td>
</tr>

<tr>
<td>2</td><td><b>Téléchargez le code JavaScript requis pour AppMeasurement</b> à partir du gestionnaire de code. Décompressez le fichier.</td><td><a href="../../admin/tools/code-manager-admin.md">Gestionnaire de code</a></td>
</tr>

<tr>
<td>3</td><td><b>Ajoutez <code>AppMeasurement.js</code> au fichier de modèle de votre site web</b>. Ce code contient les bibliothèques requises pour envoyer des données à Adobe.

```html
<head>
  <script src="AppMeasurement.js"></script>
  …
</head>
```

</td><td></td>
</tr>

<tr>
<td>4</td><td><b>Définissez des variables de configuration dans <code>AppMeasurement.js</code></b>. Lorsque l’objet Analytics est appelé, ces variables garantissent que les paramètres de collecte de données sont corrects.

```JavaScript
// Instantiate the Analytics tracking object with report suite ID
var s_account = "examplersid";
var s=s_gi(s_account);
 
// Make sure data is sent to the correct tracking server
s.trackingServer = "example.data.adobedc.net";
```

</td><td><a href="../vars/config-vars/configuration-variables.md">Variables de configuration</a></td>
</tr>

<tr>
<td>5</td><td><b>Définissez des variables de niveau page dans le code de page de votre site</b>. Ces variables déterminent des dimensions et des mesures spécifiques envoyées à Adobe.

```js
s.pageName = "Example page";
s.eVar1 = "Example eVar";
s.events = "event1";
```

</td><td><a href="../vars/page-vars/page-variables.md">Variables de page</a></td>
</tr>

<tr>
<td>6</td><td><b>Envoyez les données à Adobe à l’aide de la méthode <code>t()</code></b>, lorsque toutes les variables de page sont définies.

```js
s.t();
```

</td><td><a href="../vars/functions/t-method.md">Méthode t()</a></td>
</tr>

<tr>
<td>7</td><td><b>Étendez et validez votre implémentation</b> avant de la diffuser en production.</b></td><td></td>
</tr>

</table>

## Ressources supplémentaires

- [Vue d’ensemble des variables, fonctions, méthodes et plug-ins](../vars/overview.md)
