---
title: Présentation des plug-ins
description: Vous permet d’ajouter de nouvelles fonctionnalités en collant le code sur votre site.
feature: Variables
exl-id: faae7963-078d-40ad-ba09-71efa0b90df1
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 95%

---

# Présentation des plug-ins

Les plug-ins sont des fragments de code qui exécutent plusieurs fonctions avancées pour faciliter la mise en œuvre d’Analytics. Ces plug-ins étendent les capacités de votre fichier JavaScript en apportant des fonctionnalités qui ne sont pas disponibles avec la mise en œuvre de base. Adobe propose de nombreux autres plug-ins dans le cadre de solutions avancées.

>[!IMPORTANT]
>
>Les plug-ins sont fournis par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ces plug-ins, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur un plug-in, contactez le gestionnaire de compte de votre organisation. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

Adobe propose plusieurs méthodes pour installer un plug-in donné :

1. Utilisation de l’extension &quot;Plug-ins Analytics communs&quot; à l’aide du SDK Web ou de l’extension Adobe Analytics
2. Coller le code du plug-in à l’aide de l’éditeur de code personnalisé
3. Coller le code du plug-in dans le fichier `AppMeasurement.js`.

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
