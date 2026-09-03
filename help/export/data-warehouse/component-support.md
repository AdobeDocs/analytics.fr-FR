---
title: Prise en charge des composants dans Data Warehouse
description: Découvrez les dimensions et mesures disponibles lorsque vous créez une requête Data Warehouse, celles qui ne sont pas disponibles et celles qui se comportent différemment.
feature: Data Warehouse
exl-id: ce7411a4-a720-47b7-90d5-4d867eff4bae
TQID: https://experienceleague.adobe.com/NhSEyPN3093B9M0SngJluJdZScI2lXvRyHkXQd8gg-4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 362
ht-degree: 11%

---

# Prise en charge des composants dans Data Warehouse

Cette page décrit les dimensions et les mesures que vous pouvez utiliser lors de la création d’une requête Data Warehouse. Les sections incluent les composants disponibles, indisponibles et qui se comportent différemment des autres outils Adobe Analytics.

## Dimensions exclusives à Data Warehouse

Les dimensions suivantes peuvent être utilisées dans Data Warehouse, mais ne sont pas disponibles dans les autres fonctionnalités d’Adobe Analytics.

* [[!UICONTROL Identifiant visiteur Experience Cloud]](/help/components/dimensions/experience-cloud-visitor-id.md)
* [[!UICONTROL Adresse IP]](/help/components/dimensions/ip-address.md)
* [[!UICONTROL URL de la page]](/help/components/dimensions/page-url.md)
* [[!UICONTROL ID d’achat]](/help/components/dimensions/purchase-id.md)
* [[!UICONTROL Identifiant visiteur]](/help/components/dimensions/visitor-id.md)

## Dimensions non prises en charge

Les dimensions suivantes ne sont pas disponibles dans les segments ou les rapports Data Warehouse :

* [[!UICONTROL Matin/après-midi]](/help/components/dimensions/am-pm.md)
* Toutes les dimensions d’entrée, à l’exception de [[!UICONTROL Page d’entrée]](/help/components/dimensions/entry-dimensions.md) et [[!UICONTROL Page d’entrée d’origine]](/help/components/dimensions/entry-dimensions.md) qui sont autorisées
* Toutes les dimensions de sortie, à l’exception de [[!UICONTROL Page de sortie]](/help/components/dimensions/exit-dimensions.md) et [[!UICONTROL Lien de sortie]](/help/components/dimensions/exit-link.md) qui sont autorisées.
* [[!UICONTROL Profondeur d’accès]](/help/components/dimensions/hit-depth.md)
* [[!UICONTROL Fréquence des retours]](/help/components/dimensions/return-frequency.md)
* [[!UICONTROL Durée avant événement]](/help/components/dimensions/time-prior-to-event.md)
* [[!UICONTROL Durée de consultation de la page - Regroupement]](/help/components/dimensions/time-spent-on-page.md)
* [[!UICONTROL Durée par visite - Regroupement]](/help/components/dimensions/time-spent-per-visit.md)
* [[!UICONTROL Classement de toutes les pages de recherche]](/help/components/dimensions/all-search-page-rank.md)
* Variables [[!UICONTROL Hiérarchie]](/help/components/dimensions/overview.md#retired-dimensions)
* [[!UICONTROL Type d’accès]](/help/components/dimensions/hit-type.md)
* [[!UICONTROL Recherche payante]](/help/components/dimensions/paid-search.md)
* [[!UICONTROL Visites de page unique]](/help/components/dimensions/single-page-visits.md)
* [[!UICONTROL Suivi du motif de désinscription]](/help/components/dimensions/tracking-opt-out-reason.md)
* [[!UICONTROL  États américains ]](/help/components/dimensions/us-states.md)

Certaines dimensions sont disponibles dans une requête Data Warehouse, mais ne peuvent pas être utilisées dans un segment. Voir [Compatibilité des segments ](segment-compatibility.md) pour plus d’informations.

## Dimensions avec un formatage de date non standard

Les dimensions temporelles suivantes sont prises en charge dans les rapports Data Warehouse, mais leur sortie utilise un format non standard :

* [[!UICONTROL Année]](/help/components/dimensions/year.md)
* [[!UICONTROL Trimestre]](/help/components/dimensions/quarter.md)
* [[!UICONTROL Mois]](/help/components/dimensions/month.md)
* [[!UICONTROL Semaine]](/help/components/dimensions/week.md)
* [[!UICONTROL Jour]](/help/components/dimensions/day.md)
* [[!UICONTROL Heure]](/help/components/dimensions/hour.md)
* [[!UICONTROL Minute]](/help/components/dimensions/minute.md)

Les valeurs de date sont générées au format `1YYMMDDHHMM` :

* **Année (AA)** : Décalage par 1900. Ajoutez `1900` aux trois premiers chiffres. Par exemple, `125` = année **2025**.
* **Month** : basé sur zéro. Janvier = `00`, février = `01`, ..., décembre = `11`.

Par exemple, si le champ Semaine de la période affiche `1260901`, l’année est 1900 + 126 = **2026** et le mois est 09 = **Octobre**.

## Mesures définies différemment dans Data Warehouse

* **[[!UICONTROL Visites]](/help/components/metrics/visits.md)** : exclut les visites de cookies non persistants, contrairement à la mesure Visites dans d’autres outils Adobe Analytics.
* **[[!UICONTROL Visites - Tous les visiteurs]](/help/components/metrics/visits.md)** : compte tous les visiteurs, y compris ceux qui disposent de cookies non persistants, ce qui en fait l’équivalent le plus proche de la mesure standard [!UICONTROL Visites] utilisée ailleurs dans Adobe Analytics.

## Mesures non prises en charge

Les mesures suivantes ne sont pas disponibles dans Data Warehouse :

* [[!UICONTROL Rebonds]](/help/components/metrics/bounces.md)
* [[!UICONTROL Entrées]](/help/components/metrics/entries.md)
* [[!UICONTROL Sorties]](/help/components/metrics/exits.md)
* [[!UICONTROL Actualisations]](/help/components/metrics/reloads.md)
* [[!UICONTROL Accès unique]](/help/components/metrics/single-access.md)
* Mesures [[!UICONTROL Temps passé]](/help/components/metrics/time-spent.md)
* Toutes les mesures utilisant un modèle d’attribution [participation](/help/components/calculated-metrics/workflow/c-build-metrics/participation-metric.md)
