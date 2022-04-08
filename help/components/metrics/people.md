---
title: Personnes
description: Nombre de personnes uniques, généralement avec plusieurs appareils.
feature: Metrics
exl-id: 0136b843-2a1e-44d5-b5a6-e0fb03b7b995
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: ht
source-wordcount: '161'
ht-degree: 100%

---

# Personnes

Il existe deux versions de la mesure « Personnes ».

Pour les membres de [Device Co-op](https://experienceleague.adobe.com/docs/device-co-op/using/data/people.html?lang=fr) qui nʼutilisent pas [les analyses entre appareils](../cda/overview.md), la mesure « Personnes » est un décompte statistique du nombre de personnes représentées dans le rapport. Il sʼagit du nombre dʼidentifiants de visiteurs qui sont identifiés par Device Co-op plus le nombre dʼappareils qui ne sont pas identifiés par Co-op.

Dans une suite de rapports virtuelle [Analyses entre appareils](../cda/overview.md), la mesure « Personnes » n’est pas une dérivation statistique. Les personnes constituent la somme des individus qui ont été identifiés dans le rapport, plus le nombre dʼappareils qui nʼont pas été identifiés comme appartenant à une personne.

Si un visiteur est identifié en cours de visite, il peut compter comme 2 personnes (1 personne non identifiée et 1 personne identifiée). La [Relecture](/help/components/cda/replay.md) atténue ce double comptage en fonction de lʼintervalle du compte rendu des performances, de la fréquence de relecture et du taux de réussite. Voir [Appareils uniques](unique-devices.md) pour plus d’informations.
