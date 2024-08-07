---
description: Décrit comment définir des codes de devise cible pour permettre une prise en charge multidevise.
title: Prise en charge multidevise
feature: Analytics Basics
exl-id: b67f459c-0636-4eac-af52-51846bb583b5
source-git-commit: 99156dd9d898ce0abf214561cb0040c647d7e6ab
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 16%

---

# Prise en charge multidevise

Adobe offre plusieurs niveaux de conversion de devise afin que votre entreprise puisse obtenir la devise souhaitée dans de nombreux rapports. La conversion se produit à trois niveaux :

## Niveau de page

Vous pouvez utiliser la variable [`currencyCode`](/help/implement/vars/config-vars/currencycode.md) pour définir la devise souhaitée sur chaque page. Si la devise de la page ne correspond pas à la devise de la suite de rapports de destination, Adobe effectue une conversion de devise vers la devise de la suite de rapports en fonction du taux d’exchange du jour en cours. La devise convertie est enregistrée.

## Niveau de la suite de rapports

Chaque suite de rapports possède une **devise de base**. Cette devise détermine le contexte de toutes les mesures de devise (telles que [Recettes](/help/components/metrics/revenue.md)). Toutes les données de devise stockées se trouvent dans la devise de base de la suite de rapports.

