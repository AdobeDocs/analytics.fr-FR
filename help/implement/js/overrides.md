---
title: Remplacements de variables
description: Les remplacements de variables permettent de modifier une valeur de variable pour un seul suivi ou un appel de lien de suivi.
feature: Implementation Basics
exl-id: e297ef94-c5f7-42b1-a9d0-57e073f0d1a9
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 100%

---

# Remplacements de variables

Le remplacement de variables vous permet de modifier les valeurs Analytics pour un accès unique sans affecter les variables existantes sur la page.

## Processus

1. Créez un objet JavaScript. Le choix du nom de l’objet est libre.

   ```js
   var y = new Object();
   ```

2. Attribuez des propriétés Analytics valides à cet objet :

   ```js
   y.eVar1 = "New value";
   y.events = "event2";
   ```

3. Utilisez l’objet comme argument dans l’appel de suivi approprié :

   ```js
   // Use the override object in a standard page view call
   s.t(y);
   
   // Use the override object in a link tracking call
   s.tl(this,'o','Example override link',y);
   ```

Lorsqu’un appel de suivi reçoit un objet dans le paramètre de remplacement, toutes les valeurs valides de l’objet de remplacement remplacent les valeurs de l’objet Analytics standard. Les variables déjà définies dans votre objet Analytics existant ne sont pas affectées.
