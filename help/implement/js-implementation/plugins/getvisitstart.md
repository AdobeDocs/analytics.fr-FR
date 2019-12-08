---
description: Détermine si une nouvelle visite commence.
keywords: Analytics Implementation
title: getVisitStart
topic: Developer and implementation
uuid: 7dd3e51f-2f73-4452-a9fb-cac513cd28eb
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

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

