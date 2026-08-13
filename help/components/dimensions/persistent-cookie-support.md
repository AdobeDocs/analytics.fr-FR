---
title: Prise en charge des cookies persistants
description: Détermine si le visiteur peut prendre en charge les cookies persistants.
feature: Dimensions
exl-id: ced69e41-d992-4c5a-8541-920aeb7186ae
TQID: https://experienceleague.adobe.com/QmbTee9NoWeTmiRdFI3p24idNhzEzK66xb5RY-KKnQ4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 207
ht-degree: 90%

---

# Prise en charge des cookies persistants

La « Prise en charge des cookies persistants » [dimension](overview.md) indique si l’accès a utilisé un identifiant visiteur provenant d’une source persistante. La source persistante la plus courante provient dʼun cookie, mais peut également utiliser des en-têtes mobiles et dʼautres sources.

## Renseignement de cette dimension avec des données

Adobe détermine la valeur de cette dimension côté serveur en fonction de la source de lʼidentifiant de lʼaccès. Il nʼest pas possible de la définir directement. Elle est prête à lʼemploi pour toutes les implémentations.

## Éléments de dimension

* **`Enabled`** : lʼidentifiant visiteur de lʼaccès provient dʼune source qui persiste généralement. Parmi les exemples les plus courants, citons les paramètres de chaîne de requête `aid`, `fid` ou `mid`, car ils dérivent leurs valeurs dʼun cookie.
* **`Disabled`** : lʼidentifiant visiteur de lʼaccès provient dʼune source quʼAdobe ne reconnaît pas comme étant persistante, telle que lʼIP + la chaîne de lʼagent utilisateur. Cet élément de dimension inclut également les identifiants visiteurs personnalisés à lʼaide de la variable [`visitorID`](/help/implement/vars/config-vars/visitorid.md).

## Différence entre « Prise en charge des cookies » et « Prise en charge des cookies persistants »

* **Prise en charge des cookies** : AppMeasurement tente de définir un cookie générique. Lʼélément de dimension est basé sur le fait que le cookie a été défini avec succès.
* **Prise en charge des cookies persistants** : lʼélément de dimension est basé sur le fait que lʼidentifiant de lʼaccès provient dʼune source persistante, telle quʼun cookie.
