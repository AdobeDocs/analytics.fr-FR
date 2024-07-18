---
title: Prise en charge des cookies persistants
description: Détermine si le visiteur peut prendre en charge les cookies persistants.
feature: Dimensions
exl-id: ced69e41-d992-4c5a-8541-920aeb7186ae
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 90%

---

# Prise en charge des cookies persistants

La [dimension](overview.md) de la &quot;prise en charge des cookies persistants&quot; indique si l’accès a utilisé un identifiant visiteur provenant d’une source persistante. La source persistante la plus courante provient dʼun cookie, mais peut également utiliser des en-têtes mobiles et dʼautres sources.

## Renseignement de cette dimension avec des données

Adobe détermine la valeur de cette dimension côté serveur en fonction de la source de lʼidentifiant de lʼaccès. Il nʼest pas possible de la définir directement. Elle est prête à lʼemploi pour toutes les implémentations.

## Éléments de dimension

* **`Enabled`** : lʼidentifiant visiteur de lʼaccès provient dʼune source qui persiste généralement. Parmi les exemples les plus courants, citons les paramètres de chaîne de requête `aid`, `fid` ou `mid`, car ils dérivent leurs valeurs dʼun cookie.
* **`Disabled`** : lʼidentifiant visiteur de lʼaccès provient dʼune source quʼAdobe ne reconnaît pas comme étant persistante, telle que lʼIP + la chaîne de lʼagent utilisateur. Cet élément de dimension inclut également les identifiants visiteurs personnalisés à lʼaide de la variable [`visitorID`](/help/implement/vars/config-vars/visitorid.md).

## Différence entre « Prise en charge des cookies » et « Prise en charge des cookies persistants »

* **Prise en charge des cookies** : AppMeasurement tente de définir un cookie générique. Lʼélément de dimension est basé sur le fait que le cookie a été défini avec succès.
* **Prise en charge des cookies persistants** : lʼélément de dimension est basé sur le fait que lʼidentifiant de lʼaccès provient dʼune source persistante, telle quʼun cookie.
