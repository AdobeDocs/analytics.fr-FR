---
title: 'Instances '
description: Nombre d’accès pour lesquels une variable a été définie (et n’a pas été conservée).
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 1%

---


# Instances 

La mesure Instances montre le nombre de fois où une dimension a été explicitement définie dans une demande d’image. Certaines dimensions, telles que les [eVars](../dimensions/evar.md), conservent les éléments de dimension au-delà de l’accès sur lequel ils sont définis. Cette mesure s’avère utile lorsque vous souhaitez voir le nombre de fois où un élément de dimension a été défini sans les accès pour lesquels cette valeur a persisté.

## Méthode de calcul de cette mesure

Sur tous les accès d’une suite de rapports, incluez uniquement les accès qui définissent explicitement un élément de dimension dans la demande d’image. Certaines dimensions, telles que les [eVars](../dimensions/evar.md), persistent au-delà de l’accès défini. Les mesures telles que vues [de](page-views.md) page et [Occurrences](occurrences.md) comptabilisent à la fois les valeurs initiales et les valeurs persistantes. Cette mesure ne comptabilise pas les valeurs conservées.