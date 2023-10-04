---
title: Notes de mise à jour actuelles d’Adobe Analytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 5785629376b8ae528535629a77a29dcdd2ca80b8
workflow-type: tm+mt
source-wordcount: '1215'
ht-degree: 58%

---

# Notes de mise à jour actuelles d’Adobe Analytics (octobre 2023)

**Dernière mise à jour** : 4 octobre 2023

Les notes de mise à jour d’octobre couvrent la période du 4 octobre 2023 au 25 octobre 2023. Les mises à jour dʼAdobe Analytics suivent une [modèle de diffusion continue](releases.md), ce qui permet un déploiement plus flexible et progressif des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Nouvelles fonctionnalités ou améliorations {#features}

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Nouvelles colonnes disponibles lors de la gestion des composants** | Les nouvelles colonnes suivantes sont désormais disponibles lors de la gestion des composants :<ul><li>Utilisation dans<p>Cette colonne est disponible dans la [Gestionnaire de mesures calculées](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md) et la variable [Gestionnaire de segments](/help/components/segmentation/segmentation-workflow/seg-manage.md).</p></li><li>Dernière utilisation<p>Cette colonne est disponible dans la [Gestionnaire de mesures calculées](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md), la variable [Gestionnaire de segments](/help/components/segmentation/segmentation-workflow/seg-manage.md), et la variable [Gestionnaire d’alertes](/help/components/c-alerts/alert-manager.md).</p></li></ul><p>Ces informations peuvent vous aider à déterminer si un composant est utile aux utilisateurs et utilisatrices de votre entreprise, où il est utilisé et s’il doit être supprimé ou modifié. Vous pouvez utiliser le dictionnaire de données avec ces informations pour vous aider à effectuer le suivi et à mieux comprendre comment les composants sont utilisés dans votre organisation.</p> | 20 septembre 2023 | 4 octobre 2023 |
| **Améliorations apportées à Activity Manager pour la création de rapports** | Le gestionnaire des activités de rapport vous permet d’afficher la capacité de création de rapports pour chaque suite de rapports de votre organisation.  Il fournit aux administrateurs une visibilité détaillée sur la consommation des rapports afin de diagnostiquer et de résoudre facilement les problèmes de capacité pendant les heures de pointe de la création de rapports. Voici quelques-unes des améliorations désormais disponibles dans le Gestionnaire d’activités de création de rapports : <ul><li>Restreindre les requêtes suivantes : en plus d’annuler les requêtes en cours, les administrateurs peuvent désormais limiter les requêtes pour une période définie. Les administrateurs peuvent limiter les requêtes par requête, projet et utilisateur.</li><li>Outre les mesures Utilisation et Capacité, le Gestionnaire des activités de création de rapports inclut désormais plus de données sur l’activité de création de rapports : colonne Complexité, colonne Utilisateur et colonne Connexion.</li><li>Toutes les annulations et restrictions effectuées dans le Gestionnaire des activités de reporting sont désormais visibles dans le Journal d’audit. Les administrateurs peuvent utiliser le journal d’audit pour afficher ce qui est actuellement annulé. Les annulations ne peuvent pas être annulées dans le Gestionnaire des activités de création de rapports ou dans le Journal d’audit.</li></ul>En savoir plus (bientôt disponible) | 17 octobre 2023 | 23 octobre 2023 |
| **Améliorations de Data Warehouse** | Lors de la création d’une requête de Data Warehouse, vous pouvez désormais configurer un compte cloud à utiliser comme destination du rapport. Les types de compte cloud suivants sont disponibles pour l’envoi de données :<ul><li>Amazon S3</li><li>Google Cloud Platform</li><li>SAS Azure</li><li>RBAC Azure</li><li>E-mail (cette option était auparavant disponible)</li></ul>FTP, SFTP, Azure Blob et S3 sont toujours disponibles en tant que destinations de rapport, mais ne sont plus recommandés.<p>L’expérience client lors de la création et de la gestion de requêtes de Data Warehouse a également été améliorée. Pour plus d’informations, voir [Créer une requête de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md) et [Gérer des requêtes de Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-requests-manage.html?lang=fr). | 12 septembre 2023 | 25 octobre 2023 |
| **Migration de projets Adobe Analytics et de tout composant inclus vers Customer Journey Analytics** | Vous pouvez désormais migrer vos projets Adobe Analytics vers Customer Journey Analytics. Ce processus simplifie la transition d’Adobe Analytics vers Customer Journey Analytics. Lorsque vous migrez des projets vers Customer Journey Analytics, les ressources sont mappées d’une suite de rapports Adobe Analytics à une vue de données de Customer Journey Analytics. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration.html) | 11 octobre 2023 | 25 octobre 2023 |

{style="table-layout:auto"}

## Correctifs dans Adobe Analytics

* Correction de problèmes en raison desquels les rapports A4T n’apparaissaient pas dans l’interface utilisateur de Target/Analytics. (AN-329375, AN-329745, AN-330026)

AN-313983; AN-324189; AN-325095; AN-325677; AN-325886; AN-; AN-326068; AN-326360; AN-326458; AN-327290; AN-; AN-327315; AN-327353; AN-327505; AN-; AN-; AN-; AN-; AN-; AN-; AN-AN; AN-; AN-; AN-; AN-; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN-AN ; AN- ; AN- ; AN-AN ; AN- ; AN-AN-AN-AN-AN-ET-AN-; AN ; AN-AN-AN-AN-AN-ET-AN-AN AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN-AN ; AN- ; AN- ; AN-AN ; AN- ; AN-AN-AN-AN-AN-ET-AN-; AN ; AN-AN-AN-AN-AN-ET-AN-AN AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN-

## Avis importants pour les administrateurs d’Adobe Analytics {#admin}

| Remarque | Date d’ajout ou de mise à jour | Description |
| ----------- | ---------- | ---------- |
| **Obscurcissement complet des adresses IP pour les accès Adobe Experience Edge** | 27 septembre 2023 | L’obscurcissement des adresses IP pour les accès provenant d’Experience Edge sera mis à jour plus tard en octobre 2023. En avril, Experience Edge a ajouté la possibilité d’obscurcir les adresses IP. À l’époque, Adobe Analytics ne prenait en charge que l’obscurcissement partiel des adresses IP, en raison de la manière dont Analytics traitait les accès à partir d’Experience Edge. Lorsque les clients ont choisi l’obscurcissement complet pour Experience Edge, Analytics n’a reçu que des adresses IP partiellement obscurcies. Lorsque cette modification est mise en oeuvre, Analytics reçoit l’adresse IP entièrement obscurcie. |
| **Adobe Analytics Livestream - API Analytics 2.0** | 27 septembre 2023 | Les clients peuvent désormais accéder au [Guide de point de terminaison pour Adobe Analytics Livestream](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/) sous les API Adobe Analytics 2.0 à la place dans son emplacement précédent, avec les API 1.4. Notez que les clients qui utilisent des informations d’identification JWT d’Adobe I/O doivent migrer vers les informations d’identification Adobe I/O OAuth serveur à serveur d’ici le 1er janvier 2025. (Voir les détails sous les avis de fin de vie ci-dessous.) |

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

Pour connaître les dernières mises à jour des versions d’AppMeasurement (version 2.25.0), reportez-vous aux [Notes de mise à jour d’AppMeasurement pour JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=fr).


## Ressources connexes

* [Notes de mise à jour précédentes pour 2022](/help/release-notes/2022.md)
* [Notes de mise à jour de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=fr)
* [Notes de mise à jour de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* Dernières mises à jour des [produits Adobe Experience Cloud](https://business.adobe.com/fr/products/adobe-experience-cloud-products.html)
