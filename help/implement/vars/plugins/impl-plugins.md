---
title: Présentation des plug-ins
description: Collez le code sur votre site pour introduire de nouvelles fonctionnalités.
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# Présentation des plug-ins

Les plug-ins sont des fragments de code qui exécutent plusieurs fonctions avancées pour faciliter la mise en oeuvre d’Analytics. Ces modules externes étendent les capacités de votre fichier JavaScript en apportant des fonctionnalités qui ne sont pas disponibles avec l’implémentation de base. Adobe propose de nombreux autres modules dans le cadre de solutions avancées.

> [!IMPORTANT] Les plug-ins sont fournis par Adobe Consulting à titre gracieux pour vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit aucune assistance pour ces modules externes, y compris l’installation ou le dépannage. Si vous avez besoin d’aide sur un module externe, contactez le gestionnaire de compte de votre entreprise. Ils peuvent organiser une réunion avec un consultant pour obtenir de l&#39;aide.

Adobe propose plusieurs méthodes pour installer un module externe donné :

1. Utilisation de l’extension Common Analytics Plugins à l’aide d’Adobe Experience Platform Launch
2. Coller le code du module externe à l’aide de l’éditeur de code personnalisé Lancer
3. Collez le code du module externe dans votre `AppMeasurement.js` fichier

Chaque organisation a des besoins d’implémentation différents. Vous pouvez donc décider de la manière dont vous souhaitez les inclure dans votre implémentation. Veillez à respecter les critères suivants lorsque vous incluez le code sur votre site :

1. Instanciez d’abord l’objet de suivi Analytics (à l’aide `s_gi`).
   * Lancer instancie automatiquement l’objet de suivi au chargement d’Adobe Analytics.
   * Implémentations utilisant `AppMeasurement.js` généralement l’initialisation de l’objet de suivi en haut du fichier JavaScript.
2. Insérez le code du module externe en deuxième.
   * L’extension &quot;Plugins Analytics communs&quot; dispose d’une configuration d’action dans laquelle vous pouvez initialiser les plug-ins.
   * Si vous ne souhaitez pas utiliser le module externe, vous pouvez coller le code du module dans l’éditeur de code personnalisé lors de la configuration de l’extension Analytics.
   * Si votre implémentation n’utilise pas le paramètre Lancer, vous pouvez coller le code du module externe n’importe où `AppMeasurement.js` après avoir appelé l’objet de suivi.
3. Appelez le module externe tiers.
   * Toutes les implémentations, à l’intérieur et à l’extérieur de Launch, utilisent JavaScript pour appeler des modules externes. Appelez le module externe au format indiqué sur la page de ce module.
4. Validez votre mise en oeuvre et publiez-la.

De nombreuses organisations appellent des plug-ins à l’aide de la [`doPlugins`](../functions/doplugins.md) fonction. Bien que cette fonction ne soit pas requise, Adobe considère qu’il est préférable de l’utiliser. AppMeasurement appelle cette fonction juste avant de compiler et d’envoyer une demande d’image, ce qui est idéal car plusieurs plug-ins dépendent d’autres variables Analytics.
