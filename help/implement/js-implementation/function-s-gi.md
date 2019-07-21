---
description: La fonction s_gi() sert à créer ou rechercher votre instance AppMeasurement par identifiant de suite de rapports. En interne, AppMeasurement effectue le suivi de toutes les instances créées, tandis que la fonction s_gi() renvoie l’instance existante pour une suite de rapports, le cas échéant. S’il n’existe aucune instance, une nouvelle instance est créée et renvoyée.
keywords: Mise en œuvre d’Analytics
seo-description: La fonction s_gi() sert à créer ou rechercher votre instance AppMeasurement par identifiant de suite de rapports. En interne, AppMeasurement effectue le suivi de toutes les instances créées, tandis que la fonction s_gi() renvoie l’instance existante pour une suite de rapports, le cas échéant. S’il n’existe aucune instance, une nouvelle instance est créée et renvoyée.
seo-title: Fonction s_gi()
solution: Analytics
title: Fonction s_gi()
topic: Développeur et mise en œuvre
uuid: a 77 de 90 e-c 60 e -4946-90 cf-deaf 8 aa 3 d 755
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Fonction s_gi()

La fonction s_gi() sert à créer ou rechercher votre instance AppMeasurement par identifiant de suite de rapports. En interne, AppMeasurement effectue le suivi de toutes les instances créées, tandis que la fonction s_gi() renvoie l’instance existante pour une suite de rapports, le cas échéant. S’il n’existe aucune instance, une nouvelle instance est créée et renvoyée.

We recommend calling `s_gi()` before setting variables and making tracking calls throughout your page code. Cela permet de garantir l’utilisation de l’objet approprié pour effectuer l’appel de suivi, en cas d’écrasement accidentel de la variable s.

## Utilisation de plusieurs suites de rapports {#section_F2F3B76E7AFD4B4B91CDC8BBEB34BBC5}

L’objet renvoyé dépend des identifiants de suite de rapports transmis. Par exemple, si vous effectuez l’appel initial suivant vers la fonction `s_gi()` :

```
var s=s_gi('rsid1,rsid2')
```

Le tableau ci-dessous indique les objets renvoyés par les appels suivants :

| ** Appel suivant vers la fonction s_gi** | ** Description de l’objet renvoyé** |
|---|---|
| `s=s_gi('rsid1,rsid2')` | Même objet référencé précédemment. |
| `s=s_gi('rsid1')` | Copie de l’objet créé précédemment, mais pas l’original. |
| `s=s_gi('rsid1,rsid3')` | Copie de l’objet créé précédemment, mais pas l’original. |
| `s=s_gi('rsid3')` | Nouvel objet vide, sans variables de configuration définies (par exemple, linkTrackVars est vide, au même titre que linkDownloadFileTypes). |

