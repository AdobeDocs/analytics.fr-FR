---
title: Limiter une suite de rapports virtuelle à certaines dates
description: Découvrez comment limiter une période de suite de rapports virtuelle pour vous concentrer uniquement sur les données regroupées.
exl-id: 421d101d-8c64-47f7-b5a2-da039889f663
feature: CDA
role: Admin
source-git-commit: be5a73347d417c8dc6667d4059e7d46ef5f0f5cd
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 41%

---

# Limiter une suite de rapports virtuelle à certaines dates

Une fois lʼassemblage activé, il débute à une date précise. Supposons que la date soit le 1er juin. La suite de rapports virtuelle des analyses entre appareils contiendra des données désassemblées avant le 1er juin. Vous souhaiterez peut-être masquer les données de la suite de rapports virtuelle avant le 1er juin afin que votre analyse puisse se concentrer sur les périodes après le début du groupement.

Vous pouvez limiter les données de la suite de rapports virtuelle à certaines dates en procédant comme suit :

## Étape 1 : création d’une suite de rapports virtuelle avec une période variable quotidienne

Lorsque vous configurez la suite de rapports virtuelle, sous Composants, ajoutez une plage de dates avec un début fixe, avec une plage de dates quotidienne variable. Le début fixe devrait être le jour de début de lʼassemblage.

![](assets/rolling-daily.png)

## Étape 2 : créer un segment « exclure-exclure »

Créez ensuite un segment dʼaccès qui place la période dans un segment « exclure le conteneur » à lʼintérieur dʼun autre segment « exclure le conteneur ». C&#39;est un &quot;exclusion&quot;.

La raison de l’exclusion est que les plages de dates sont destinées à remplacer la plage de dates du rapport. Ainsi, si vous incluez uniquement les données à partir du 1er juin, la période du rapport sera toujours du 1er juin à la date actuelle. Cela conduira à des résultats indésirables. Lorsque vous &quot;excluez&quot;, cela remplace ce comportement et limite simplement les données que vous pouvez extraire à la période appropriée.

![](assets/exclude-exclude.png)

## Étape 3 : appliquez ce segment à votre suite de rapports virtuelle Analytics sur l’ensemble des appareils

![](assets/apply-segment.png)

## Étape 4 : afficher les résultats dans le compte rendu des performances

Remarquez que le compte rendu des performances débute désormais à la date souhaitée, le jour même où lʼassemblage a été mis en œuvre pour la première fois :

![](assets/report-limited-dates.png)
