---
title: Section du site
description: Nom de la section du site.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 0%

---


# Section du site

La dimension &quot;Section du site&quot; liste les noms des sections du site. Pour les sites volumineux, il est utile de regrouper les pages en sections. Cette dimension est utile pour afficher les sections du site les plus consultées ou les plus performantes.

Cette dimension est liée aux dimensions [Page](page.md) et [Serveur](server.md) . La page est la plus granulaire, le serveur est la moins granulaire et la section du site est comprise entre les deux.

## Renseigner cette dimension avec des données

Cette dimension récupère les données de la chaîne [`ch` de](/help/implement/validate/query-parameters.md) requête dans les demandes d’image. AppMeasurement collecte ces données à l’aide de la [`channel`](/help/implement/vars/page-vars/channel.md) variable.

## Éléments de dimension

Les éléments de dimension incluent les noms des sections du site. Votre organisation détermine les éléments de dimension spécifiques que vous souhaitez utiliser. Quelle que soit la méthode utilisée, assurez-vous qu’elle est cohérente et que vous l’enregistrez dans un document [de conception de](/help/implement/prepare/solution-design.md)solution.
