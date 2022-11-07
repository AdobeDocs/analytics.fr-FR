---
title: Bonnes pratiques en matière dʼattribution
description: Quelles sont les bonnes pratiques pour décider dʼun modèle dʼattribution ?
feature: Attribution
exl-id: 92c6039c-f950-4746-8b34-ba18be258c08
source-git-commit: ac9e4934cee0178fb00e4201cc3444d333a74052
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 100%

---

# Bonnes pratiques en matière dʼattribution

Le choix du modèle dʼattribution approprié pour votre organisation dépend de plusieurs critères. Cet article explore une méthodologie et quelques bonnes pratiques générales.

## Étape 1 : analyse exploratoire

>[!NOTE]
>Cette analyse doit avoir lieu avant de choisir un modèle dʼattribution.

Cette phase consiste dʼabord à comprendre le comportement des clients et à définir des mesures de conversion. Selon les mesures de conversion, des outils tels que les [Flux de données](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=fr) (pour les données brutes) ou Analysis Workspace facilitent votre compréhension des questions suivantes :

* combien de clients empruntent plusieurs canaux marketing avant la conversion ?
* La proportion/répartition de ces comportements.

Par exemple, si 50 % des clients empruntent 3 canaux avant la conversion, y a-t-il une interaction entre ces 3 canaux ?
Vous pouvez ensuite effectuer une analyse des entonnoirs supérieur et inférieur afin dʼaméliorer votre compréhension.

### Analyse de lʼentonnoir supérieur

Lʼanalyse de lʼentonnoir supérieur étudie les canaux utilisés pour faire connaître la marque ou le produit. Par exemple, lʼobjectif de la plupart des publicités télévisées est de faire connaître la marque. Vous pouvez utiliser le [modèle dʼattribution « Décroissance temporelle »](/help/analyze/analysis-workspace/attribution/models.md), car les visiteurs oublieront votre publicité télévisée au fil du temps.

### Analyse de lʼentonnoir inférieur

Dans cette analyse, le postulat est que les gens connaissent déjà votre marque et que vous souhaitez passer à la conversion. Utilisez des notifications par e-mail ou push ou des publicités Facebook.

## Étape 2 : attribution basée sur les règles

Cette étape a pour but de valider vos hypothèses.

**Exemple 1**

Supposons que votre hypothèse soit la suivante : « Mon canal Première touche a plus dʼimpact sur la conversion que mon canal Dernière touche. » Vous choisirez alors le [modèle dʼattribution « En forme de J inversé »](/help/analyze/analysis-workspace/attribution/models.md) pour tester cette hypothèse. Ce modèle accorde 60 % du crédit au premier point de contact.

**Exemple 2**

Votre hypothèse peut être la suivante : « Dans notre secteur (tel que celui des voyages), lʼintervalle dʼattribution est de 60 ou 90 jours, et non de 30 jours, car les clients font beaucoup de recherches avant dʼacheter un produit. » Vous remplacerez ensuite lʼ[intervalle de recherche en amont](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html?lang=fr#lookback-windows) par 90 jours.

## Étape 3 : utilisation de lʼattribution algorithmique

Comme il est très difficile de valider un grand nombre dʼhypothèses et de combinaisons possibles, vous pouvez utiliser lʼ[attribution algorithmique](/help/analyze/analysis-workspace/attribution/algorithmic.md) pour laisser ce travail aux algorithmes intégrés. Si vous avez déjà trouvé le modèle dʼattribution idéal qui répond à toutes vos questions et besoins, alors vous nʼavez évidemment pas besoin de passer par cette étape.

## Autres considérations

* Il se peut que vous deviez faire appel aux services dʼun spécialiste des données au lieu de vous fier uniquement à Analysis Workspace.
* Vous pouvez vous fier aux données brutes, comme dans les flux de données Adobe.
* Envisagez dʼutiliser [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=fr), par exemple, si vous souhaitez prendre en compte vos données sur les Impressions.
