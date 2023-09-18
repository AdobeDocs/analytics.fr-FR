---
title: bufferRequests
description: Amélioration de la fiabilité de la capture des requêtes de suivi des liens pour les navigateurs qui déchargent immédiatement la page.
feature: Variables
source-git-commit: 58a82151a8cbc80318e4f4ab4186fcabef3f35ab
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 6%

---

# bufferRequests

La variable `bufferRequests()` vous permet de mettre en cache les demandes d’image sur la page active au lieu de les envoyer à Adobe. Le déclenchement de cette méthode est utile dans les cas où un navigateur ne prend pas en charge [`navigator.sendBeacon()`](https://developer.mozilla.org/fr-FR/docs/Web/API/Navigator/sendBeacon) ou annule les demandes d’image lors du déchargement d’une page. De nombreuses versions de navigateurs WebKit, comme Safari, présentent généralement le comportement d’arrêt d’une demande d’image lorsque vous cliquez sur un lien. La variable `bufferRequests()` est disponible sur toutes les versions d’AppMeasurement v2.25.0 ou version ultérieure.

Lorsque vous appelez [`t()`](t-method.md) ou [`tl()`](tl-method.md) sur une page suivante de la même session de navigateur et `bufferRequests()` n’a pas encore été appelée sur cette page, toutes les demandes mises en mémoire tampon sont envoyées en plus de la demande d’image de cette page. Les demandes mises en mémoire tampon sont envoyées dans l’ordre correct, où la demande d’image de la page active est envoyée en dernier.

>[!TIP]
>
>L’horodatage des requêtes mises en mémoire tampon est partagé avec la page sur laquelle les données sont envoyées. Si vous souhaitez plus de précision lors de l’enregistrement exact d’une requête mise en mémoire tampon, vous pouvez définir la variable [`timestamp`](../page-vars/timestamp.md) avant la mise en mémoire tampon de la requête. Si vous utilisez cette variable, assurez-vous que la variable [Horodatages facultatifs](/help/technotes/timestamps-optional.md) est activé : dans le cas contraire, tous les accès horodatés sont définitivement perdus.

## Limites

Lorsque vous appelez la fonction `bufferRequests()` , gardez à l’esprit les limites suivantes. Puisque cette méthode utilise [`Window.sessionStorage`](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API), plusieurs des mêmes restrictions s’appliquent :

* Le lien de destination doit résider sur le même domaine et sous-domaine. Les requêtes mises en mémoire tampon ne fonctionnent pas entre les domaines ou les sous-domaines, même si les deux disposent de la même mise en oeuvre Adobe Analytics. Cette limitation signifie également que vous ne pouvez pas utiliser de requêtes mises en mémoire tampon pour effectuer le suivi des liens de sortie.
* Le lien de destination doit utiliser le même protocole que la page active. Vous ne pouvez pas envoyer de requêtes mises en mémoire tampon entre HTTP et HTTPS.
* Les requêtes mises en mémoire tampon sont stockées jusqu’à ce que vous appeliez `t()` ou `tl()` sans appel `bufferRequests()` d’abord, ou jusqu’à ce que le navigateur ou l’onglet soit fermé. Si une session de navigateur se termine avant de pouvoir envoyer ces données à l’Adobe, les demandes mises en mémoire tampon non envoyées sont définitivement perdues.
* Si un navigateur ne prend pas en charge la variable [API de stockage Web](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API) ou le [API JSON](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON), un avertissement s’affiche dans la console du navigateur et l’AppMeasurement tente d’envoyer immédiatement la demande d’image à l’aide de la fonction `t()` .

## Requêtes mises en mémoire tampon dans le SDK Web

Le SDK Web n’offre actuellement pas la possibilité de mettre des requêtes en mémoire tampon.

## Demandes mises en mémoire tampon à l’aide de l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.bufferRequests() dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

Appelez le `bufferRequests()` avant d’appeler `t()` ou `tl()`. When `bufferRequests()` est appelée, les appels de suivi suivants sont écrits dans le stockage de session au lieu d’être envoyés aux serveurs de collecte de données d’Adobe.

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
