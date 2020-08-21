---
title: Serveur
description: Le nom du serveur.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 85%

---


# Serveur

La dimension « Serveur » indique généralement le nom d’hôte du site. Pour les suites de rapports combinant plusieurs domaines ou sous-domaines, cette dimension est utile pour identifier les domaines ou sous-domaines les plus performants.

Cette dimension est liée aux dimensions [Page](page.md) et [Section du site](site-section.md). Page est la dimension la plus granulaire, Serveur est la moins granulaire et Section du site est comprise entre les deux.

## Renseignement de cette dimension avec des données

Cette dimension récupère les données de la [`server`chaîne de requête](/help/implement/validate/query-parameters.md) dans les demandes d’image. AppMeasurement collecte ces données à l’aide de la variable [`server`](/help/implement/vars/page-vars/server.md).

## Éléments de Dimension

Les éléments de Dimension incluent les serveurs de votre site. Votre organisation détermine les éléments de dimension spécifiques que vous souhaitez utiliser. Certaines organisations utilisent `window.location.hostname`, tandis que d’autres formulent des valeurs personnalisées. Quelle que soit la méthode utilisée, assurez-vous qu’elle est cohérente et que vous l’enregistrez dans un [document de conception de solution](/help/implement/prepare/solution-design.md).
