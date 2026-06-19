---
title: Compatibilité des segments avec l’entrepôt de données
description: Découvrez les définitions de segment valides à utiliser dans Data Warehouse.
feature: Data Warehouse
exl-id: 66b86226-ef4c-4a1a-abe1-3c3accf419e5
TQID: https://experienceleague.adobe.com/7CrArNYD-8ZXVpfO86d1l42ySkTuv8V04PWJFeNWx3s
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: a544b409-2610-410d-a842-474ac1d0d54e
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 456
ht-degree: 9%

---

# Compatibilité des segments avec l’entrepôt de données

Tous les segments créés dans le créateur de segments ne peuvent pas être utilisés dans Data Warehouse. Utilisez cette page pour savoir quelles définitions de segment sont compatibles avec Data Warehouse. Vous pourrez ainsi les sélectionner lorsque vous [créez une requête Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

Un segment n’est compatible avec Data Warehouse que lorsque **les deux** conditions suivantes sont vraies :

* **Composants pris en charge** : le segment utilise uniquement les dimensions et mesures prises en charge par Data Warehouse.
* **Structure prise en charge** : la structure du segment suit les règles appliquées par Data Warehouse.

Si l’une de ces conditions n’est pas remplie, le segment n’apparaît pas en tant qu’option lorsque vous créez une requête Data Warehouse, et une erreur s’affiche si vous sélectionnez une suite de rapports virtuelle contenant un segment incompatible.

## Composants pris en charge

Comme un segment est évalué par rapport aux mêmes données que la requête à laquelle il est appliqué, **tout composant qui n’est pas pris en charge dans une requête Data Warehouse n’est pas non plus pris en charge dans un segment.** Pour obtenir la liste complète des dimensions et des mesures non prises en charge par Data Warehouse, voir [Prise en charge des composants dans Data Warehouse](component-support.md).

Outre la dimension et les mesures répertoriées dans [Prise en charge des composants](component-support.md), les dimensions suivantes sont disponibles dans une *requête* Data Warehouse, mais **ne peuvent pas être utilisées dans une définition de segment** :

* [[!UICONTROL Jour du mois]](/help/components/dimensions/day-of-month.md)
* [[!UICONTROL Jour de la semaine]](/help/components/dimensions/day-of-week.md)
* [[!UICONTROL Jour de l’année]](/help/components/dimensions/day-of-year.md)
* [[!UICONTROL Heure de la journée]](/help/components/dimensions/hour-of-day.md)
* [[!UICONTROL Canaux marketing]](/help/components/dimensions/marketing-channel.md) (utilisez plutôt [[!UICONTROL canal Dernière touche]](/help/components/dimensions/last-touch-channel.md))
* [[!UICONTROL Mois de l’année]](/help/components/dimensions/month-of-year.md)
* [[!UICONTROL Pages introuvables]](/help/components/dimensions/pages-not-found.md) (utilisez plutôt [[!UICONTROL Erreur de type de page]](/help/components/dimensions/pages-not-found.md))
* [[!UICONTROL Trimestre de l’année]](/help/components/dimensions/quarter-of-year.md)
* [[!UICONTROL Jour ouvrable/week-end]](/help/components/dimensions/weekday-weekend.md)

## Structure prise en charge

Même lorsqu’un segment utilise uniquement des composants pris en charge, sa structure doit suivre les règles appliquées par Data Warehouse. Les structures de segment sont entièrement prises en charge, partiellement prises en charge ou non prises en charge :

**Pris en charge** :

* **Empilage de segments** : plusieurs segments peuvent être appliqués à une seule requête Data Warehouse.
* **Conteneurs imbriqués** : prise en charge, à condition que la portée diminue à chaque niveau (visiteur → visite → accès). Les conteneurs dont la portée augmente ne sont pas pris en charge.

**Pris en charge en partie** :

* **Exclure les conteneurs** : pris en charge uniquement au niveau supérieur. Data Warehouse ne prend en charge que les segments pouvant être exprimés sous la forme `A AND NOT B`, c’est-à-dire **inclure cette caractéristique** et **exclure cette caractéristique**. Les conteneurs d’exclusion imbriqués dans d’autres conteneurs ne sont pas pris en charge.
* **Logique ET/OU** : pris en charge avec des limitations. Lors de l’utilisation d’un conteneur `exclusion` ou `without` en combinaison avec la logique AND/OR, seuls les segments pouvant être réécrits au fur et à mesure que les `A AND NOT B` sont pris en charge.

**Non pris en charge** :

* **Segments séquentiels** : les segments utilisant l’opérateur THEN pour définir les séquences de navigation ordonnées du visiteur ne sont pas pris en charge.
* **les opérateurs « Est égal à n’importe lequel » et « N’est égal à aucun des »** : ces opérateurs ne sont pas pris en charge dans les segments Data Warehouse.

## Segments utilisés comme dimensions

Lorsque vous utilisez un segment comme une dimension dans un rapport Data Warehouse, le rapport renvoie une colonne contenant des `"0"` ou des `"1"` :

* **`"0"`** : l’élément de dimension ne répondait pas aux critères du segment.
* **`"1"`** : l’élément de dimension répondait aux critères du segment.
