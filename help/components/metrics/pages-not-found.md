---
title: Pages introuvables
description: Nombre d’accès contenant une erreur.
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 5%

---


# Pages introuvables

*Cette page d&#39;aide décrit le fonctionnement de &quot;Pages introuvables&quot; en tant que mesure. Pour plus d’informations, voir la dimension[Pages introuvables](../dimensions/pages-not-found.md).*

La mesure Pages introuvables indique le nombre d&#39;accès pour lesquels la page contenait une erreur. Cette mesure s’avère utile lorsque vous souhaitez identifier les pages ou les URL qui contenaient des messages d’erreur (par exemple, 404). Vous pouvez ainsi déterminer la cause de l’erreur et la corriger.

## Méthode de calcul de cette mesure

Cette mesure comptabilise tous les accès pour lesquels la [`pageType`](/help/implement/vars/page-vars/pagetype.md) variable est égale à la valeur de `"errorPage"`. Il s’agit de la mesure équivalente à la dimension [Pages introuvables](../dimensions/pages-not-found.md) .