---
title: Instances
description: Nombre d’accès pour lesquels une variable (non persistante) a été définie.
exl-id: 9d1a66b5-46f9-4834-87a1-5f63e386e61d
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '129'
ht-degree: 100%

---

# Instances

La mesure « Instances » indique le nombre de fois où une dimension a été explicitement définie dans une demande d’image. Certaines dimensions, telles que les [eVars](../dimensions/evar.md), conservent les éléments de dimension au-delà de l’accès sur lequel ils sont définis. Cette mesure s’avère utile lorsque vous souhaitez voir le nombre de fois où un élément de dimension a été défini sans les accès pour lesquels cette valeur a été conservée.

## Méthode de calcul de cette mesure

Sur tous les accès d’une suite de rapports, incluez uniquement les accès qui définissent explicitement un élément de dimension dans la demande d’image. Certaines dimensions, telles que les [eVars](../dimensions/evar.md), persistent au-delà de l’accès pour lequel elles ont été définies. Les mesures telles que [Pages vues](page-views.md) et [Occurrences](occurrences.md) comptabilisent à la fois les valeurs initiales et les valeurs persistantes. Cette mesure ne comptabilise pas les valeurs persistantes.
