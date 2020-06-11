---
title: 'Instances '
description: Nombre d’accès pour lesquels une variable a été définie (et n’a pas été conservée).
translation-type: tm+mt
source-git-commit: 554ced510600a4d5866e89806b058b5d2d9a3edf
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 1%

---


# Instances 

La mesure Instances montre le nombre de fois où une dimension a été explicitement définie dans une demande d’image. Certaines dimensions, telles que les [eVars](../dimensions/evar.md), conservent les valeurs de dimension au-delà de l’accès sur lequel elles sont définies. Cette mesure s’avère utile lorsque vous souhaitez voir le nombre de fois où une valeur de dimension a été définie sans les accès pour lesquels cette valeur a persisté.

## Méthode de calcul de cette mesure

Sur tous les accès d’une suite de rapports, incluez uniquement les accès qui définissent explicitement une valeur de dimension dans la demande d’image. Certaines dimensions, telles que les [eVars](../dimensions/evar.md), persistent au-delà de l’accès défini. Les mesures telles que vues [de](page-views.md) page et [Occurrences](occurrences.md) comptabilisent à la fois les valeurs initiales et les valeurs persistantes. Cette mesure ne comptabilise pas les valeurs conservées.