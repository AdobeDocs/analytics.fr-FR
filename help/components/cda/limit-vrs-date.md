---
title: Limiter une suite de rapports virtuelle à certaines dates
description: Découvrez comment limiter une période de suite de rapports virtuelle pour se concentrer uniquement sur les données assemblées.
exl-id: 421d101d-8c64-47f7-b5a2-da039889f663
feature: CDA
role: Admin
TQID: 'https://experienceleague.adobe.com/x7zHG4xkSr1yDLZ2dfosn5PaK4JVxiMWC6xksSTLypE'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: f99536a1-75c7-4151-a2c8-073630632526
    internal-label: CDA
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 41%
---
# Limiter une suite de rapports virtuelle à certaines dates

{{available-existing-customers}}

Une fois lʼassemblage activé, il débute à une date précise. Supposons que la date soit le 1er juin. La suite de rapports virtuelle des analyses entre appareils contiendra des données désassemblées avant le 1er juin. Vous pouvez masquer toutes les données de la suite de rapports virtuelle avant le 1er juin afin que votre analyse puisse se concentrer sur les périodes après le début du groupement.

Vous pouvez limiter les données de la suite de rapports virtuelle à certaines dates en procédant comme suit :

## Étape 1 : créer une suite de rapports virtuelle avec une période mobile quotidienne

Lorsque vous configurez la suite de rapports virtuelle, sous Composants, ajoutez une période dont le début est fixe, avec une période mobile quotidienne. Le début fixe devrait être le jour de début de lʼassemblage.

![](assets/rolling-daily.png)

## Étape 2 : créer un segment « exclure-exclure »

Créez ensuite un segment de hits qui place la période dans un conteneur dʼexclusion imbriqué dans un autre conteneur d’exclusion. C&#39;est une exclusion.

La raison de l’« exclusion » est que les périodes sont destinées à remplacer la période du rapport. Ainsi, si vous incluez uniquement les données à partir du 1er juin, la période du rapport sera toujours du 1er juin à la date actuelle. Cela conduira à des résultats indésirables. Lorsque vous « excluez, excluez », cela remplace ce comportement et limite simplement les données que vous pouvez extraire à la période appropriée.

![](assets/exclude-exclude.png)

## Étape 3 : appliquer ce segment à votre suite de rapports virtuelle Analytics sur l’ensemble des appareils

![](assets/apply-segment.png)

## Étape 4 : Consulter les résultats dans le reporting

Notez que le reporting commence désormais à la date souhaitée, le jour même où le rapprochement a été mis en œuvre pour la première fois :

![](assets/report-limited-dates.png)
