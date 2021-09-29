---
title: Personnes
description: Nombre de personnes uniques, généralement avec plusieurs appareils.
exl-id: 0136b843-2a1e-44d5-b5a6-e0fb03b7b995
source-git-commit: 639897682c9a28df7dc642dd7c68ad992fde40a9
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 49%

---

# Personnes

Il existe deux versions de la mesure « Personnes ».

Pour les membres de [Device Co-op](https://experienceleague.adobe.com/docs/device-co-op/using/data/people.html?lang=fr) qui nʼutilisent pas [les analyses entre appareils](../cda/overview.md), la mesure « Personnes » est un décompte statistique du nombre de personnes représentées dans le rapport. Il sʼagit du nombre dʼidentifiants de visiteurs qui sont identifiés par Device Co-op plus le nombre dʼappareils qui ne sont pas identifiés par Co-op.

Dans une suite de rapports virtuelle [Analyses entre appareils](../cda/overview.md), la mesure &quot;Personnes&quot; n’est pas une dérivation statistique. Il s’agit plutôt de la somme des individus identifiés dans le rapport, plus le nombre de périphériques qui ne sont pas identifiés comme appartenant à une personne.

Si un visiteur est identifié en cours de visite, il peut compter comme 2 personnes (1 personne non identifiée et 1 personne identifiée). [](/help/components/cda/replay.md) Les lectures atténuent ce double comptage en fonction de la fenêtre de rapport, de la fréquence de relecture et du taux de succès. Voir [Appareils uniques](unique-devices.md) pour plus d’informations.
