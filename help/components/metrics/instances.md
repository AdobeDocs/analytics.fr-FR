---
title: Instances
description: Nombre d’accès pour lesquels une variable (non persistante) a été définie.
feature: Metrics
exl-id: 9d1a66b5-46f9-4834-87a1-5f63e386e61d
source-git-commit: 813d209980ad02c412970a698c282c1358921ed6
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 44%

---

# Instances

Les &quot;Instances&quot; [metric](overview.md) indique le nombre de fois où une dimension a été explicitement définie dans une demande d’image. Certaines dimensions, telles que les [eVars](../dimensions/evar.md), conservent les éléments de dimension au-delà de l’accès sur lequel ils sont définis. Cette mesure s’avère utile lorsque vous souhaitez voir le nombre de fois où un élément de dimension a été défini sans les accès pour lesquels cette valeur a été conservée.

## Méthode de calcul de cette mesure

Sur tous les accès d’une suite de rapports, incluez uniquement les accès qui définissent explicitement un élément de dimension dans la demande d’image. Certaines dimensions, telles que les [eVars](../dimensions/evar.md), persistent au-delà de l’accès pour lequel elles ont été définies. Les mesures telles que [Pages vues](page-views.md) et [Occurrences](occurrences.md) comptabilisent à la fois les valeurs initiales et les valeurs persistantes. Cette mesure ne comptabilise pas les valeurs persistantes.

Par exemple, un visiteur arrive sur votre site et utilise la recherche interne. Vous effectuez le suivi de la recherche interne en eVar1. Après avoir utilisé la recherche interne une seule fois, ils consultent cinq autres pages avant de quitter le site.

Si vous affichez un rapport dans Workspace, une instance eVar1 et six occurrences s’affichent. Une instance compte sur la page des résultats de recherche, tandis que la mesure des occurrences compte la valeur initiale et les valeurs persistantes suivantes.

## Comparaison avec des mesures similaires

* **Instances et [Occurrences](occurrences.md)**: les instances n’incluent pas les accès pour lesquels un élément de dimension persiste. Les occurrences comptabilisent les accès pour lesquels un élément de dimension a été défini ou conservé.
* **Instances et [Pages vues](page-views.md)**: les instances incluent tous les types d’accès, y compris les appels de suivi de pages vues ([`t()`](/help/implement/vars/functions/t-method.md)), appels de suivi des liens ([`tl()`](/help/implement/vars/functions/tl-method.md)), et les données du résumé [Sources de données](/help/import/data-sources/overview.md). La mesure Pages vues inclut uniquement les appels de suivi de pages vues, à l’exclusion des appels de suivi de liens et des sources de données récapitulatives.
