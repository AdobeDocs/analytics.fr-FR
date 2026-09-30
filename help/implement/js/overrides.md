---
title: Remplacements de variables
description: Les remplacements de variables permettent de modifier une valeur de variable pour un seul suivi ou un appel de lien de suivi.
feature: Implementation Basics
exl-id: e297ef94-c5f7-42b1-a9d0-57e073f0d1a9
role: Developer
TQID: 'https://experienceleague.adobe.com/IVA-JMaZPrKpF1NhhL6o3uiCQOOCtZerk78aQTqJAyc'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 100%
---
# Remplacements de variables

Le remplacement de variables vous permet de modifier les valeurs Analytics pour un hit unique sans affecter les variables existantes sur la page.

## Processus

1. Créez un objet JavaScript. Le choix du nom de l’objet est libre.

   ```js
   var y = new Object();
   ```

2. Attribuer des propriétés Analytics valides à cet objet :

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
