---
title: Limitation d’une suite de rapports virtuelle à certaines dates
description: Comprenez comment limiter une plage de dates de la suite de rapports virtuelle pour vous concentrer uniquement sur les données assemblées.
translation-type: tm+mt
source-git-commit: 954927359420cfdb3d0e908758fc36464e15fee5
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 4%

---


# Limitation d’une suite de rapports virtuelle à certaines dates

Lorsque nous activons la couture, les débuts de couture sur une date spécifique. Supposons que la date soit le 1er juin. La SRV de l&#39;ADC contiendra des données non recoupées avant le 1er juin. Vous pouvez masquer les données de la suite de rapports virtuelle avant le 1er juin afin que votre analyse puisse se concentrer sur les plages de dates après le début de la sélection.

Vous pouvez limiter les données VRS à certaines dates en procédant comme suit :

## Étape 1 : Créer une suite de rapports virtuelle avec une plage de dates quotidienne variable

Lorsque vous configurez la suite de rapports virtuelle, sous Composants, ajoutez une plage de dates avec un début fixe, avec une plage de dates journalière variable. Le début fixe devrait être le jour où les coutures ont commencé.

![](assets/rolling-daily.png)

## Étape 2 : Création d’un segment d’exclusion

Créez ensuite un segment d’accès qui place la plage de dates dans un conteneur d’exclusion dans un autre conteneur d’exclusion. Il s’agit d’une exclusion.

La raison de l’exclusion est que les plages de dates sont destinées à remplacer la plage de dates du rapport. Ainsi, si vous incluez uniquement le 1er juin à l’avance, la plage de dates du rapport sera toujours reportée le 1er juin. Cela conduira à des résultats indésirables. Lorsque vous excluez l’exclusion, elle remplace ce comportement et limite simplement les données que vous pouvez extraire à la plage de dates appropriée.

![](assets/exclude-exclude.png)

## Étape 3 : Appliquer ce segment à votre suite de rapports virtuelle CDA

![](assets/apply-segment.png)

## Étape 4 : Afficher les résultats dans le rapports

Notez que le rapports début désormais à la date souhaitée, le jour même où l’assemblage a été mis en oeuvre pour la première fois :

![](assets/report-limited-dates.png)