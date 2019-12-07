---
description: La fonction s_gi() sert à créer ou rechercher votre instance AppMeasurement par identifiant de suite de rapports. En interne, AppMeasurement effectue le suivi de toutes les instances créées, tandis que la fonction s_gi() renvoie l’instance existante pour une suite de rapports, le cas échéant. S’il n’existe aucune instance, une nouvelle instance est créée et renvoyée.
keywords: Analytics Implementation
title: Fonction s_gi()
topic: Developer and implementation
uuid: a77de90e-c60e-4946-90cf-deaf8aa3d755
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Fonction s_gi()

La fonction s_gi() sert à créer ou rechercher votre instance AppMeasurement par identifiant de suite de rapports. En interne, AppMeasurement effectue le suivi de toutes les instances créées, tandis que la fonction s_gi() renvoie l’instance existante pour une suite de rapports, le cas échéant. S’il n’existe aucune instance, une nouvelle instance est créée et renvoyée.

Il est conseillé d’appeler `s_gi()` avant de définir des variables et d’effectuer des appels de suivi sur tout le code de page. Cela permet de garantir l’utilisation de l’objet approprié pour effectuer l’appel de suivi, en cas d’écrasement accidentel de la variable s.

## Utilisation de plusieurs suites de rapports {#section_F2F3B76E7AFD4B4B91CDC8BBEB34BBC5}

L’objet renvoyé dépend des identifiants de suite de rapports transmis. Par exemple, si vous effectuez l’appel initial suivant vers la fonction `s_gi()` :

```
var s=s_gi('rsid1,rsid2')
```

Le tableau ci-dessous indique les objets renvoyés par les appels suivants :

| **Appel suivant vers la fonction s_gi** | **Description de l’objet renvoyé** |
|---|---|
| `s=s_gi('rsid1,rsid2')` | Même objet référencé précédemment. |
| `s=s_gi('rsid1')` | Copie de l’objet créé précédemment, mais pas l’original. |
| `s=s_gi('rsid1,rsid3')` | Copie de l’objet créé précédemment, mais pas l’original. |
| `s=s_gi('rsid3')` | Nouvel objet vide, sans variables de configuration définies (par exemple, linkTrackVars est vide, au même titre que linkDownloadFileTypes). |
