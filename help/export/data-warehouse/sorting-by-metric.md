---
description: Découvrez comment le tri par mesure facilite l’interprétation des rapports Data Warehouse et leur comparaison avec d’autres vues de rapports de répartition Analytics.
title: Tri par mesure
feature: Data Warehouse
exl-id: 6bd82951-c3b4-4ba2-8e4d-b7c9b351911b
TQID: 'https://experienceleague.adobe.com/YPqL6i9RWACubLdf2ywm8xuPyeQkZ30L6rO6FAbhpJI'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2: id: f47edbe0-f963-46ff-a667-71011396f5f3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 337
ht-degree: 92%

---

# Trier par mesure

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
