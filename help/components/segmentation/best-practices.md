---
title: Bonnes pratiques
description: Découvrez quelques bonnes pratiques en matière de segmentation.
feature: Segmentation
exl-id: 4115a804-5063-430a-b9d3-2b64b26ca4d8
TQID: https://experienceleague.adobe.com/PJi-kkv6HL3jHEKArltzxMGk9BVtZ-Mr1ivHMkhxt88
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 304
ht-degree: 60%

---

# Bonnes pratiques de la segmentation

Des segments complexes sont souvent nécessaires pour obtenir les données souhaitées. Si les segments complexes sont inefficaces et utilisés dans une suite de rapports volumineuse, l’exécution des rapports est considérablement plus longue. Tenez compte des ressources suivantes lors de la création ou de la modification d’un segment afin de minimiser la complexité.

## N’utilisez l’opérateur `Contains` qu’en dernier recours

L’opérateur [**[!UICONTROL Contains &#x200B;]**](/help/components/segmentation/seg-reference/seg-operators.md) est l’une des fonctionnalités de segmentation les plus gourmandes en traitement, dans la mesure où l’opérateur doit analyser l’intégralité du contenu de chaque valeur. Pensez à utiliser d’autres opérateurs tels que&#x200B;**[!UICONTROL &#x200B; Commence par &#x200B;]**&#x200B;ou&#x200B;**[!UICONTROL &#x200B; Se termine par &#x200B;]**&#x200B;si les valeurs souhaitées se trouvent au début ou à la fin d’une chaîne.

Si un opérateur **[!UICONTROL Contient]** dans un segment renvoie un grand nombre de résultats, le rapport expire généralement. Par exemple, si vous avez créé un segment où **[!UICONTROL Référent]** **[!UICONTROL égal]** `"."`, le segment recherche dans le contenu de chaque valeur. Envisagez plutôt l’utilisation de l’opérateur **[!UICONTROL Exists]**.

## Utilisez des classifications pour regrouper des éléments de dimension

Si vous avez de nombreuses conditions de segment, elles peuvent rapidement dégrader les performances des segments. Par exemple, **[!UICONTROL Page]** **[!UICONTROL est égal à]** `X` **[!UICONTROL OU]** **[!UICONTROL Page]** **[!UICONTROL est égal à]** `Y`OR **[!UICONTROL Page]**&#x200B;égal **&#x200B;**&#x200B;**&#x200B;** `Z` répété avec des centaines de valeurs différentes. Au lieu d’écrire ces centaines de conditions, classifiez toutes les valeurs souhaitées dans un segment, puis utilisez la valeur classifiée dans un segment.

1. Créez une classification pour la variable que vous utilisez.
2. Téléchargez le modèle de classification et ouvrez-le dans la feuille de calcul ou l’éditeur de texte de votre choix.
3. Donnez la même valeur à chaque élément de dimension que vous souhaitez inclure dans votre segment.
4. Utilisez l’importateur de classifications pour réimporter la feuille de calcul dans Adobe Analytics.
5. Une fois le traitement de la classification terminé, créez un segment à l’aide de la valeur classifiée.

Cette méthode augmente considérablement les performances et permet de modifier facilement les conditions de segment. Au lieu de modifier le segment avec des valeurs différentes, vous pouvez ajouter ou supprimer des éléments de dimension de la classification.
