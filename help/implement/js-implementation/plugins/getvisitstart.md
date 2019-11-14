---
description: Détermine si une nouvelle visite commence.
keywords: Analytics Implementation
solution: Analytics
title: getVisitStart
topic: Developer and implementation
uuid: 7dd3e51f-2f73-4452-a9fb-cac513cd28eb
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# getVisitStart

Détermine si une nouvelle visite commence.

**Variables de configuration**

Aucun

**Paramètres**

Nom du cookie c = (chaîne) pour le suivi.

**Retours**

(entier) 1 sur la première page de la visite, sinon 0.

**Exemples d’appel**

```
s.eVar50 = s.getVisitStart("s_visit");
```

