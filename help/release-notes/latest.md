---
title: Notes de mise à jour actuelles d’Adobe Analytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: dfb3750edabed3fd9aef758d2ea1625fc3fb6a96
workflow-type: tm+mt
source-wordcount: '1131'
ht-degree: 100%

---

# Notes de mise à jour actuelles d’Adobe Analytics (octobre/novembre 2023)

**Dernière mise à jour** : 25 octobre 2023

Ces notes de mise à jour portent sur la période du 23 octobre 2023 à la fin novembre 2023. Les mises à jour dʼAdobe Analytics suivent une [modèle de diffusion continue](releases.md), ce qui permet un déploiement plus flexible et progressif des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Nouvelles fonctionnalités ou améliorations {#features}

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Améliorations apportées au gestionnaire des activités de rapport** | Le gestionnaire des activités de rapport vous permet d’afficher la capacité de création de rapports pour chaque suite de rapports de votre organisation. Il offre aux administrateurs et administratrices une visibilité détaillée sur la consommation de rapports et permet de diagnostiquer et de résoudre facilement les problèmes de capacité pendant les heures de pointe de la création de rapports. Voici quelques-unes des améliorations désormais disponibles dans le gestionnaire des activités de rapport : <ul><li>Limiter les demandes ultérieures : en plus d’annuler des demandes en cours, les administrateurs et administratrices peuvent désormais limiter les demandes pour une période définie. Les administrateurs et administratrices peuvent limiter les demandes par demande, projet et utilisateur ou utilisatrice.</li><li>Outre les mesures Utilisation et Capacité, le gestionnaire des activités de rapport inclut désormais plus de données sur l’activité de création de rapports : colonne Complexité, colonne Utilisateur et colonne Connexion.</li><li>Toutes les annulations et restrictions effectuées dans le gestionnaire des activités de rapport sont désormais visibles dans le Journal d’audit. Les administrateurs et administratrices peuvent utiliser le journal d’audit pour afficher les annulations en cours. Le processus d’annulation ne peut pas être annulé dans le gestionnaire des activités de rapport ou dans le journal d’audit.</li></ul><p>Pour plus d’informations, voir [Présentation du gestionnaire des activités de rapport](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md).</p> | 17 octobre 2023 | 24 octobre 2023 |
| **Améliorations de Data Warehouse** | Lors de la création d’une requête de Data Warehouse, vous pouvez désormais configurer un compte cloud à utiliser comme destination du rapport. Les types de compte cloud suivants sont disponibles pour l’envoi de données :<ul><li>Amazon S3</li><li>Google Cloud Platform</li><li>SAS Azure</li><li>RBAC Azure</li><li>E-mail (cette option était auparavant disponible)</li></ul>FTP, SFTP, Azure Blob et S3 sont toujours disponibles en tant que destinations de rapport, mais ne sont plus recommandés.<p>L’expérience client lors de la création et de la gestion de requêtes de Data Warehouse a également été améliorée. Pour plus d’informations, voir [Créer une requête de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md) et [Gérer des requêtes de Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-requests-manage.html?lang=fr). | 12 septembre 2023 | À confirmer |

{style="table-layout:auto"}

## Correctifs dans Adobe Analytics

* Ces modifications du moteur de traitement et de reporting Analytics seront déployées au cours de la dernière semaine d’octobre : nous corrigerons un problème où les libellés des dimensions Page ou Lien s’affichaient incorrectement comme `Unknown`. Avant le correctif, les libellés `Unknown` pouvaient s’afficher de manière incorrecte lorsqu’un nom de page ou un nom de lien n’était pas transmis lors d’un accès, affichant par défaut l’[!UICONTROL URL de la page] et l’[!UICONTROL URL du lien], respectivement. Ces dimensions ont été configurées pour ne pas respecter la casse. Grâce à ce correctif, les futurs rapports seront corrects. Mais pour les rapports sur les données historiques, certains résultats peuvent encore être incorrectement libellés comme `Unknown`. (AN-328030)

### Autres correctifs

-315676 ; AN- ; AN-323398 ; AN-326209 ; AN-328178 ; AN-328261 ; AN-328395 ; AN-328671 ; AN-329282 ; AN-329330 ; AN-329355 ; AN-329506 ; AN-329516 ; AN-329738 ; AN-329769 ; AN-329771 ; AN-329816 ; AN-329877 ; AN-329928 ; AN-329957 ; AN-329962 ; AN-329966 ; AN-330023 ; AN-330081 ; AN-330083 ; AN-330105 ; AN-330138 ; AN-330140 ; AN-330165 ; AN-330241 ; AN-330359 ; AN-330366 ; AN-330427 ; AN-330438 ; AN-330442 ; AN-330534 ; AN-330616 ; AN-330654 ; AN-330783 ; AN-330879 ; AN-330881 ; AN-330883 ; AN-330887 ; AN-330888 ; AN-330955 ; AN-330979 ; AN-331031 ; AN-331053 ; AN-331068 ; AN-331071 ; AN-331074 ; AN-331075 ; AN-331076 ; AN-331078 ; AN-331085 ; AN-331093 ; AN-331167 ; AN-331171 ; AN-331181 ; AN-331196 ; AN-331226 ; AN-331258 ; AN-331260 ; AN-331279 ; AN-331286 ; AN-331290 ; AN-331365 ; AN-331375 ; AN-331376 ; AN-331454 ; AN-331519 ; AN-331570 ; AN-331590 ; AN-331593 ; AN-331603 ; AN-331751 ; AN-331816 ; AN-331897 ; AN-331900 ; AN-331906 ; AN-331926 ; AN-331929 ; AN-332031 ; AN-332067 ; AN-332101 ; AN-332114 ; AN-332156 ; AN-332201 ; AN-332225 ; AN-332253 ; AN-332277 ; AN-332361 ; AN-332370 ; AN-332386

## Avis importants pour les administrateurs d’Adobe Analytics {#admin}

| Remarque | Date d’ajout ou de mise à jour | Description |
| ----------- | ---------- | ---------- |
| **Obscurcissement complet des adresses IP pour les accès Adobe Experience Edge** | 27 septembre 2023 | L’obscurcissement des adresses IP pour les accès provenant d’Experience Edge sera mis à jour ultérieurement en octobre 2023. En avril 2023, Experience Edge a ajouté la possibilité d’obscurcir les adresses IP. À ce moment-là, Adobe Analytics ne prenait en charge que l’obscurcissement partiel des adresses IP, en raison de la manière dont Analytics traitait les accès d’Experience Edge. Lorsque les clients et clientes choisissaient l’obscurcissement complet pour Experience Edge, Analytics ne recevait que des adresses IP partiellement obscurcies. Lorsque cette modification est mise en œuvre, Analytics reçoit l’adresse IP entièrement obscurcie. |
| **Adobe Analytics Livestream - API Analytics 2.0** | 27 septembre 2023 | Les clientes et clients peuvent maintenant accéder au [Guide de point d’entrée pour Adobe Analytics Livestream](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/) sous les API Adobe Analytics 2.0 à la place de son emplacement précédent (avec les API 1.4). Notez que les clientes et clients qui utilisent les informations d’identification JWT d’Adobe I/O doivent migrer vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O avant le 1er janvier 2025. (Voir les détails sous les avis de fin de vie ci-dessous.) |

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
