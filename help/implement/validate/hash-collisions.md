---
title: Collisions de hachage
description: Décrit ce qu’est une collision de hachage et de quelle façon elle se manifeste.
feature: Implementation Basics
exl-id: 693d5c03-4afa-4890-be4f-7dc58a1df553
role: Admin, Developer
TQID: https://experienceleague.adobe.com/yjYX-h-8jJA7k-jzRMOJ0l2BxN5-no2kCfySkGYss8w
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 9b4525e014170b72688044a6ead344b1bde8c39b
workflow-type: tm+mt
source-wordcount: 539
ht-degree: 5%

---

# Collisions de hachage

Dans Adobe Analytics, les dimensions collectent les valeurs de chaîne. Parfois, ces chaînes comptent des centaines de caractères, tandis que d&#39;autres fois, elles sont courtes. Pour améliorer les performances, ces valeurs de chaîne ne sont pas utilisées directement dans le traitement de la période de rapport. Au lieu de cela, un hachage est calculé pour chaque valeur, produisant un identifiant de taille uniforme. Pour la plupart des champs, la valeur est convertie en minuscules avant le hachage, ce qui réduit le nombre total de valeurs uniques. Tous les rapports s’exécutent sur ces valeurs hachées, ce qui améliore considérablement leurs performances.

Adobe Analytics conserve une table de hachage distincte pour chaque variable, et chaque table est reconstruite chaque mois. Dans l’une de ces tables, deux valeurs source différentes peuvent parfois produire le même hachage, connu sous le nom de *collision de hachage*.

Les collisions de hachage peuvent se manifester dans les rapports comme suit :

* Si vous affichez un rapport au fil du temps et constatez un pic inattendu, il est possible que plusieurs valeurs uniques pour cette variable utilisent le même hachage.
* Si vous utilisez un segment et que vous voyez une valeur inattendue, il est possible que l’élément de dimension inattendu utilise le même hachage qu’un autre élément de dimension correspondant à votre segment.

## Probabilité d’une collision de hachage

Adobe Analytics utilise des hachages 32 bits pour la plupart des dimensions, ce qui signifie qu’il existe 2<sup>32 </sup> de combinaisons de hachage possibles (environ 4,3 milliards). La probabilité approximative de rencontrer une collision de hachage en fonction du nombre de valeurs uniques est la suivante. Ces cotes sont basées sur une seule dimension pour un seul mois.

| Valeurs uniques | Odds |
| --- | --- |
| 1 000 | 0.01% |
| 10 000 | 1% |
| 50 000 | 26% |
| 100 000 | 71% |

Tout comme le [paradoxe d’anniversaire](https://en.wikipedia.org/wiki/Birthday_problem), la probabilité de collisions de hachage augmente considérablement à mesure que le nombre de valeurs uniques augmente. Avec 1 million de valeurs uniques, il est probable qu’il existe au moins 100 collisions de hachage pour cette dimension.

## Réduire les collisions de hachage

Les collisions de hachage ne peuvent pas être entièrement éliminées, mais leur impact sur les rapports peut être atténué. La plupart des collisions de hachage se produisent avec deux valeurs peu courantes, qui n’ont aucun impact significatif sur les rapports. Même si un hachage entre en conflit avec une valeur commune et peu commune, le résultat est négligeable. Cependant, dans les rares cas où deux valeurs populaires subissent une collision de hachage, il est possible de voir clairement son effet. Adobe recommande ce qui suit pour réduire son effet dans les rapports :

* **Modifier la période** : les tableaux de hachage changent tous les mois. Si la période s’étend sur un autre mois, chaque valeur peut avoir des hachages différents qui ne sont pas en conflit. Il s’agit généralement du moyen le plus rapide d’effacer une anomalie visible d’un rapport spécifique.
* **Réduire le nombre de valeurs uniques** : vous pouvez ajuster votre implémentation ou utiliser les [Règles de traitement](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) pour réduire le nombre de valeurs uniques qu’une dimension collecte. Par exemple, si votre dimension collecte une URL, vous pouvez supprimer les chaînes de requête ou le protocole.
* **Utiliser [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) ou [Flux de données](/help/export/analytics-data-feed/data-feed-overview.md)** : ces outils ne reposent pas sur des tables de hachage.
* **Déplacer vers [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=fr)** : Customer Journey Analytics n’a pas de couche de hachage et [aucune limite de cardinalité sur les dimensions](https://experienceleague.adobe.com/docs/analytics-platform/using/components/dimensions/high-cardinality.html). Envisagez de passer à ce produit si des collisions de hachage ou un [[!UICONTROL Faible trafic]](/help/technotes/low-traffic.md) affectent fréquemment vos rapports.

>[!MORELIKETHIS]
>
>* Valeur [[!UICONTROL  Faible trafic ] dans Adobe Analytics](/help/technotes/low-traffic.md)
>* [Présentation des règles de traitement](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)

<!-- https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=OmniArch&title=Uniques -->
