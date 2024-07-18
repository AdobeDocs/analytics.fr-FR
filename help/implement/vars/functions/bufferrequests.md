---
title: bufferRequests
description: Amélioration de la fiabilité de la capture des requêtes de suivi des liens pour les navigateurs qui déchargent immédiatement la page.
feature: Variables
exl-id: f103deb4-f449-4325-b1a0-23e58a3c9ba0
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 6%

---

# bufferRequests

La méthode `bufferRequests()` vous permet de mettre en cache les demandes d’image sur la page active au lieu de les envoyer à Adobe. Le déclenchement de cette méthode est utile dans les cas où un navigateur ne prend pas en charge [`navigator.sendBeacon()`](https://developer.mozilla.org/fr-FR/docs/Web/API/Navigator/sendBeacon) ou annule les demandes d’image lors du déchargement d’une page. De nombreuses versions de navigateurs WebKit, comme Safari, présentent généralement le comportement d’arrêt d’une demande d’image lorsque vous cliquez sur un lien. La méthode `bufferRequests()` est disponible sur toutes les versions d’AppMeasurement v2.25.0 ou version ultérieure.

Lorsque vous appelez [`t()`](t-method.md) ou [`tl()`](tl-method.md) sur une page ultérieure dans la même session de navigateur et que `bufferRequests()` n’a pas encore été appelé sur cette page, toutes les demandes mises en mémoire tampon sont envoyées en plus de la demande d’image de cette page. Les demandes mises en mémoire tampon sont envoyées dans l’ordre correct, où la demande d’image de la page active est envoyée en dernier.

>[!TIP]
>
>L’horodatage des requêtes mises en mémoire tampon est partagé avec la page sur laquelle les données sont envoyées. Si vous souhaitez plus de précision lors de l’enregistrement exact d’une requête mise en mémoire tampon, vous pouvez définir la variable de page [`timestamp`](../page-vars/timestamp.md) avant de la mettre en mémoire tampon. Si vous utilisez cette variable, assurez-vous que l’option [Horodatages facultatifs](/help/technotes/timestamps-optional.md) est activée. Si ce n’est pas le cas, tous les accès horodatés sont définitivement perdus !

## Limites

Lors de l’appel de la méthode `bufferRequests()`, gardez à l’esprit les limites suivantes. Puisque cette méthode utilise [`Window.sessionStorage`](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API), plusieurs des mêmes limites s’appliquent :

* Le lien de destination doit résider sur le même domaine et sous-domaine. Les requêtes mises en mémoire tampon ne fonctionnent pas entre les domaines ou les sous-domaines, même si les deux disposent de la même mise en oeuvre Adobe Analytics. Cette limitation signifie également que vous ne pouvez pas utiliser de requêtes mises en mémoire tampon pour effectuer le suivi des liens de sortie.
* Le lien de destination doit utiliser le même protocole que la page active. Vous ne pouvez pas envoyer de requêtes mises en mémoire tampon entre HTTP et HTTPS.
* Les requêtes mises en mémoire tampon sont stockées jusqu’à ce que vous appeliez `t()` ou `tl()` sans appeler `bufferRequests()` au préalable, ou jusqu’à la fermeture du navigateur ou de l’onglet. Si une session de navigateur se termine avant de pouvoir envoyer ces données à l’Adobe, les demandes mises en mémoire tampon non envoyées sont définitivement perdues.
* Si un navigateur ne prend pas en charge l’[API de stockage Web](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API) ou l’ [ API JSON](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON), un avertissement s’affiche dans la console du navigateur et l’AppMeasurement tente d’envoyer immédiatement la demande d’image à l’aide de la méthode `t()`.

## Requêtes mises en mémoire tampon dans le SDK Web

Le SDK Web n’offre actuellement pas la possibilité de mettre des requêtes en mémoire tampon.

## Demandes mises en mémoire tampon à l’aide de l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.bufferRequests() dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

Appelez la méthode `bufferRequests()` avant d’appeler `t()` ou `tl()`. Lorsque `bufferRequests()` est appelé, les appels de suivi suivants sont écrits dans le stockage de session au lieu d’être envoyés aux serveurs de collecte de données d’Adobe.

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
