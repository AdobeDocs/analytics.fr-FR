---
title: Pages introuvables (mesures)
description: Le nombre d’accès contenant une erreur.
feature: Metrics
exl-id: 71e138b5-69bb-41b0-852c-ca4af22be1f3
TQID: https://experienceleague.adobe.com/V5jVT8wh71qMrchQmmM6c4EMofHPUEI388TmAf7Zf6M
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 139
ht-degree: 35%

---

# Pages introuvables

*Cette page d’aide décrit le fonctionnement de la mesure « Pages introuvables ». Voir la page de dimension [Pages introuvables](../dimensions/pages-not-found.md) pour plus d’informations sur son fonctionnement en tant que dimension.*

La [mesure Pages introuvables](overview.md) indique le nombre d’accès pour lesquels une dimension a été définie ou conservée au moment où un visiteur a rencontré une erreur. Cette mesure est utile lorsque vous souhaitez déterminer les pages ou URL contenant des messages d’erreur (une erreur 404, par exemple). Vous pouvez ensuite transmettre ces informations à votre équipe de développement web, qui peut déterminer la cause de l’erreur et la corriger.

## Méthode de calcul de cette mesure

Cette mesure tient compte de tous les accès pour lesquels la variable [`pageType`](/help/implement/vars/page-vars/pagetype.md) est égale à la valeur de `"errorPage"`. Il s’agit de la mesure équivalente à la dimension [Pages introuvables](../dimensions/pages-not-found.md).
