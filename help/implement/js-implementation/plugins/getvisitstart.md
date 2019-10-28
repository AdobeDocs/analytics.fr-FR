---
description: Détermine si une nouvelle visite commence.
keywords: Mise en œuvre d’Analytics
seo-description: Détermine si une nouvelle visite commence.
seo-title: getVisitStart
solution: Analytics
title: getVisitStart
topic: Développeur et mise en œuvre
uuid: 7dd3e51f-2f73-4452-a9fb-cac513cd28eb
translation-type: ht
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

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

