---
title: Analyse des données affectées par les événements
description: Comprendre comment les données affectées par un événement contribuent à la qualité générale des données.
exl-id: 8d81a432-42d6-4f5d-b66a-bb3af7fc4857
feature: Curate and Share
source-git-commit: 29ab0cc535bd8f74b50428c11756bf8b446a23ab
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 90%

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


