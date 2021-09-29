---
title: Prise en charge des cookies persistants
description: Détermine si le visiteur peut prendre en charge les cookies persistants.
exl-id: ced69e41-d992-4c5a-8541-920aeb7186ae
source-git-commit: 82d6137bc9229bbaa997c6856690bf76c20b755c
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 11%

---

# Prise en charge des cookies persistants

La dimension &quot;Prise en charge des cookies persistants&quot; indique si l’accès a utilisé un identifiant de visiteur provenant d’une source persistante. La source persistante la plus courante provient d’un cookie, mais peut également utiliser des en-têtes mobiles et d’autres sources.

## Renseignement de cette dimension avec des données

Adobe détermine la valeur de cette dimension côté serveur en fonction de la source de l’identifiant de l’accès. Il n’existe aucun moyen de le définir directement. Il est prêt à l’emploi pour toutes les implémentations.

## Éléments de dimension

* **`Enabled`**: L’identifiant visiteur de l’accès provient d’une source qui persiste généralement. Les exemples les plus courants incluent les paramètres de chaîne de requête `aid`, `fid` ou `mid`, car ils dérivent leurs valeurs d’un cookie.
* **`Disabled`**: L’identifiant visiteur de l’accès provient d’une source que l’Adobe ne reconnaît pas comme persistante, telle que IP + chaîne de l’agent utilisateur. Cet élément de dimension inclut également les identifiants visiteur personnalisés utilisant la variable [`visitorID`](/help/implement/vars/config-vars/visitorid.md) .

## Différence entre &quot;Prise en charge des cookies&quot; et &quot;prise en charge des cookies persistants&quot;

* **Prise en charge** des cookies : AppMeasurement tente de définir un cookie générique. L’élément de dimension est basé sur la définition du cookie.
* **Prise en charge** des cookies persistants : L’élément de dimension est basé sur le fait que l’identifiant de l’accès provient d’une source persistante, telle qu’un cookie.
