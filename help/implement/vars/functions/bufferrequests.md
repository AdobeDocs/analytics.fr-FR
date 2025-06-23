---
title: bufferRequests
description: Améliorez la fiabilité de la capture des requêtes de suivi des liens pour les navigateurs qui déchargent immédiatement la page.
feature: Appmeasurement Implementation
exl-id: f103deb4-f449-4325-b1a0-23e58a3c9ba0
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 6%

---

# bufferRequests

La méthode `bufferRequests()` permet de mettre en cache les demandes d’image sur la page active au lieu de les envoyer à Adobe. Le déclenchement de cette méthode est utile dans les cas où un navigateur ne prend pas en charge les [`navigator.sendBeacon()`](https://developer.mozilla.org/fr-FR/docs/Web/API/Navigator/sendBeacon) ou annule les demandes d’image lors du déchargement d’une page. De nombreuses versions de navigateurs WebKit, telles que Safari, affichent généralement le comportement d’arrêt d’une demande d’image lorsque vous cliquez sur un lien. La méthode `bufferRequests()` est disponible sur toutes les versions d’AppMeasurement v2.25.0 ou ultérieures.

Lorsque vous appelez [`t()`](t-method.md) ou [`tl()`](tl-method.md) sur une page suivante dans la même session de navigateur et que `bufferRequests()` n’a pas encore été appelé sur cette page, toutes les requêtes mises en mémoire tampon sont envoyées en plus de la requête d’image de cette page. Les requêtes mises en mémoire tampon sont envoyées dans le bon ordre, là où la requête d’image de la page active est envoyée en dernier.

>[!TIP]
>
>La date et l’heure des requêtes mises en mémoire tampon sont partagées avec la page d’envoi des données. Si vous souhaitez plus de précision à la seconde exacte où une requête mise en mémoire tampon est enregistrée, vous pouvez définir la variable de page [`timestamp`](../page-vars/timestamp.md) avant de mettre la requête en mémoire tampon. Si vous utilisez cette variable, assurez-vous que la variable [Horodatages facultatifs](/help/technotes/timestamps-optional.md) est activée. Si ce n’est pas le cas, tous les accès horodatés sont définitivement perdus.

## Limites

Lors de l’appel de la méthode `bufferRequests()`, gardez à l’esprit les restrictions suivantes. Comme cette méthode utilise [`Window.sessionStorage`](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API), plusieurs des mêmes restrictions s’appliquent :

* Le lien de destination doit résider sur le même domaine et sous-domaine. Les requêtes mises en mémoire tampon ne fonctionnent pas sur plusieurs domaines ou sous-domaines, même si les deux ont la même implémentation d’Adobe Analytics. Cette limitation signifie également que vous ne pouvez pas utiliser de requêtes mises en mémoire tampon pour suivre les liens de sortie.
* Le lien de destination doit utiliser le même protocole que la page active. Vous ne pouvez pas envoyer de requêtes mises en mémoire tampon entre HTTP et HTTPS.
* Les requêtes mises en mémoire tampon sont stockées jusqu’à ce que vous appeliez `t()` ou `tl()` sans appeler `bufferRequests()` au préalable, ou jusqu’à ce que le navigateur ou l’onglet soit fermé. Si une session de navigateur se termine avant que vous puissiez envoyer ces données à Adobe, les requêtes mises en mémoire tampon non envoyées sont définitivement perdues.
* Si un navigateur ne prend pas en charge l’[API de stockage web](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API) ou l’[API JSON](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON), un avertissement est généré dans la console du navigateur et AppMeasurement tente d’envoyer immédiatement la demande d’image à l’aide de la méthode `t()`.

## Requêtes mises en mémoire tampon dans le SDK Web

Actuellement, Web SDK ne permet pas de mettre les requêtes en mémoire tampon.

## Requêtes mises en mémoire tampon à l’aide de l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.bufferRequests() dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

Appelez la méthode `bufferRequests()` avant d’appeler `t()` ou `tl()`. Lorsqu’`bufferRequests()` est appelé, les appels de suivi suivants sont écrits dans le stockage de session au lieu d’être envoyés aux serveurs de collecte de données Adobe.

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// Flag the request to be buffered
s.bufferRequests();

// The t() or tl() method then writes the data to session storage instead of sending it to Adobe
s.tl(true,"o","Example link click");

// On a subsequent page, the tracking call sends both the above link tracking call and the page view call
s.t();
```
