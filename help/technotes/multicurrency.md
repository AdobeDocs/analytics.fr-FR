---
description: Décrit comment définir des codes de devise cible pour permettre une prise en charge multidevise.
title: Prise en charge multidevise
feature: Analytics Basics
exl-id: b67f459c-0636-4eac-af52-51846bb583b5
source-git-commit: f659d1bde361550928528c7f2a70531e3ac88047
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 10%

---

# Prise en charge multidevise

Adobe offre plusieurs niveaux de conversion de devise afin que votre entreprise puisse obtenir la devise souhaitée dans de nombreux rapports. La conversion se produit à trois niveaux :

## Niveau de page

Vous pouvez utiliser la variable [`currencyCode`](/help/implement/vars/config-vars/currencycode.md) pour définir la devise souhaitée sur chaque page. Si la devise de la page ne correspond pas à la devise de la suite de rapports de destination, Adobe effectue une conversion de devise vers la devise de la suite de rapports en fonction du taux de change du jour en cours. La devise convertie est enregistrée.

## Niveau de la suite de rapports

Chaque suite de rapports comporte une **monnaie de base**. Cette devise détermine le contexte de toutes les mesures monétaires (telles que [Recettes](/help/components/metrics/revenue.md)). Toutes les données de devise stockées se trouvent dans la devise de base de la suite de rapports.

## Niveau d’utilisateur

Pour Reports &amp; Analytics, les utilisateurs peuvent définir une devise différente de la devise de base de la suite de rapports sous [Paramètres des rapports](/help/analyze/reports-analytics/report-settings.md). Ce paramètre est non destructif, ce qui signifie qu’il ne modifie pas les données sous-jacentes. Il applique plutôt une conversion de devise de base à tous les rapports consultés en fonction du taux de change actuel. Si vous affichez le même rapport sur des jours différents, les chiffres peuvent changer en raison de taux de change quotidiens différents.

Analysis Workspace ne propose actuellement pas de conversion de devise au niveau de l’utilisateur.
