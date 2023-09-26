---
title: Notes de mise à jour actuelles d’Adobe Analytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: f6c1162e6f5e8cc6f38da21b5bc19389ffd1e3c5
workflow-type: tm+mt
source-wordcount: '899'
ht-degree: 95%

---

# Notes de mise à jour actuelles d’Adobe Analytics (septembre 2023)

**Dernière mise à jour** : 20 septembre 2023

Les notes de mise à jour de septembre couvrent la période du 13 septembre 2023 au 3 octobre 2023. Les mises à jour dʼAdobe Analytics suivent une [modèle de diffusion continue](releases.md), ce qui permet un déploiement plus flexible et progressif des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Nouvelles fonctionnalités ou améliorations {#features}

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Classifications dans API 2.0** | Fournit les méthodes de l’API Adobe Analytics 2.0 pour enregistrer, supprimer, récupérer, importer et exporter des données de jeu de classifications. [En savoir plus](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/) | S.O. | 13 septembre 2023 |
| **Prise en charge du nouveau champ `correlationID` pour les classifications A4T** | Le champ `_experience.decisioning.propositions.scopeDetails.correlationID` est désormais disponible dans le schéma du connecteur source Adobe Analytics. Nous ajoutons cet ID pour faciliter l’association des données de classification pour les activités Adobe Target et les événements d’expérience. | S.O. | 13 septembre 2023 |
| **Améliorations de Data Warehouse** | Lors de la création d’une requête de Data Warehouse, vous pouvez désormais configurer un compte cloud à utiliser comme destination du rapport. Les types de compte cloud suivants sont disponibles pour l’envoi de données :<ul><li>Amazon S3</li><li>Google Cloud Platform</li><li>SAS Azure</li><li>RBAC Azure</li><li>E-mail (cette option était auparavant disponible)</li></ul>FTP, SFTP, Azure Blob et S3 sont toujours disponibles en tant que destinations de rapport, mais ne sont plus recommandés.<p>L’expérience client lors de la création et de la gestion de requêtes de Data Warehouse a également été améliorée. Pour plus d’informations, voir [Créer une requête de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md) et [Gérer des requêtes de Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-requests-manage.html?lang=fr). | 13 septembre 2023 | 4 octobre 2023 |
| **Nouvelles colonnes disponibles lors de la gestion des composants** | Les nouvelles colonnes suivantes sont désormais disponibles lors de la gestion des composants :<ul><li>Utilisation dans<p>Cette colonne est disponible dans la [Gestionnaire de mesures calculées](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md) et la variable [Gestionnaire de segments](/help/components/segmentation/segmentation-workflow/seg-manage.md).</p></li><li>Dernière utilisation<p>Cette colonne est disponible dans la [Gestionnaire de mesures calculées](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md), la variable [Gestionnaire de segments](/help/components/segmentation/segmentation-workflow/seg-manage.md), et la variable [Gestionnaire d’alertes](/help/components/c-alerts/alert-manager.md).</p></li></ul><p>Ces informations peuvent vous aider à déterminer si un composant est utile aux utilisateurs et utilisatrices de votre entreprise, où il est utilisé et s’il doit être supprimé ou modifié. Vous pouvez utiliser le dictionnaire de données avec ces informations pour vous aider à effectuer le suivi et à mieux comprendre comment les composants sont utilisés dans votre organisation.</p> | 20 septembre 2023 | 4 octobre 2023 |

{style="table-layout:auto"}

## Correctifs dans Adobe Analytics

* Correction d’un problème qui empêchait l’affichage des données de classification dans Workspace. (AN-326827)

## Autres correctifs

AN-314882 ; AN-315591 ; AN-318165 ; AN-318559 ; AN-319031 ; AN-319244 ; AN-321657 ; AN-321759 ; AN-323099 ; AN-323596 ; AN-323640 ; AN-324442 ; AN-324921 ; AN-324953 ; AN-324977 ; AN-324979 ; AN-325124 ; AN-325395 ; AN-325433 ; AN-325535 ; AN-325693 ; AN-325720 ; AN-325835 ; AN-325880 ; AN-325957 ; AN-325984 ; AN-326054 ; AN-326065 ; AN-326136 ; AN-326155 ; AN-326162 ; AN-326235 ; AN-326317 ; AN-326344 ; AN-326357 ; AN-326359 ; AN-326433 ; AN-326438 ; AN-326440 ; AN-326461 ; AN-326464 ; AN-326523 ; AN-326553 ; AN-326606 ; AN-326635 ; AN-326642 ; AN-326652 ; AN-326678 ; AN-326769 ; AN-326777 ; AN-326830 ; AN-326938 ; AN-326949 ; AN-327081 ; AN-327082 ; AN-327085 ; AN-327103 ; AN-327198 ; AN-327225 ; AN-327275 ; AN-327358 ; AN-327423 ; AN-327561 ; AN-327755 ; AN-327896 ; AN-327922 ; AN-328128 ; AN-328300 ; AN-328428 ; AN-328518 ; AN-328554

## Avis importants pour les administrateurs d’Adobe Analytics {#admin}

| Remarque | Date d’ajout ou de mise à jour | Description |
| ----------- | ---------- | ---------- |
| S.O. | S.O. | S.O. |

{style="table-layout:auto"}

## Avis de fin de vie {#eol}

| Produit ou fonctionnalité en fin de vie | Date d’ajout ou de mise à jour | Description |
| --- | --- | --- |
| **Migration vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O** | 11 mai 2023 | Les clients et clientes de l’API Adobe Analytics et de Livestream qui utilisent les informations d’identification JWT d’Adobe I/O doivent migrer vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O avant le **1er janvier 2025**. Adobe I/O n’autorisera pas la création d’informations d’identification JWT à compter du 1er mai 2024. Les clients et clientes utilisant JWT doivent créer des informations d’identification de serveur à serveur OAuth ou migrer leurs informations d’identification JWT existantes vers des informations d’identification de serveur à serveur OAuth. Ils ou elles doivent également mettre à jour leurs applications clientes afin d’utiliser les nouvelles informations d’identification de serveur à serveur OAuth. <ul><li>[Migration des informations d’identification du compte de service (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guide de mise en œuvre pour les nouvelles et les anciennes applications avec OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilisation des nouvelles informations d’identification de serveur à serveur OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Questions fréquentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **Fin de vie de [!DNL Reports & Analytics]** | 7 mars 2023 | À compter du **31 décembre 2023**, Adobe prévoit dʼabandonner [!DNL Reports & Analytics] et ses rapports et fonctionnalités associés. [!DNL Reports & Analytics] sʼappuie sur des rapports, des visualisations et des technologies sous-jacentes qui ne répondent plus aux normes technologiques dʼAdobe. La plupart des fonctionnalités de [!DNL Reports & Analytics] sont disponibles dans [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=fr). Depuis la publication d’Analysis Workspace en 2015, les fonctionnalités de [!DNL Reports & Analytics] ont migré vers Analysis Workspace, de telle sorte quʼun seuil de parité en matière de workflow a été atteint. [Cet avis](https://spark.adobe.com/page/6WnF8JK6IRDhf/) décrit le processus de fin de vie.<p>Le 31 décembre 2023, nous allons mettre fin à de nombreuses fonctionnalités Reports &amp; Analytics associées, notamment : Rapports planifiés, Extractions de données et Rapports DL. Après le 31 décembre 2023, les rapports planifiés ne seront plus envoyés. En **avril 2023**, tous les rapports dont l’expiration était planifiée au-delà du 31 décembre 2023 ont été automatiquement mis à jour et leur expiration a été définie pour le 31 décembre 2023. En outre, vous ne pouvez plus planifier les rapports ultérieurs au-delà du 31 décembre 2023. |
| **Abandon de la fonctionnalité [!UICONTROL Listes de publication]** | 29 septembre 2022 | Dans le cadre de la fin de vie de Reports &amp; Analytics, les [!UICONTROL listes de publication] sont programmées pour atteindre la fin de vie en **décembre 2023**. Vous ne pourrez pas créer de [!UICONTROL listes de publication] ou y accéder pour envoyer ou planifier des projets [!UICONTROL Analysis Workspace]. |
| **Fin de vie de Data Workbench** | 14 septembre 2022 | Adobe a l’intention d’abandonner Data Workbench à compter du **31 décembre 2023**. Consultez l’[annonce de fin de vie du Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=fr) pour plus d’informations. Contactez le gestionnaire de compte Adobe de votre entreprise pour toute question. |

{style="table-layout:auto"}

## AppMeasurement

Pour connaître les dernières mises à jour des versions d’AppMeasurement (version 2.24.0), reportez-vous aux [Notes de mise à jour d’AppMeasurement pour JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=fr).


## Ressources connexes

* [Notes de mise à jour précédentes pour 2022](/help/release-notes/2022.md)
* [Notes de mise à jour de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=fr)
* [Notes de mise à jour de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* Dernières mises à jour des [produits Adobe Experience Cloud](https://business.adobe.com/fr/products/adobe-experience-cloud-products.html)
