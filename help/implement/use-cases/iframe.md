---
title: Utilisation d’AppMeasurement avec des iframes
description: Accédez aux variables Adobe Analytics à l’intérieur d’un iframe ou d’une page parente pendant qu’elles se trouvent dans un iframe.
translation-type: tm+mt
source-git-commit: 355985a6baa1a1112e75446012be72f5c0a1d0c2
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 6%

---


# Utilisation d’AppMeasurement avec des iframes

Vous pouvez référencer des variables AppMeasurement à partir d’iframes enfant et parentes. Il est nécessaire de définir toutes les variables au même emplacement que la bibliothèque AppMeasurement. Les exemples suivants expliquent comment définir les variables et méthodes AppMeasurement de base à l’intérieur et à l’extérieur d’un iframe.

Si vous utilisez Adobe Experience Platform Launch, assurez-vous que l’objet de suivi est accessible à tous. Voir [Présentation de l’extension Adobe Analytics](https://docs.adobe.com/content/help/fr-FR/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html) dans le guide de l’utilisateur de lancement.

>!![CAUTION]
Evitez d’inclure des bibliothèques AppMeasurement sur une page parente et un iframe. Cela comporte des risques d’envoi de plusieurs demandes d’image, d’augmentation du nombre de rapports et d’appels serveur facturables.

## Accès à AppMeasurement qui réside dans un iframe

Vous pouvez accéder aux variables AppMeasurement par le biais de l’objet iframe. Ces exemples définissent [pageName](../vars/page-vars/pagename.md) et appellent la méthode [t()](../vars/functions/t-method.md) en utilisant deux méthodes différentes pour référencer l’objet iframe.

```js
// Reference AppMeasurement code that resides within an iframe and send an image request
document.getElementById('targetFrame').contentWindow.s.pageName="Page name within iframe";
document.getElementById('targetFrame').contentWindow.s.t();

// An alternate method to the above if there's only one iframe on the page
window.frames[0].contentWindow.s.pageName = "Page name within iframe";
window.frames[0].contentWindow.s.t();
```

## Accès à AppMeasurement depuis un iframe

Vous pouvez accéder aux variables AppMeasurement sur une page parente depuis un iframe. Cet exemple définit [pageName](../vars/page-vars/pagename.md) et appelle la méthode [t()](../vars/functions/t-method.md) à l&#39;aide de la propriété [`parent`](https://www.w3schools.com/jsref/prop_win_parent.asp).

```js
// Reference AppMeasurement code on a parent page from within an iframe and send an image request
parent.s.pageName = "Page Name on Hosted Window";
parent.s.t();
```

## Utiliser `postMessage` et des écouteurs de événement

Vous pouvez également utiliser `postMessage` et des écouteurs de événement pour définir des variables. Cette méthode ne nécessite pas de référence directe à un iframe.

```js
// Place this code in your parent window
function listenMessage(e) {
    if(e.data == "Example page view call") {
        s.pageName = "Page name using postMessage";
        s.t();
    }
}
window.addEventListener("message", listenMessage, false);

// Place this code in the iframe
window.top.postMessage("Example page view call","https://example.com");
```

## Limites

* Comme pour tout autre code JavaScript, les iframes ne peuvent communiquer que lorsque les domaines et les protocoles correspondent. Ces exemples ne fonctionnent pas si le contenu iframe réside sur un domaine différent de celui du parent.
* Si AppMeasurement réside dans un iframe, la variable [`referrer`](../vars/page-vars/referrer.md) est définie sur l’URL parente et non sur l’URL référente réelle. Vous pouvez définir manuellement la variable `referrer` pour résoudre ce problème.
* Le [débogueur Adobe Experience Cloud](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=fr-FR) ne reconnaît pas les demandes d’image déclenchées dans les iframes.
* Le Activity Map n’affiche pas le heatmap sur les liens sur lesquels l’utilisateur a cliqué dans les iframes. La totalité de l’iframe est mise en surbrillance.
