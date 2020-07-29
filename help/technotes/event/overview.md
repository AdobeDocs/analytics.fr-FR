---
title: Analyse des données affectées par les événements
description: Comprendre comment les données affectées par un événement contribuent à la qualité générale des données.
translation-type: tm+mt
source-git-commit: 178e372e63c436268a1f7028d986504983430b2f
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 3%

---


# Analyse des données affectées par les événements

Il arrive qu’un événement ait un impact sur la qualité des données de votre entreprise. Par exemple :

* Un robot qui envoie des données plus rares, telles que des millions de dollars de recettes
* Votre organisation a mis à jour votre site Web afin d’avoir un impact négatif sur votre mise en oeuvre Analytics.
* Autres problèmes affectant la qualité ou l&#39;exhaustivité des données

Si votre site a rencontré un problème de qualité des données, vous pouvez l’exclure du rapports afin d’éviter de prendre des décisions commerciales à son sujet. Utilisez ces sections pour évaluer l&#39;impact du événement sur vos données et déterminer comment procéder.

## Détermination de la cause d’un événement

Si vous n’êtes pas sûr de la raison pour laquelle vous constatez un pic ou une baisse des données, voir [Dépannage des pics/des pertes de données](spikes-drops.md).

## Analyser et exclure des données à l’aide de la segmentation

Adobe Analytics offre une méthode simple et robuste pour cibler ou exclure les données à l’aide de la segmentation. Vous pouvez utiliser les dimensions de plage de dates dans les segments pour filtrer ou vous concentrer sur ces dates spécifiques. See [Exclude specific dates in analysis](segments.md).

## Comparer un événement aux plages de dates précédentes

Si vous souhaitez en savoir plus sur l’impact d’un événement sur vos données au fil du temps, vous pouvez utiliser la comparaison de dates dans l’Analysis Workspace. Cette fonctionnalité vous permet de comparer les données jour par jour, semaine par semaine ou mois par mois pour comparer les données aux plages précédentes. Vous pouvez ensuite utiliser cette comparaison pour déterminer dans quelle mesure un événement affecte les tendances. Voir [Comparer les dates affectées par un événement aux plages](compare-dates.md)précédentes.

## Dériver des données à l’aide de mesures calculées

Une fois que vous avez créé des segments et utilisé la comparaison de dates, vous pouvez combiner ces deux concepts pour corriger les données de tendance à l’aide de mesures calculées. Incluez les segments dans une mesure calculée, puis multipliez les jours affectés par le décalage trouvé lors de la comparaison des dates. See [Derive data impacted by events](calcmetrics.md).

## Communiquer l’impact sur les utilisateurs de votre entreprise

Une fois que vous êtes prêt à gérer un événement, vous pouvez [communiquer avec les utilisateurs de votre organisation](communicate.md). Adobe offre plusieurs endroits dans Analytics où vous pouvez placer du texte pour communiquer aux utilisateurs ce qui s&#39;est passé et quels composants ils peuvent utiliser.

## Vidéo

Cette vidéo présente chacune des étapes ci-dessus.

>[!VIDEO](https://video.tv.adobe.com/v/33316?quality=12)

* **0:27**: Exclure des données à l’aide de la segmentation
* **02:55**: Comparaison d’un événement avec des plages précédentes
* **8:42**: Dériver des données à l’aide de mesures calculées
* **11:46**: Communiquer l’impact aux utilisateurs
