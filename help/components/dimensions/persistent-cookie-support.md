---
title: Prise en charge des cookies persistants
description: Détermine si le visiteur peut prendre en charge les cookies persistants.
feature: Dimensions
exl-id: ced69e41-d992-4c5a-8541-920aeb7186ae
TQID: https://experienceleague.adobe.com/QmbTee9NoWeTmiRdFI3p24idNhzEzK66xb5RY-KKnQ4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 67%
---
# Prise en charge des cookies persistants

La « Prise en charge des cookies persistants » [dimension](overview.md) indique si l’accès a utilisé un identifiant visiteur provenant d’une source persistante. La source persistante la plus courante provient dʼun cookie, mais peut également utiliser des en-têtes Mobile et dʼautres sources.

## Renseignement de cette dimension avec des données

Adobe détermine cette dimension côté serveur, en fonction du fait que l’identifiant visiteur de l’accès provient ou non d’une source qui persiste généralement (un cookie, par exemple). Il n’existe aucune variable à définir et elle est prête à l’emploi pour toutes les implémentations.

| Propriété | Valeur |
| --- | --- |
| **Variable** | Aucun (côté serveur dérivé) |
| **Champ Web SDK/XDM** | Aucun (côté serveur dérivé) |
| **Paramètre de requête** | S.O. |
| **Balise XML** | S.O. |
| **Limite d’octets** | S.O. |
| **Persistance** | S.O. |

## Éléments de dimension

* **`Enabled`** : lʼidentifiant visiteur du hit provient dʼune source qui persiste généralement. Parmi les exemples les plus courants, citons les paramètres de chaîne de requête `aid`, `fid` ou `mid`, car ils dérivent leurs valeurs dʼun cookie.
* **`Disabled`** : lʼidentifiant visiteur du hit provient dʼune source quʼAdobe ne reconnaît pas comme étant persistante, telle que l’adresse IP + la chaîne d’agent utilisateur. Cet élément de dimension inclut également les identifiants visiteurs personnalisés à lʼaide de la variable [`visitorID`](/help/implement/vars/config-vars/visitorid.md).

## Différence entre « Prise en charge des cookies » et « Prise en charge des cookies persistants »

* **Prise en charge des cookies** : AppMeasurement tente de définir un cookie générique. Lʼélément de dimension est basé sur le fait que le cookie a été défini avec succès.
* **Prise en charge des cookies persistants** : lʼélément de dimension est basé sur le fait que lʼidentifiant du hit provient dʼune source persistante, telle quʼun cookie.
