---
title: Présentation des plug-ins
description: Vous permet d’ajouter de nouvelles fonctionnalités en collant le code sur votre site.
feature: Appmeasurement Implementation
exl-id: faae7963-078d-40ad-ba09-71efa0b90df1
role: Admin, Developer
TQID: https://experienceleague.adobe.com/ImzoBRU0DajPc99vRlu1698CteFNk9dOS2OZrN9DBZs
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c069c44e-5426-4c1a-accc-8028662f2fdeid: df312454-73c4-43f6-a90e-18f5043f074cid: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c1579802-ddd4-4214-8a91-97b2066abe11id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 410
ht-degree: 79%

---

# Présentation des plug-ins

Les plug-ins sont des fragments de code qui exécutent plusieurs fonctions avancées pour faciliter la mise en œuvre d’Analytics. Ces plug-ins étendent les capacités de votre fichier JavaScript en apportant des fonctionnalités qui ne sont pas disponibles avec la mise en œuvre de base. Adobe propose de nombreux autres plug-ins dans le cadre de solutions avancées.

{{plug-in}}

Adobe propose plusieurs méthodes pour installer un plug-in donné :

* Utiliser l’extension de modules externes courants Analytics à l’aide de l’extension Adobe Analytics
* Coller le code du plug-in à l’aide de l’éditeur de code personnalisé
* Coller le code du plug-in dans le fichier `AppMeasurement.js`.

Chaque organisation a des besoins différents en matière de mise en œuvre. Vous pouvez donc décider de la manière dont vous souhaitez les prendre en compte dans votre mise en œuvre. Veillez à respecter les critères suivants lorsque vous intégrez le code dans votre site :

1. Instanciez d’abord l’objet de suivi Analytics (avec [`s_gi`](../functions/s-gi.md)).
   * Votre site activé pour les balises instancie automatiquement l’objet de suivi au chargement d’Adobe Analytics.
   * Les mises en œuvre utilisant `AppMeasurement.js` initialisent généralement l’objet de suivi en haut du fichier JavaScript.
2. Deuxièmement, intégrez le code du plug-in.
   * L’extension « Plug-ins Analytics communs » dispose d’une configuration d’action qui permet d’initialiser des plug-ins.
   * Si vous ne souhaitez pas utiliser l’extension, vous pouvez coller le code de plug-in dans l’éditeur de code personnalisé lors de la configuration de l’extension Analytics.
   * Si votre implémentation n’utilise pas les balises dans Adobe Experience Platform, vous pouvez coller le code du plug-in dans `AppMeasurement.js` n’importe où après avoir instancié l’objet de suivi.
3. Troisièmement, appelez le plug-in.
   * Toutes les implémentations, aussi bien internes qu’externes au site activé pour les balises, utilisent JavaScript pour faire appel aux plug-ins. Appelez le plug-in en respectant le format indiqué sur la page de ce plug-in.
4. Pour finir, validez votre mise en œuvre et publiez-la.

De nombreuses entreprises utilisent la fonction [`doPlugins`](../functions/doplugins.md) pour faire appel à des plug-ins. Bien que cette fonction ne soit pas requise, Adobe considère qu’il est préférable de l’utiliser. AppMeasurement appelle cette fonction juste avant de compiler et d’envoyer une demande d’image, ce qui est idéal puisque plusieurs plug-ins dépendent d’autres variables Analytics.

## Plug-ins retirés

Les plug-ins suivants ont été retirés. Ils sont documentés ici à titre de référence si vous les rencontrez dans une implémentation héritée.

* **`getPageLoadTime`** : mesure du temps nécessaire à une page pour se charger complètement à l’aide de l’objet de performance JavaScript. Il n’est plus pris en charge, car son code repose sur l’interface [`PerformanceTiming`](https://developer.mozilla.org/fr-FR/docs/Web/API/PerformanceTiming), obsolète dans la plupart des navigateurs modernes. Il n’y a pas de remplacement direct et les instructions d’installation et le code du plug-in ne sont plus disponibles.
