---
description: Les variables de page renseignent directement un rapport (pageName, props de liste, variables de liste, etc.).
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variables de page
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: d5804b411c28270ef910eec5a815532c067a4642

---


# media.trackEvents

La variable identifie les événements qui doivent être envoyés avec un accès au média.

<!-- 

media_trackEvents.xml

 -->

Elle s’applique uniquement à JavaScript et [!UICONTROL ActionSource].

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | N/D | s.Media.trackEvents="None" |

**Syntaxe et valeurs possibles** {#section_66A978EF56914BEAAE73359A268A1B4A}

Noms d’événements tels que « event1 » ou « purchase ».

**Exemples** {#section_140A55D80EA24011954F9383CF312237}

```js
s.Media.trackEvents="event1,purchase"
```

**Pièges, questions et conseils** {#section_030B11C64EE84D46A85CA550DB732D28}

Veillez à renseigner « events » dans la variable [!UICONTROL trackVars], le cas échéant.
