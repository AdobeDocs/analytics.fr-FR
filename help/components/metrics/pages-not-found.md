---
title: Pages introuvables (mesures)
description: Le nombre d’accès contenant une erreur.
feature: Metrics
exl-id: 71e138b5-69bb-41b0-852c-ca4af22be1f3
source-git-commit: ed4538efa9a28d40ab18fecd3bd87545808d9ac5
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 45%

---

# Pages introuvables

*Cette page d’aide décrit le fonctionnement de la mesure « Pages introuvables ». Pour plus d’informations, consultez la dimension [Pages introuvables](../dimensions/pages-not-found.md).*

La mesure &quot;Pages introuvables&quot; indique le nombre d’accès pour lesquels une dimension a été définie ou conservée au moment où un visiteur a rencontré une erreur. Cette mesure s’avère utile lorsque vous souhaitez identifier les pages ou les URL qui contenaient des messages d’erreur (par exemple, une 404). Vous pouvez ensuite transmettre ces informations à votre équipe de développement web, qui peut déterminer la cause de l’erreur et la corriger.

## Méthode de calcul de cette mesure

Cette mesure tient compte de tous les accès pour lesquels la variable [`pageType`](/help/implement/vars/page-vars/pagetype.md) est égale à la valeur de `"errorPage"`. Il s’agit de la mesure équivalente à la dimension [Pages introuvables](../dimensions/pages-not-found.md).
