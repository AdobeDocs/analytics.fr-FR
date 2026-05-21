---
title: Analyse des données affectées par les événements
description: Comprendre comment les données affectées par un événement contribuent à la qualité générale des données.
exl-id: 8d81a432-42d6-4f5d-b66a-bb3af7fc4857
feature: Curate and Share
TQID: https://experienceleague.adobe.com/DJoJwtp9CkgrCfA1DwW8rKX2x3ssfzLCo7vCfhdLusg
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b4dd41a7-ccf8-4e9d-918e-acaab534a307id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 404
ht-degree: 91%

---

# Analyse des données affectées par les événements

Parfois, un événement peut avoir un impact sur la qualité des données de votre entreprise. Par exemple :

* Un robot qui envoie des données de valeurs aberrantes, telles que des millions de dollars de chiffre d’affaires.
* Votre entreprise a effectué une mise à jour du site Web qui a eu un impact négatif sur votre mise en œuvre d’Analytics.
* D’autres problèmes qui affectent la qualité ou l’exhaustivité des données.

Si votre site a rencontré le moindre problème de qualité en matière de données, vous pouvez l’exclure des rapports afin d’éviter la prise de décisions professionnelles sur base de celui-ci. Utilisez ces sections pour évaluer l’impact de l’événement sur vos données et déterminer comment procéder.

## Identification de la cause d’un événement

Si vous ignorez pourquoi vous constatez un pic ou une baisse de données, consultez [Résolution des problèmes liés aux pics/baisses de données](spikes-drops.md).

## Analyse et exclusion des données par segmentation

Adobe Analytics offre une méthode simple et robuste pour mettre l’accent sur les données ou les exclure à l’aide de la segmentation. Vous pouvez utiliser les dimensions de période dans les segments pour filtrer ces dates spécifiques ou vous concentrer sur celles-ci. Consultez [Exclusion de dates spécifiques dans l’analyse](segments.md).

## Comparaison d’un événement aux périodes précédentes

Si vous souhaitez en savoir plus sur l’impact d’un événement sur vos données au fil du temps, vous pouvez utiliser la comparaison de dates dans Analysis Workspace. Cette fonctionnalité vous permet de comparer les données quotidiennement, hebdomadairement ou mensuellement pour comparer les données aux périodes précédentes. Vous pouvez ensuite utiliser cette comparaison pour déterminer l’ampleur de l’impact d’un événement sur les tendances. Consultez [Comparaison des dates affectées par un événement avec les périodes précédentes](compare-dates.md).

## Dérivation de données à l’aide de mesures calculées

Une fois que vous avez créé des segments et utilisé la comparaison de dates, vous pouvez combiner ces deux concepts pour corriger les données de tendances à l’aide de mesures calculées. Ajoutez les segments dans une mesure calculée, puis multipliez les jours concernés par le décalage trouvé lors de la comparaison des dates. Consultez [Dérivation de données affectées par les événements](calcmetrics.md).

## Communication de l’impact aux utilisateurs de votre entreprise

Une fois que vous êtes prêt à gérer un événement, vous pouvez [communiquer avec les utilisateurs de votre entreprise](communicate.md). Adobe offre plusieurs emplacements dans Analytics où vous pouvez placer du texte pour informer les utilisateurs de ce qui s’est passé et indiquer les composants qu’ils peuvent utiliser.

## Vidéo

>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analyser et communiquer les variations dans vos données](https://video.tv.adobe.com/v/33316?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

* **0:27** : exclure des données à l’aide de la segmentation
* **2:55** : comparaison d’un événement aux plages précédentes
* **8:42** : dérivation des données à l’aide de mesures calculées
* **11:46** : communiquer l’impact aux utilisateurs

>[!ENDSHADEBOX]


