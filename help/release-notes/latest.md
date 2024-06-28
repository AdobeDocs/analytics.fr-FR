---
title: Notes de mise à jour actuelles d’Adobe Analytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 4633225cc35658a7de39a40cd77df00137a54461
workflow-type: tm+mt
source-wordcount: '1077'
ht-degree: 97%

---

# Notes de mise à jour actuelles d’Adobe Analytics (juin 2024)

**Dernière mise à jour** : jeudi 26 juin 2024

Ces notes de mise à jour portent sur la période du 12 juin 2024 à juillet 2024. Les mises à jour dʼAdobe Analytics suivent une [modèle de diffusion continue](releases.md), ce qui permet un déploiement plus flexible et progressif des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Nouvelles fonctionnalités ou améliorations {#features}

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Sélectionner plusieurs champs dans un filtre déroulant** | Lorsque plusieurs champs ont été ajoutés à un filtre déroulant, les utilisateurs et utilisatrices peuvent désormais sélectionner plusieurs champs à la fois. Le panneau est filtré pour inclure l’un des champs sélectionnés. <p>Auparavant, les utilisateurs et utilisatrices ne pouvaient sélectionner qu’un seul champ à la fois dans un filtre déroulant.</p><p>Pour plus d’informations, voir [Segments de liste déroulante statiques](/help/analyze/analysis-workspace/c-panels/panels.md#static-drop-down-segments) dans [Vue d’ensemble des panneaux](/help/analyze/analysis-workspace/c-panels/panels.md).</p><p>[Afficher une démonstration vidéo de cette fonctionnalité](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/navigating-workspace-projects/use-multi-select-drop-down-filters).</p> |  | 19 juin 2024 |
| **Table des matières pour les projets Workspace** | Une nouvelle table des matières est désormais disponible pour les projets. La table des matières contient des liens qui permettent aux utilisateurs et utilisatrices d’accéder rapidement aux panneaux et aux visualisations dans le projet. La table des matières peut être activée pour des projets individuels ou tous les projets d’un utilisateur ou d’une utilisatrice spécifique.<p>Pour plus d’informations, voir [Table des matières du projet](/help/analyze/analysis-workspace/build-workspace-project/project-table-of-contents.md).</p><p>[Afficher une démonstration vidéo de cette fonctionnalité](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/navigating-workspace-projects/create-a-toc-in-analysis-workspace).</p> |  | 19 juin 2024 |
| **Créer des liens hypertexte pour les éléments de dimension dans un tableau à structure libre** | Vous pouvez créer des liens hypertexte pour un ou plusieurs éléments de dimension afin de les rendre cliquables dans un tableau à structure libre d’Analysis Workspace. <p>Vous pouvez créer des liens hypertexte pour les éléments de dimension qui comportent des valeurs d’URL ou créer des URL personnalisées pour les éléments de dimension qui n’ont pas de valeurs d’URL.</p><p>Vous pouvez créer des URL personnalisées dynamiques pour plusieurs éléments de dimension à l’aide de variables. Les variables peuvent faire référence à la valeur d’un élément de dimension ou à la dimension de répartition.</p><p>Pour plus d’informations, voir [Créer des hyperliens pour les dimensions dans un tableau à structure libre](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md).</p><p>[Afficher une démonstration vidéo de cette fonctionnalité](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/tips-and-tricks/create-hyperlinks-in-freeform-tables).</p> |  | 19 juin 2024 |
| **Paramètres d’administration pour contrôler les comptes et les emplacements utilisés pour l’export et l’import** | Un nouvel onglet [« Paramètres d’administration » dans le gestionnaire des emplacements](/help/components/locations/locations-manager.md#configure-company-wide-settings-administrators-only) permet à l’équipe d’administration de contrôler si les utilisateurs et utilisatrices peuvent créer et modifier des comptes et des emplacements. Ces paramètres s’appliquent lorsque les utilisateurs et utilisatrices [configurent des comptes d’import et d’export dans le cloud](/help/components/locations/configure-import-accounts.md) et [configurent des emplacements d’import et d’export dans le cloud](/help/components/locations/configure-import-locations.md). <p>L’équipe d’administration peut également limiter les types de comptes (Google Cloud Platform, Azure RBAC, Amazon S3, etc.) que les utilisateurs et utilisatrices peuvent créer et utiliser.</p><p>Auparavant, un utilisateur ou une utilisatrice pouvait créer, modifier et utiliser des comptes et des emplacements pour n’importe quel type de compte.</p> | 12 juin 2024 | 20 juin 2024 |
| **Partager les comptes et les emplacements utilisés pour l’export et l’import** | Les personnes peuvent désormais mettre les comptes et les emplacements qu’elles créent à la disposition de toutes les personnes de leur organisation. Seules les personnes propriétaires de comptes et de sites, ainsi que les administrateurs et administratrices du système, peuvent modifier et supprimer des comptes et des emplacements.<p>Auparavant, les comptes et les emplacements ne pouvaient être utilisés que par la personne qui les avait créés.</p><p>Ces paramètres sont disponibles lorsque les utilisateurs et utilisatrices [configurent des comptes d’import et d’export dans le cloud](https://experienceleague.adobe.com/fr/docs/analytics/components/locations/configure-import-accounts) et [configurent des emplacements d’import et d’export dans le cloud](https://experienceleague.adobe.com/fr/docs/analytics/components/locations/configure-import-locations). </p> | 12 juin 2024 | 20 juin 2024 |
| **Activity Map utilise moins d’appels au serveur pour le SDK web.** | Actuellement, les événements de lien d’Activity Map sont comptabilisés comme leurs propres événements et engendrent des coûts supplémentaires. Cette amélioration applique certains événements de lien et les regroupe dans l’accès suivant, comme la manière dont les événements sont gérés par AppMeasurement. <p>(Lien vers la documentation mise à jour à suivre)</p> | La version bêta ouverte commence le jeudi 10 juillet 2024. | À confirmer |
| **Nouveau guide de l’API des sources de données** | Les points d’entrée de l’[API des sources de données Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-sources/) fournissent des méthodes pour créer, afficher, supprimer et charger des données vers des comptes de sources de données. |  | Disponible maintenant |
| **Nouvelles méthodes dans le guide de l’API Classifications** | Deux nouvelles méthodes pour récupérer les partitions de fichier ont été ajoutées au guide de l’API Classifications.<ul><li>[Obtenir la partition du fichier de traitement de classification](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/#get-classification-job-file-partition-list)</li><li>[Obtenir la partition du fichier de traitement d’export de classification](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/#get-classification-export-job-file-part)</li></ul> |  | Disponible maintenant |

{style="table-layout:auto"}

## Correctifs dans Adobe Analytics

* Correction des problèmes de classifications suivants : AN-347682 ; AN-348396 ; AN-348625 ; AN-348668 ; AN-348926 ; AN-348936 ; AN-349040 ; AN-349191 ; AN-349195 ; AN-349443 ; AN-349697 ; AN-349758 ; AN-349862 ; AN-350051 ; AN-350054 ; AN-350208 ; AN-350497 ; AN-350525 ; AN-351067
* Correction des problèmes de Data Warehouse suivants : AN-346862 ; AN-349409 ; AN-349926 ; AN-350629 ; AN-350996
* Correction des problèmes de flux de données suivants : AN-346727 ; AN-348282 ; AN-348334 ; AN-348725 ; AN-348726 ; AN-348823 ; AN-349081 ; AN-349207 ; AN-349307 ; AN-349539 ; AN-349710 ; AN-349729 ; AN-349742 ; AN-349878 ; AN-349943 ; AN-350527 ;
* Correction du problème des sources de données suivant : AN-350038
* Correction des problèmes Analysis Workspace suivants : AN-342953 ; AN-346346 ; AN-349590 ; AN-349717 ; AN-350057 ; AN-350697 ; AN-350904
* Résolution des problèmes de Report Builder suivants : AN-348903 ; AN-350691
* Correction des problèmes A4T suivants : AN-347690 ; AN-350853

### Autres correctifs d’Analytics

AN-346470 ; AN-346850 ; AN-347227 ; AN-348145 ; AN-348564 ; AN-349001 ; AN-349008 ; AN-349211 ; AN-349719 ; AN-350523 ;

## Avis importants pour les administrateurs d’Adobe Analytics {#admin}

| Avis | Date d’ajout ou de mise à jour | Description |
| ----------- | ---------- | ---------- |
| **Expiration après 13 mois des`cust_visids`** enregistrés | 22 mai 2024 | Une prochaine version du moteur de traitement des accès Analytics, **prévue pour juillet 2024**, introduit l’expiration après 13 mois des `cust_visids` enregistrés. Si « Activer la connexité des visiteurs » est activé dans la suite de rapports, ce paramètre est utilisé pour rechercher le `cust_visid` pour une `visid_high/visid_low value` sans `cust_visid` sur l’accès. Actuellement, il n’existe aucune expiration du mappage d’un `cust_visid` pour `visid_high/visid_low`. Avec cette version, si 13 mois ou plus se sont écoulés depuis que `visid_high/visid_low` a eu un `cust_visid` sur un accès, le mappage expire. |
| **Mises à jour des zones géographiques ISO** | 10 mai 2024 | Adobe effectuera les mises à jour 2024 des zones géographiques ISO le 7 juin 2024. Attendez-vous à voir des mises à jour mineures des informations géographiques après cette version. |

{style="table-layout:auto"}

## Avis de fin de vie {#eol}

| Produit ou fonctionnalité en fin de vie | Date d’ajout ou de mise à jour | Description |
| --- | --- | --- |
| **Migration vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O** | 11 mai 2023 | Les clients et clientes de l’API Adobe Analytics et de Livestream qui utilisent les informations d’identification JWT d’Adobe I/O doivent migrer vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O avant le **1er janvier 2025**. Adobe I/O n’autorisera pas la création d’informations d’identification JWT à compter du 1er mai 2024. Les clients et clientes utilisant JWT doivent créer des informations d’identification de serveur à serveur OAuth ou migrer leurs informations d’identification JWT existantes vers des informations d’identification de serveur à serveur OAuth. Ils ou elles doivent également mettre à jour leurs applications clientes afin d’utiliser les nouvelles informations d’identification de serveur à serveur OAuth. <ul><li>[Migration des informations d’identification du compte de service (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guide de mise en œuvre pour les nouvelles et les anciennes applications avec OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilisation des nouvelles informations d’identification de serveur à serveur OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Questions fréquentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

Pour connaître les dernières mises à jour des versions d’AppMeasurement (version 2.26.0), reportez-vous aux [Notes de mise à jour d’AppMeasurement pour JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=fr).


## Ressources connexes

* [Notes de mise à jour précédentes pour 2024](/help/release-notes/2024.md)
* [Notes de mise à jour de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=fr)
* [Notes de mise à jour du module complémentaire Collection de médias en flux continu](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* Dernières mises à jour des [produits Adobe Experience Cloud](https://business.adobe.com/fr/products/adobe-experience-cloud-products.html)
