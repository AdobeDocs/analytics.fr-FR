---
description: Décrit comment définir des codes de devise cible pour permettre une prise en charge multidevise.
title: Prise en charge multidevise
feature: Analytics Basics
exl-id: b67f459c-0636-4eac-af52-51846bb583b5
TQID: https://experienceleague.adobe.com/-t0JAIvbmUmzTCTznOWcjVmvtJbmQNV5MIrbQBvhv6M
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: a421fb65-2c82-457a-921c-28c46b697a39
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 127
ht-degree: 18%

---

# Prise en charge multidevise

Adobe propose plusieurs niveaux de conversion de devise afin que votre entreprise puisse atteindre la devise souhaitée dans de nombreux rapports. La conversion se produit à trois niveaux :

## Niveau de page

Vous pouvez utiliser la variable [`currencyCode`](/help/implement/vars/config-vars/currencycode.md) pour définir la devise souhaitée sur chaque page. Si la devise sur la page ne correspond pas à la devise de la suite de rapports de destination, Adobe effectue une conversion de devise dans la devise de la suite de rapports en fonction du taux de change du jour en cours. La devise convertie est enregistrée.

## Niveau de la suite de rapports

Chaque suite de rapports a une **devise de base**. Cette devise détermine le contexte de toutes les mesures de devise (telles que [Chiffre d’affaires](/help/components/metrics/revenue.md)). Toutes les données de devise stockées sont dans la devise de base de la suite de rapports.

