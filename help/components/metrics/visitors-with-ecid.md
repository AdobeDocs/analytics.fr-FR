---
title: Visiteurs avec un Experience Cloud ID
description: Nombre de visiteurs et visiteuses uniques utilisant un ECID.
feature: Metrics
exl-id: 16c170d0-3546-4e0a-8f3c-c141b8a0e4fe
TQID: https://experienceleague.adobe.com/CCk7FDZhZ3mFYXtAggcxnAjvJoJp5zMf0NNk5w0tVY8
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
subfeature_v2:
  - id: e6c28e30-8689-4bf4-8fa8-561343d308a9
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 384
ht-degree: 25%

---

# Visiteurs avec un Experience Cloud ID

La [mesure](overview.md) « [!UICONTROL Visiteurs avec un Experience Cloud ID] » indique le nombre de visiteurs uniques qui ont été identifiés par Adobe avec un ECID (à l’aide du [Service d’identification des visiteurs](https://experienceleague.adobe.com/fr/docs/id-service/using/home) ou [Service d’identification Experience Platform](https://experienceleague.adobe.com/fr/docs/experience-platform/identity/home)). Cette mesure est utile pour la comparaison avec la mesure [Visiteurs uniques](unique-visitors.md) afin de s’assurer que la majorité des visiteurs de votre site utilise un ECID. Si une grande partie des visiteurs n’utilise pas cet identifiant, cela peut indiquer un problème dans votre implémentation.

>[!NOTE]
>
>Cette mesure est particulièrement importante pour le débogage si vous utilisez plusieurs services d’entreprise CX, tels qu’Adobe Target ou Adobe Audience Manager. Les segments partagés entre les produits CX Enterprise n’incluent pas les visiteurs sans ECID.

## Méthode de calcul de cette mesure

Cette mesure est basée sur la mesure [Visiteurs uniques](unique-visitors.md), mais ne comprend que les individus identifiés à l’aide de la chaîne de requête `mid` (basée sur le cookie [`s_ecid`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics)).

## Déboguer la configuration ECID

La mesure « [!UICONTROL &#x200B; Visiteurs avec un ID Experience Cloud &#x200B;] » peut s’avérer utile pour résoudre les problèmes liés aux intégrations d’entreprise CX ou pour identifier les zones de votre site dans lesquelles le service d’identification des visiteurs ou le service d’identification Experience Platform n’est pas déployé.

Faites glisser « [!UICONTROL &#x200B; Visiteurs avec un Experience Cloud ID &#x200B;] » côte à côte avec les visiteurs uniques pour les comparer :

![Comparaison avec les visiteurs uniques](assets/metric-mcvid1.png)

Dans cet exemple, notez que chaque page comporte le même nombre de « [!UICONTROL Visiteurs uniques] » que « [!UICONTROL Visiteurs avec un Experience Cloud ID] ». Cependant, le nombre total de « [!UICONTROL &#x200B; Visiteurs uniques &#x200B;] » est supérieur au nombre total de « [!UICONTROL &#x200B; Visiteurs avec un Experience Cloud ID &#x200B;] ». Vous pouvez créer une [mesure calculée](../calculated-metrics/cm-overview.md) pour déterminer les pages qui n’utilisent pas d’ECID à l’aide de la définition suivante :

![Définition de la mesure calculée](assets/metric-mcvid2.png)

En ajoutant la mesure calculée au rapport, vous pouvez trier le rapport Pages afin que les pages comportant le plus grand nombre de visiteurs sans ECID soient affichées :

![&#x200B; Pages sans ECID &#x200B;](assets/metric-mcvid3.png)

Notez que les éléments de dimension « Aperçu rapide du produit » ne sont pas correctement implémentés avec un ECID. Vous pouvez collaborer avec les équipes appropriées de votre entreprise pour mettre à jour ces pages le plus rapidement possible. Vous pouvez créer un rapport similaire avec n’importe quel type de dimension, tel que [Type de navigateur](../dimensions/browser-type.md), [Section du site](../dimensions/site-section.md) ou n’importe quelle [eVar](../dimensions/evar.md).
