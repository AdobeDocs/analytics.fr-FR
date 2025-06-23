---
title: Présentation des plug-ins
description: Vous permet d’ajouter de nouvelles fonctionnalités en collant le code sur votre site.
feature: Appmeasurement Implementation
exl-id: faae7963-078d-40ad-ba09-71efa0b90df1
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 96%

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
