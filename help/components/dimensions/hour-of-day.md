---
title: Heure de la journée
description: Heure numérique de la journée, indépendamment du jour.
feature: Dimensions
exl-id: b9361534-7e58-41ed-9a38-c02aeed7a2d8
TQID: https://experienceleague.adobe.com/cktusukSxy7fHIIUi-7MSmx8Gl9FlUObfmJGS3VC3Jw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 69%
---
# Heure de la journée

La [dimension](overview.md) « Heure du jour » indique l’heure numérique d’un jour donné en tant qu’élément de dimension. Par exemple, si vous disposez d’un rapport qui s’étend du 1er au 7 janvier, la première heure de chaque jour est regroupée dans le même élément de dimension. Ce rapport est utile si vous souhaitez un rapport divisé par heure de la journée, mais ne souhaitez pas d’heures statiques comme éléments de dimension. Il s’avère particulièrement utile comme dimension dans les rapports planifiés, dans la mesure où cette dimension s’étend sur la période sélectionnée.

Cette dimension est basée sur le fuseau horaire de la suite de rapports, et non sur celui du visiteur. Par exemple, si votre suite de rapports est en heure des Rocheuses et qu’un visiteur en Californie visite votre site à 10 h, heure du Pacifique, les accès sont regroupés sous l’élément de dimension `11:00 AM` . Si vous souhaitez une dimension qui enregistre l’heure locale du visiteur, Adobe recommande d’utiliser le plug-in [getTimeParting](/help/implement/vars/plugins/gettimeparting.md).

## Renseignement de cette dimension avec des données

Cette dimension est dérivée de la date et de l’heure de chaque accès ; il n’y a aucune variable à définir. Comme indiqué ci-dessus, l’heure reflète le fuseau horaire de la suite de rapports plutôt que le fuseau horaire local du visiteur.

| Propriété | Valeur |
| --- | --- |
| **Variable** | Aucune (dérivée de la date et heure de l’accès) |
| **Champ Web SDK/XDM** | Aucune (dérivée de la date et heure de l’accès) |
| **Paramètre de requête** | S.O. |
| **Balise XML** | S.O. |
| **Limite d’octets** | S.O. |
| **Persistance** | Hit |

## Éléments de dimension

Les éléments de dimension vont de `12:00 AM` à `11:00 PM`, ce qui représente l’heure de la journée où le hit a eu lieu (arrondie à l’unité inférieure). Par exemple, si un accès a été généré à 15h58, il est regroupé sous l’élément de dimension `3:00 PM`.

## Heure d’été

L’heure d’été est une pratique qui consiste à avancer les horloges d’une heure au printemps et à les reculer d’une heure à l’automne. Si le fuseau horaire d’une suite de rapports utilise l’heure d’été, Adobe adapte les données en fonction de cette heure.

* **Début de l’heure d’été** : en mars, les rapports indiquent généralement un décalage d’une heure dans les données au début de l’heure d’été. L’heure n’existe pas, elle ne fait donc pas partie de la collecte de données. Notez qu’une petite quantité de données peut encore se trouver dans cette heure. Les serveurs de collecte de données d’Adobe prennent plusieurs secondes (jusqu’à une minute) pour tenir compte des ajustements à l’heure d’été.
* **Fin de l’heure d’été** : en novembre, les rapports indiquent généralement une heure doublée à la fin de l’heure d’été. L’heure apparaissant deux fois, les deux heures sont agrégées dans les rapports.
