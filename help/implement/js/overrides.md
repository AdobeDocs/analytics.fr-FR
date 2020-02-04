---
title: Remplacements de variables
description: Les remplacements de variables permettent de modifier une valeur de variable pour un seul suivi ou un appel de lien de suivi.
translation-type: tm+mt
source-git-commit: 1f0fd2dcb0454ad9bc2e0c2141b5e17470c6a5de

---


# Remplacements de variables

Le remplacement de variables vous permet de modifier les valeurs Analytics pour un accès unique sans affecter les variables existantes sur la page.

## Workflow

1. Créez un objet JavaScript. Le nom de l’objet peut être tout ce que vous voulez.

   ```js
   var y = new Object();
   ```

2. Attribuez des propriétés Analytics valides à cet objet :

   ```js
   y.eVar1 = "New value";
   y.events = "event2";
   ```

3. Utilisez l’objet comme argument dans l’appel de suivi approprié :

   ```js
   // Use the override object in a standard page view call
   s.t(y);
   
   // Use the override object in a link tracking call
   s.tl(this,'o','Example override link',y);
   ```

Lorsqu’un appel de suivi reçoit un objet dans le paramètre overrides, toutes les valeurs valides de l’objet override remplacent les valeurs de l’objet Analytics standard. Les variables déjà définies dans votre objet Analytics existant ne sont pas affectées.
