---
title: Section du site
description: Nom de la section du site.
exl-id: 349bace0-4596-4b4c-bf29-6cd8866c246b
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '137'
ht-degree: 100%

---

# Section du site

La dimension « Section du site » liste les noms des sections de votre site. Pour les sites volumineux, il est utile de regrouper les pages en sections. Cette dimension est utile pour afficher les sections du site les plus consultées ou les plus performantes.

Cette dimension est liée aux dimensions [Page](page.md) et [Serveur](server.md). Page est la dimension la plus granulaire, Serveur est la moins granulaire et Section du site est comprise entre les deux.

## Renseignement de cette dimension avec des données

Cette dimension récupère les données de la [`ch`chaîne de requête](/help/implement/validate/query-parameters.md) dans les demandes d’image. AppMeasurement collecte ces données à l’aide de la variable [`channel`](/help/implement/vars/page-vars/channel.md).

## Éléments de dimension

Les éléments de dimension incluent les noms des sections de votre site. Votre entreprise détermine les éléments de dimension spécifiques à utiliser. Quelle que soit la méthode utilisée, assurez-vous qu’elle est cohérente et que vous l’enregistrez dans un [document de conception de solution](/help/implement/prepare/solution-design.md).
