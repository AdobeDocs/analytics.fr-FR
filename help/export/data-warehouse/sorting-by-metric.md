---
description: Fournit des rapports de répartition avec classement dans Data Warehouse, triés par valeurs de mesure décroissantes.
title: Tri par mesure
feature: Data Warehouse
exl-id: 6bd82951-c3b4-4ba2-8e4d-b7c9b351911b
source-git-commit: 42c95198a4d4389308c78c312b5bb37572350cc1
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 99%

---

# Tri par mesure

Fournit des rapports de répartition avec classement dans Data Warehouse, triés par valeurs de mesure décroissantes.

Le tri par mesure permet d’interpréter plus facilement les rapports de Data Warehouse. Il est aussi plus facile de comparer ces rapports à d’autres rapports de répartition des analyses.

Le tableau suivant présente la façon dont sont classées les lignes dans un rapport Data Warehouse une fois l’option Tri des mesures activée.

Les rapports Data Warehouse peuvent être triés par mesure de quatre différentes façons, selon la granularité de date, les dimensions de rapports, la configuration des mesures et si l’option Nombre max. de lignes est définie :

* **Disposition 1** : les éléments de ligne sont triés dans l’ordre du dictionnaire (par défaut). Si l’option Nombre max. de lignes est définie, seules les N premières lignes sont fournies dans le rapport.
* **Disposition 2** : Data Warehouse applique un tri des mesures par rapport à toutes les lignes du rapport. Les liens dans la valeur de la première mesure sont ventilés selon la 2e mesure, puis la 3e, etc. Si toutes les mesures sont liées, l’ordre standard du dictionnaire des éléments de ligne répartis s’applique.
* **Disposition 3** : identique à la Disposition 2, avec uniquement les N premières lignes (soit le nombre de lignes max. par défaut défini) apparaissant dans le rapport.
* **Disposition 4** : identique à la Disposition 2, à l’exception toutefois que les éléments de ligne pour chaque période de granularité de dates sont groupés et triés au sein de cet intervalle de temps respectif.

Reportez-vous à la colonne Disposition du rapport dans ce tableau pour déterminer de quelle façon le tri des mesures interagit avec d’autres options de génération de rapports de Data Warehouse.

| Tri par mesure ? | A des mesures ? | A des répartitions ? | Granularité des dates ? | Nb max. de lignes défini ? | Disposition du rapport |
|---|---|---|---|---|---|
| Non | Oui ou Non | Oui ou Non | Oui ou Non | Oui ou Non | 1 |
| Oui | Non | Oui ou Non | Oui ou Non | Oui ou Non | 1 |
| Oui | Oui | Non | Non | S.O. | 1 |
| Oui | Oui | Non | Oui ou Non | Non | 1 |
| Oui | Oui | Oui | Non | Non | 2 |
| Oui | Oui | Non | Oui | Oui | 3 |
| Oui | Oui | Oui | Oui ou Non | Oui | 3 |
| Oui | Oui | Oui | Oui | Non | 4 |
