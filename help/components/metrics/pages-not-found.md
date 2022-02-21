---
title: Pages introuvables
description: Le nombre d’accès contenant une erreur.
feature: Metrics
exl-id: 71e138b5-69bb-41b0-852c-ca4af22be1f3
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 100%

---

# Pages introuvables

*Cette page d’aide décrit le fonctionnement de la mesure « Pages introuvables ». Pour plus d’informations, consultez la dimension [Pages introuvables](../dimensions/pages-not-found.md).*

La mesure « Pages introuvables » indique le nombre d’accès pour lesquels la page contenait une erreur. Cette mesure s’avère utile lorsque vous souhaitez identifier les pages ou les URL contenant des messages d’erreur (par exemple, 404). Vous pouvez ainsi déterminer la cause de l’erreur et la corriger.

## Méthode de calcul de cette mesure

Cette mesure tient compte de tous les accès pour lesquels la variable [`pageType`](/help/implement/vars/page-vars/pagetype.md) est égale à la valeur de `"errorPage"`. Il s’agit de la mesure équivalente à la dimension [Pages introuvables](../dimensions/pages-not-found.md).
