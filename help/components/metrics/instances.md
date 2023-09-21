---
title: Instances
description: Nombre d’accès pour lesquels une variable (non persistante) a été définie.
feature: Metrics
exl-id: 9d1a66b5-46f9-4834-87a1-5f63e386e61d
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 57%

---

# Instances

Les &quot;Instances&quot; [metric](overview.md) indique le nombre de fois où une dimension a été explicitement définie dans une demande d’image. Certaines dimensions, telles que les [eVars](../dimensions/evar.md), conservent les éléments de dimension au-delà de l’accès sur lequel ils sont définis. Cette mesure s’avère utile lorsque vous souhaitez voir le nombre de fois où un élément de dimension a été défini sans les accès pour lesquels cette valeur a été conservée.

## Méthode de calcul de cette mesure

Sur tous les accès d’une suite de rapports, incluez uniquement les accès qui définissent explicitement un élément de dimension dans la demande d’image. Certaines dimensions, telles que les [eVars](../dimensions/evar.md), persistent au-delà de l’accès pour lequel elles ont été définies. Les mesures telles que [Pages vues](page-views.md) et [Occurrences](occurrences.md) comptabilisent à la fois les valeurs initiales et les valeurs persistantes. Cette mesure ne comptabilise pas les valeurs persistantes.

Par exemple, un visiteur arrive sur votre site et utilise la recherche interne. Vous effectuez le suivi de la recherche interne en eVar1. Après avoir utilisé la recherche interne une seule fois, ils consultent cinq autres pages avant de quitter le site.

Si vous affichez un rapport dans Workspace, une instance eVar1 et six occurrences s’affichent. L’instance unique déclenchée sur la page des résultats de recherche, tandis que les occurrences comptabilisaient la valeur initiale ainsi que les valeurs persistantes.
