---
title: Visiteurs avec un Experience Cloud ID
description: Le nombre de visiteurs uniques utilisant le service Adobe Experience Cloud ID.
feature: Metrics
exl-id: 16c170d0-3546-4e0a-8f3c-c141b8a0e4fe
TQID: https://experienceleague.adobe.com/CCk7FDZhZ3mFYXtAggcxnAjvJoJp5zMf0NNk5w0tVY8
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
subfeature_v2: id: e6c28e30-8689-4bf4-8fa8-561343d308a9id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 378
ht-degree: 76%

---

# Visiteurs avec un Experience Cloud ID

La mesure « Visiteurs avec un Experience Cloud ID » [](overview.md) indique le nombre de visiteurs uniques qui ont été identifiés par Adobe à l’aide du service [Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=fr). Cette dimension est utile pour la comparaison avec la mesure [Visiteurs uniques](unique-visitors.md) afin de s’assurer que la majorité des visiteurs de votre site utilise le service d’identifiant. Si une grande partie des visiteurs n’utilisent pas les cookies du service d’ID, cela peut indiquer un problème dans votre implémentation.

>[!NOTE]
>
>Cette mesure est particulièrement importante pour le débogage si vous utilisez plusieurs services d’entreprise CX, tels qu’Adobe Target ou Adobe Audience Manager. Les segments partagés entre les produits CX Enterprise n’incluent pas les visiteurs sans Experience Cloud ID.

## Méthode de calcul de cette mesure

Cette mesure est basée sur la mesure [Visiteurs uniques](unique-visitors.md), mais ne comprend que les individus identifiés à l’aide de la chaîne de requête `mid` (basée sur le cookie [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=fr)).

## Débogage de la configuration Experience Cloud ID

La mesure Visiteurs avec un Experience Cloud ID peut s’avérer utile pour résoudre les problèmes d’intégration des entreprises CX ou identifier les zones de votre site dans lesquelles le service d’ID n’est pas déployé.

Faites glisser « Visiteurs avec un Experience Cloud ID » à côté des visiteurs uniques pour les comparer :

![Comparaison avec les visiteurs uniques](assets/metric-mcvid1.png)

Dans cet exemple, chaque page comporte le même nombre de « Visiteurs uniques » que de « Visiteurs avec un Experience Cloud ID ». Néanmoins, le nombre total de visiteurs uniques est supérieur au nombre total de visiteurs avec un Experience Cloud ID. Vous pouvez créer une [mesure calculée](../calculated-metrics/cm-overview.md) pour déterminer les pages qui ne définissent pas le service d’ID. Vous pouvez utiliser la définition suivante :

![Définition de la mesure calculée](assets/metric-mcvid2.png)

En ajoutant la mesure calculée au rapport, vous pouvez trier le rapport Pages de sorte que les pages comportant le plus grand nombre de visiteurs sans MCID s’affichent :

![Pages sans service d’ID](assets/metric-mcvid3.png)

Notez que l’élément de dimension « Aperçus rapides du produit » n’est pas correctement implémenté avec Identity Service. Vous pouvez collaborer avec les équipes appropriées de votre entreprise pour mettre à jour ces pages le plus rapidement possible. Vous pouvez créer un rapport similaire avec n’importe quel type de dimension, tel que [Type de navigateur](../dimensions/browser-type.md), [Section du site](../dimensions/site-section.md) ou n’importe quelle [eVar](../dimensions/evar.md).
