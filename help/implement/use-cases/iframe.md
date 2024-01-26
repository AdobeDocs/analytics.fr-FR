---
title: Utilisation dʼAppMeasurement avec des iFrames
description: Accédez aux variables Adobe Analytics à lʼintérieur dʼun iframe ou dʼune page parente dans un iframe.
feature: Implementation Basics
exl-id: 59b9cd4f-8599-41ee-8b54-a6a556198ecd
role: Admin, Developer, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 100%

---

# Utilisation dʼAppMeasurement avec des iFrames

Vous pouvez référencer des variables AppMeasurement à partir des iFrames enfant et parent. Il est nécessaire de définir toutes les variables au même emplacement où se trouve la bibliothèque AppMeasurement. Les exemples suivants expliquent la manière de définir les variables et méthodes AppMeasurement de base à lʼintérieur et à lʼextérieur dʼun iframe.

Si vous utilisez des balises dans Adobe Experience Platform, assurez-vous que lʼobjet de suivi est accessible de manière globale. Consultez la [Présentation de lʼextension Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=fr).

>[!CAUTION]
>
>Evitez dʼinclure des bibliothèques AppMeasurement sur une page parente et un iframe. Cela comporte des risques dʼenvoyer de multiples demandes dʼimage, de gonfler les rapports et dʼaugmenter le nombre dʼappels au serveur facturables.

## Accès à AppMeasurement qui réside dans un iframe

Vous pouvez accéder aux variables AppMeasurement par le biais de lʼobjet iframe. Ces exemples définissent [pageName](../vars/page-vars/pagename.md) et appellent la [méthode t()](../vars/functions/t-method.md) à lʼaide de deux méthodes différentes pour référencer lʼobjet iframe.

```js
// Reference AppMeasurement code that resides within an iframe and send an image request
document.getElementById('targetFrame').contentWindow.s.pageName="Page name within iframe";
document.getElementById('targetFrame').contentWindow.s.t();

// An alternate method to the above if there's only one iframe on the page
window.frames[0].contentWindow.s.pageName = "Page name within iframe";
window.frames[0].contentWindow.s.t();
```

## Accès à AppMeasurement depuis lʼintérieur dʼun iframe

Vous pouvez accéder aux variables AppMeasurement sur une page parente depuis lʼintérieur dʼun iframe. Cet exemple définit [pageName](../vars/page-vars/pagename.md) et appelle la [méthode t()](../vars/functions/t-method.md) à lʼaide de la propriété [`parent`](https://www.w3schools.com/jsref/prop_win_parent.asp).

```js
// Reference AppMeasurement code on a parent page from within an iframe and send an image request
parent.s.pageName = "Page Name on Hosted Window";
parent.s.t();
```

## Utilisation de `postMessage` et des récepteurs dʼévénements

Vous pouvez également utiliser `postMessage` et des récepteurs dʼévénements pour définir des variables. Cette méthode ne nécessite pas de référence directe à un iframe.

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

* Comme pour tout autre code JavaScript, les iFrames ne peuvent communiquer que lorsque les domaines et les protocoles correspondent. Ces exemples ne fonctionnent pas si le contenu de lʼiframe réside sur un domaine différent de celui du parent.
* Si AppMeasurement réside dans un iframe, la variable [`referrer`](../vars/page-vars/referrer.md) est définie sur lʼURL parente et non sur lʼURL référente réelle. Vous pouvez définir manuellement la variable `referrer` pour résoudre ce problème.
* Lʼ[Experience Cloud Debugger dʼAdobe](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=fr) ne reconnaît pas les demandes dʼimage déclenchées dans les iFrames.
* Activity Map nʼaffiche pas la carte thermique sur les liens sur lesquels lʼutilisateur a cliqué dans les iFrames. La totalité de lʼiframe est mise en surbrillance à la place.
