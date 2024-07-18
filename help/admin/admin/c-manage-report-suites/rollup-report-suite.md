---
description: Description des suites de rapports globales
title: Suites de rapports globales
feature: Report Suite Settings
exl-id: 97bdc9bd-2212-436b-b3b4-ec518624f9e6
role: Admin
source-git-commit: 938795c7378cb1f0537ff84eddeab3feddf8d073
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 100%

---

# Suites de rapports globales

Une suite de rapports globale collecte des données de tous les domaines et applications dont votre organisation est propriétaire. Elle nécessite une implémentation pour envoyer toutes les demandes d’image à une seule suite de rapports.

Dans la plupart des cas, Adobe recommande dʼimplémenter une suite de rapports globale. Consultez la section « [Considérations relatives aux suites de rapports globales](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/global-rs.html?lang=fr) » pour découvrir les avantages offerts par lʼimplémentation d’une suite de rapports globale.

Vous pouvez fournir des sous-ensembles de données de la suite de rapports globale de votre société à différents utilisateurs finaux à l’aide des approches *balisage multisuite* et *suite de rapports virtuelle* :

* **Balisage multisuite** : le balisage multisuite vous permet d’envoyer des demandes d’image non seulement à une suite de rapports globale, mais également à des suites de rapports enfants individuelles. Les données du rapport global sont dédupliquées dans toutes les suites de rapports.

  Par exemple, vous pouvez collecter toutes les données dans une suite de rapports globale et créer des suites de rapports secondaires en fonction de la marque, de la zone géographique ou d’un autre facteur de différenciation. Les différentes équipes au sein de votre entreprise peuvent alors agir sur les données des suites de rapports qui les intéressent.

  Pour utiliser le balisage multisuite, implémentez des suites de rapports enfants et une suite de rapports globale qui inclut toutes les données des enfants. Dans le code de suivi de vos pages web et de vos applications, vous trouverez l’identifiant de suite de rapports (RSID) pour la suite de rapports globale et les RSID pour les suites de rapports enfants applicables.<!-- Wording/be more specific? And include any links? -->

  Un appel serveur distinct est effectué à chaque suite de rapports dans la demande d’image. Les appels aux suites de rapports enfants sont des deuxièmes appels.

* **Suite de rapports virtuelle** : une [suite de rapports virtuelle](/help/components/vrs/vrs-about.md) est une demande portant sur des segments spécifiques, collectés dans une suite de rapports globale, et disponible pour des groupes d’utilisateurs choisis. Les suites de rapports virtuelles vous permettent de traiter des éléments de rapport pour différents utilisateurs finaux, sans utiliser le balisage multisuite, ce qui permet d’éviter les deuxièmes appels serveurs.

  Pour utiliser les suites de rapports virtuelles, commencez par implémenter une suite de rapports globale, puis analysez les données afin de créer des suites de rapports virtuelles, en appliquent des segments et des autorisations de groupe spécifiques. Vous pouvez créer des suites de rapports virtuelles dans le gestionnaire de suites de rapports virtuelles ([!UICONTROL Composants] > [!UICONTROL Suites de rapports virtuelles]). Pour plus dʼinformations, consultez la section « [Worflow Suites de rapports virtuelles](/help/components/vrs/c-workflow-vrs/vrs-workflow.md) ».

L’utilisation de suites de rapports virtuelles au lieu du balisage multi-suite est souvent une bonne pratique, mais ces dernières présentent certaines limites. Consultez la section « [Considérations relatives aux suites de rapports virtuelles et au balisage multisuite](/help/components/vrs/vrs-considerations.md) » pour déterminer l’approche de suite de rapports la plus appropriée aux besoins de votre entreprise. Pour consulter en détail les différences entre les suites de rapports virtuelles et la fonctionnalité de balisage multisuite, reportez-vous à la section « [Suites de rapports virtuelles par rapport au balisage multisuite](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78) ».

<!---## Rollup reports

>[!NOTE]
>
>[!DNL Reports & Analytics] is the only tool that supported rollup reports. Reports & Analytics was end-of-lifed on January 17, 2024.

Limitations of Rollup Reports {#limitations-rollups}

* Rollups provide total data, but they do not report individual values in reports. For example, eVar1 values are not included, but their aggregate total can be.
* Data is not deduplicated when the rollup combines data across report suites.
* Rollups run nightly at midnight.
* When you add a report suite to an existing rollup, historical data is not included in the rollup.
* All child report suites must have data in them for a rollup to function. If new report suites are included in a rollup, make sure to send at least one page view to each of those report suites.
* Rollup report suites can include a maximum of 40 child report suites.
* Rollup report suites can include a maximum of 100 events.
* Data contained in rollup report suites does not support breakdowns or segments.
* The Pages report is replaced with the Most Popular Sites report, which reports on metrics at the child-suite level.

## Comparison of Global Report Suite and Rollup Report  Features

**Secondary server calls**: Rollups do not incur any additional server calls beyond what a single report suite collects. If your organization uses multi-suite tagging, secondary server calls are made for each additional report suite included in an image request.

>[!TIP]
>
>If you use only a global report suite with [virtual report suites](/help/components/vrs/vrs-considerations.md), no secondary server calls are needed.

**Implementation changes**: Rollups do not require any implementation changes, while global report suites require you to include the global report suite ID in your implementation.

**Duplication**: Global report suites deduplicate unique visitors, while rollups do not. For example, if a user visits three of your domains in the same day, rollups would count three daily unique visitors. Global report suites would record one unique visitor.

**Time frame**: Rollups are only processed at midnight each night, while global report suites report data with standard latency.

**Breadth**: Rollups have no way to communicate between report suites. Global report suites can attribute credit to conversion variables between report suites and provide pathing across report suites.

**Historical data**: Rollups can aggregate historical data, while global report suites only report data from the point they were implemented.

**Reports**: Global report suites provide data on all dimensions; rollups provide aggregate data on only high-level reports.

**Supported products**: Rollups could only be used in Reports & Analytics. They are not supported in Analysis Workspace, or Data Warehouse. Global report suites can be used across all products.

**Number of aggregated report suites**: Rollups only support a maximum of 40 child report suites. Global report suites can be implemented on any number of domains or apps that you own.--->
