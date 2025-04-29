---
title: Pages introuvables (mesures)
description: Le nombre d’accès contenant une erreur.
feature: Metrics
exl-id: 71e138b5-69bb-41b0-852c-ca4af22be1f3
source-git-commit: a15d2b596c1e8b70e91efb49dd607fdbb0ceec3c
workflow-type: tm+mt
source-wordcount: '139'
ht-degree: 35%

---

# Pages introuvables

*Cette page d’aide décrit le fonctionnement de la mesure « Pages introuvables ». Voir la page de dimension [Pages introuvables](../dimensions/pages-not-found.md) pour plus d’informations sur son fonctionnement en tant que dimension.*

La [mesure Pages introuvables](overview.md) indique le nombre d’accès pour lesquels une dimension a été définie ou conservée au moment où un visiteur a rencontré une erreur. Cette mesure est utile lorsque vous souhaitez déterminer les pages ou URL contenant des messages d’erreur (une erreur 404, par exemple). Vous pouvez ensuite transmettre ces informations à votre équipe de développement web, qui peut déterminer la cause de l’erreur et la corriger.

## Méthode de calcul de cette mesure

Cette mesure tient compte de tous les accès pour lesquels la variable [`pageType`](/help/implement/vars/page-vars/pagetype.md) est égale à la valeur de `"errorPage"`. Il s’agit de la mesure équivalente à la dimension [Pages introuvables](../dimensions/pages-not-found.md).
