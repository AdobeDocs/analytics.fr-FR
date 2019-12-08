---
description: Procédure de préparation à l’utilisation des sources de données
subtopic: Data sources
title: Préparation à l’utilisation des sources de données
topic: Developer and implementation
uuid: 876ea069-574b-4e23-93b7-e3828bfd90f5
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Préparation à l’utilisation des sources de données

Procédure de préparation à l’utilisation des sources de données

* [Identification des mesures et attribution de nouveaux noms](/help/import/c-data-sources/datasrc-preparing.md#section_0D1DA6D7768E4C4CB6E9A2F4639C0135)
* [Identification de la portée des données](/help/import/c-data-sources/datasrc-preparing.md#section_8EC6BDC4AA314D9EB85F6FCD8E6ABC0A)
* [Code de suivi de campagne](/help/import/c-data-sources/datasrc-preparing.md#section_468222796FF449ABAA90D88EB3264CB1)
* [ID de transaction](/help/import/c-data-sources/datasrc-preparing.md#section_D9513C1204B7496C9B738C5B12CCCFC7)
* [Identification d’une plage de dates valide pour des données de source de données](/help/import/c-data-sources/datasrc-preparing.md#section_03AAB1291BDC4403BDC50905A78FDB71)

## Identification des mesures et attribution de nouveaux noms {#section_0D1DA6D7768E4C4CB6E9A2F4639C0135}

It is important to understand the metrics or measurements that are contained in your data sources, such as *`Off-line Sales Revenue by Product`*, *`Returns by Product`*, or *`Ad Impressions by Campaign`*. Il s’agit des noms que vous pouvez associer aux mesures des rapports (événements, props et eVar).

Une fois les associations appropriées de mesure/événement déterminées pour les données des sources de données, renommez les événements à l’aide de noms explicites correspondant à la mesure concernée.

Voir [Événements de succès](https://marketing.adobe.com/resources/help/en_US/reference/success_event.html) dans l’aide des outils d’administration.

> [!NOTE] Adobe recommande vivement d’utiliser de nouveaux événements vides avec des données de source de données, mais dans de rares cas, il peut s’avérer judicieux d’utiliser un événement préexistant.

## Identification de la portée des données {#section_8EC6BDC4AA314D9EB85F6FCD8E6ABC0A}

Identifiez et rassemblez les données (rapports) que vous souhaitez utiliser pour ventiler les mesures importées au moyen des sources de données. On parle alors de *`data dimensions`*.

Si, par exemple, une mesure de source de donnée évalue les impressions de publicité, votre portée de données est sans doute le code de suivi de campagne. Si vous mesurez les ventes hors ligne, vous pouvez utiliser le code de produit (unité de gestion des stocks) comme portée de données.

Vous pouvez définir plusieurs portées de données pour une mesure ; toutefois, chaque mesure doit fournir une valeur ou combinaison de valeurs appropriée, pour chaque portée de données associée. Si, par exemple, vous importez une mesure Ventes hors ligne et l’associez aux portées de données *`Product`* and *`Partner`* data dimensions, the Off-line Sales metric must be relevant for each combination of product and partner (for example, Total Revenue).

> [!NOTE] Il est possible d’importer les mesures totales qui ne peuvent pas être ventilées par dimension de données.

Après avoir défini les portées de données à utiliser avec une source de données, intégrez les données des portées aux rapports marketing en les faisant correspondre à une variable. Utilisez les rapports standard (par exemple, Produit, Code de suivi, Mot-clé de recherche) ou les variables de conversion Trafic (eVars).

Lors de l’utilisation d’eVar, vous pouvez utiliser comme portées de données des eVar existantes ou nouvelles. Après avoir sélectionné une eVar pour recevoir une portée de données à partir des sources de données, veillez à la nommer de façon appropriée.

Voir [Événements de succès](https://marketing.adobe.com/resources/help/en_US/reference/success_event.html) dans l’aide d’Analytics.

## Code de suivi de campagne {#section_468222796FF449ABAA90D88EB3264CB1}

Outre l’importation d’événements de succès, vous pouvez également importer des valeurs d’eVar associées. Si, par exemple, vous effectuez un suivi sur l’activité en ligne avec un code de suivi de campagne et que vous détenez des codes de suivi de campagne pour les mesures hors ligne, vous pouvez importer les mesures à l’aide de codes de suivi de campagne. Cette approche vous permet ainsi d’afficher les mesures en ligne et hors ligne dans les rapports de campagne.

Si vous n’importez pas les mesures de sources de données avec une valeur d’eVar associée, vous ne pourrez pas afficher les mesures ventilées par eVar ; vous pourrez uniquement afficher les mesures de totaux.

## ID de transaction {#section_D9513C1204B7496C9B738C5B12CCCFC7}

L’ID de transaction permet de connecter un événement en ligne à un événement hors ligne.

## Identification d’une plage de dates valide pour des données de source de données {#section_03AAB1291BDC4403BDC50905A78FDB71}

Une fois définies vos mesures de sources de données (événements personnalisés) et vos portées de données (eVars), passez en revue la plage de dates des données de sources de données à importer. Vous ne pouvez pas importer des sources de données qui se situent en dehors de la plage de vos données de rapport existantes.

Par exemple, vous ne pouvez pas importer des données de sources de données qui existaient avant que vous n’ayez mis en place le suivi de données en ligne. Les données de sources de données doivent être ventilées par jour.
