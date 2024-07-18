---
title: Bonnes pratiques en matière dʼattribution
description: Quelles sont les bonnes pratiques pour décider dʼun modèle dʼattribution ?
feature: Attribution
exl-id: 92c6039c-f950-4746-8b34-ba18be258c08
source-git-commit: ce7f953b8f7f1f7d0616074454e4401937fcc0c7
workflow-type: tm+mt
source-wordcount: '415'
ht-degree: 100%

---

# Bonnes pratiques en matière dʼattribution

Le choix du modèle dʼattribution approprié pour votre organisation dépend de plusieurs critères. Cet article explore une méthodologie et quelques bonnes pratiques générales.

## Étape 1 : analyse exploratoire

>[!NOTE]
>Cette analyse doit avoir lieu avant de choisir un modèle dʼattribution.

Cette phase consiste dʼabord à comprendre le comportement des clients et à définir des mesures de conversion. Selon les mesures de conversion, des outils tels que les [Flux de données](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=fr) (pour les données brutes) ou Analysis Workspace facilitent votre compréhension des questions suivantes :

* Le nombre de clientes et clients qui touchent différents canaux marketing avant la conversion.
* La proportion ou répartition de ces comportements.

Par exemple, si 50 % des clients empruntent 3 canaux avant la conversion, y a-t-il une interaction entre ces 3 canaux ?
Vous pouvez ensuite effectuer une analyse des entonnoirs supérieur et inférieur afin dʼaméliorer votre compréhension.

### Analyse de lʼentonnoir supérieur

Les analyses en entonnoir supérieur étudient les canaux utilisés pour faire connaître la marque ou le produit. Par exemple, lʼobjectif de la plupart des publicités télévisées est de faire connaître la marque. Vous pouvez utiliser le [modèle dʼattribution « Décroissance temporelle »](/help/analyze/analysis-workspace/attribution/models.md), car les visiteurs oublieront votre publicité télévisée au fil du temps.

### Analyse de lʼentonnoir inférieur

Dans l’analyse en entonnoir inférieur, le postulat est que les personnes connaissent déjà votre marque et que vous souhaitez qu’elles effectuent une conversion. Utilisez des e-mails, des notifications push ou des annonces Facebook.

## Étape 2 : attribution basée sur les règles

Cette étape a pour but de valider vos hypothèses.

**Exemple 1**

Supposons que votre hypothèse soit la suivante : « mon canal Première touche a plus dʼimpact sur la conversion que mon canal Dernière touche ».

Vous choisirez alors le [modèle dʼattribution « en forme de J inversé »](/help/analyze/analysis-workspace/attribution/models.md) pour tester cette hypothèse. Ce modèle accorde 60 % du crédit au premier point de contact.

**Exemple 2**

Supposons que votre hypothèse soit la suivante : « dans notre secteur (par exemple, celui du tourisme), la fenêtre d’attribution est de 60 ou 90 jours et non de 30 jours, car les clientes et clients font beaucoup de recherches avant d’acheter un produit ».

Dans ce cas, vous pouvez modifier votre [intervalle de recherche en amont](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html?lang=fr#lookback-windows) à 90 jours.

## Étape 3 : utilisation de lʼattribution algorithmique

Si vous ne disposez pas encore d’un modèle d’attribution qui fournit des réponses satisfaisantes à toutes vos questions, vous pouvez utiliser l’[attribution algorithmique](/help/analyze/analysis-workspace/attribution/algorithmic.md). Comme il est très difficile de valider un grand nombre d’hypothèses et de combinaisons possibles, l’attribution algorithmique utilise des algorithmes intégrés pour répartir le crédit entre les éléments de dimension.

## Autres considérations

* Il se peut que vous deviez faire appel aux services dʼun spécialiste des données au lieu de vous fier uniquement à Analysis Workspace.
* Vous pouvez vous fier aux données brutes, comme dans les flux de données Adobe.
* Envisagez dʼutiliser [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=fr), par exemple, si vous souhaitez prendre en compte vos données sur les Impressions.
