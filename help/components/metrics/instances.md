---
title: Instances
description: Nombre d’accès pour lesquels une variable (non persistante) a été définie.
feature: Metrics
exl-id: 9d1a66b5-46f9-4834-87a1-5f63e386e61d
TQID: https://experienceleague.adobe.com/a6Ycw6CVzeSKuOCHezQtLNIZZo6vbkVneVWO0C2QfxQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 263
ht-degree: 50%

---

# Instances

La [mesure](overview.md) Instances indique le nombre de fois où une dimension a été explicitement définie dans une demande d’image. Certaines dimensions, telles que les [eVars](../dimensions/evar.md), conservent les éléments de dimension au-delà de l’accès sur lequel ils sont définis. Cette mesure s’avère utile lorsque vous souhaitez voir le nombre de fois où un élément de dimension a été défini sans les accès pour lesquels cette valeur a été conservée.

## Méthode de calcul de cette mesure

Sur tous les accès d’une suite de rapports, incluez uniquement les accès qui définissent explicitement un élément de dimension dans la demande d’image. Certaines dimensions, telles que les [eVars](../dimensions/evar.md), persistent au-delà de l’accès pour lequel elles ont été définies. Les mesures telles que [Pages vues](page-views.md) et [Occurrences](occurrences.md) comptabilisent à la fois les valeurs initiales et les valeurs persistantes. Cette mesure ne comptabilise pas les valeurs persistantes.

Par exemple, un visiteur arrive sur votre site et utilise la recherche interne. Vous suivez la recherche interne dans eVar1. Après avoir utilisé la recherche interne une fois, ils visitent cinq pages supplémentaires avant de partir.

Si vous affichez un rapport dans Workspace, vous verrez une instance eVar1 et six occurrences. Une instance est comptabilisée sur la page des résultats de la recherche, tandis que la mesure des occurrences comptabilise la valeur initiale et les valeurs persistantes suivantes.

## Comparaison avec des mesures similaires

* **Instances ou [Occurrences](occurrences.md)** : les instances n’incluent pas les accès pour lesquels un élément de dimension persiste. Nombre d’occurrences d’accès pour lesquelles un élément de dimension a été défini ou conservé.
* **Instances par rapport à [Pages vues](page-views.md)** : les instances incluent tous les types d’accès, y compris les appels de suivi des pages vues ([`t()`](/help/implement/vars/functions/t-method.md)), les appels de suivi des liens ([`tl()`](/help/implement/vars/functions/tl-method.md)) et les données provenant de la synthèse [Sources de données](/help/import/data-sources/overview.md). La mesure Pages vues inclut uniquement les appels de suivi de pages vues, à l’exclusion des appels de suivi de liens et des sources de données récapitulatives.
