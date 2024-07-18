---
title: Section du site
description: Nom de la section du site.
feature: Dimensions
exl-id: 349bace0-4596-4b4c-bf29-6cd8866c246b
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 90%

---

# Section du site

La [dimension](overview.md) de la &quot;section du site&quot; liste les noms des sections de votre site. Pour les sites volumineux, il est utile de regrouper les pages en sections. Cette dimension est utile pour afficher les sections du site les plus consultées ou les plus performantes.

Cette dimension est liée aux dimensions [Page](page.md) et [Serveur](server.md). Page est la dimension la plus granulaire, Serveur est la moins granulaire et Section du site est comprise entre les deux.

## Renseignement de cette dimension avec des données

Cette dimension récupère les données de la chaîne de requête [`ch`](/help/implement/validate/query-parameters.md) dans les demandes d’image. AppMeasurement collecte ces données à l’aide de la variable [`channel`](/help/implement/vars/page-vars/channel.md).

## Éléments de dimension

Les éléments de dimension incluent les noms des sections de votre site. Votre entreprise détermine les éléments de dimension spécifiques à utiliser. Quelle que soit la méthode utilisée, assurez-vous qu’elle est cohérente et que vous l’enregistrez dans un [document de conception de solution](/help/implement/prepare/solution-design.md).
