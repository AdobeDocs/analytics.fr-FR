---
title: Serveur
description: Le nom du serveur.
feature: Dimensions
exl-id: c2454c0d-497e-46f8-8569-7d0517097cab
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 92%

---

# Serveur

La dimension [Serveur](overview.md) répertorie généralement le nom d’hôte du site. Pour les suites de rapports combinant plusieurs domaines ou sous-domaines, cette dimension est utile pour identifier les domaines ou sous-domaines les plus performants.

Cette dimension est liée aux dimensions [Page](page.md) et [Section du site](site-section.md). Page est la dimension la plus granulaire, Serveur est la moins granulaire et Section du site est comprise entre les deux.

## Renseignement de cette dimension avec des données

Cette dimension récupère les données de la chaîne de requête [`server`](/help/implement/validate/query-parameters.md) dans les demandes d’image. AppMeasurement collecte ces données à l’aide de la variable [`server`](/help/implement/vars/page-vars/server.md).

## Éléments de dimension

Les éléments de dimension incluent les serveurs de votre site. Votre entreprise détermine les éléments de dimension spécifiques à utiliser. Certaines organisations utilisent `window.location.hostname`, tandis que d’autres formulent des valeurs personnalisées. Quelle que soit la méthode utilisée, assurez-vous qu’elle est cohérente et que vous l’enregistrez dans un [document de conception de solution](/help/implement/prepare/solution-design.md).
