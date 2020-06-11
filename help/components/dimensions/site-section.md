---
title: Section du site
description: Nom de la section du site.
translation-type: tm+mt
source-git-commit: 1869d69566d26aa7d99c520efc2e835901439d48
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 0%

---


# Section du site

La dimension &quot;Section du site&quot; liste les noms des sections du site. Pour les sites volumineux, il est utile de regrouper les pages en sections. Cette dimension est utile pour afficher les sections du site les plus consultées ou les plus performantes.

Cette dimension est liée aux dimensions [Page](page.md) et [Serveur](server.md) . La page est la plus granulaire, le serveur est la moins granulaire et la section du site est comprise entre les deux.

## Renseigner cette dimension avec des données

Cette dimension récupère les données de la chaîne [`ch` de](/help/implement/validate/query-parameters.md) requête dans les demandes d’image. AppMeasurement collecte ces données à l’aide de la [`channel`](/help/implement/vars/page-vars/channel.md) variable.

## Valeurs de dimension

Les valeurs de dimension incluent les noms des sections du site. Votre organisation détermine les valeurs de dimension spécifiques que vous souhaitez utiliser. Quelle que soit la méthode utilisée, assurez-vous qu’elle est cohérente et que vous l’enregistrez dans un document [de conception de](/help/implement/prepare/solution-design.md)solution.
