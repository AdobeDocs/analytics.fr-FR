---
title: Notes de mise à jour actuelles d’Adobe Analytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: c3f59a07d51f5e6a73fa87aed573450c133d5bd6
workflow-type: tm+mt
source-wordcount: '1112'
ht-degree: 39%

---

# Notes de mise à jour actuelles d’Adobe Analytics (janvier 2024)

**Dernière mise à jour** : jeudi 10 janvier 2024

Ces notes de mise à jour portent sur la période allant de janvier 2024 au 13 février 2024. Les mises à jour dʼAdobe Analytics suivent une [modèle de diffusion continue](releases.md), ce qui permet un déploiement plus flexible et progressif des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Nouvelles fonctionnalités ou améliorations {#features}

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Mises à jour du Data Warehouse** | Les améliorations de Data Warehouse suivantes sont désormais disponibles :<ul><li>Lors de la création d’une requête de Data Warehouse, les utilisateurs peuvent désormais mettre les requêtes à la disposition de tous les utilisateurs de l’organisation en activant le nouveau bouton nommé [!UICONTROL **Mise à disposition des utilisateurs de votre entreprise**].<p>Pour plus d’informations, voir [Paramètres généraux de la demande de Data Warehouse](/help/export/data-warehouse/create-request/dw-general-settings.md).</p></li><li>Lors de la création ou de la gestion de destinations de rapports de Data Warehouse, les administrateurs système peuvent désormais afficher les comptes et emplacements créés par les utilisateurs de l’entreprise en activant le bouton d’activation appelé [!UICONTROL **Afficher toutes les destinations**].<p>Pour plus d’informations, voir [Configuration d’une destination de rapport pour une requête de Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md).</p></li> | S.O. | jeudi 10 janvier 2024 |
| **Mises à jour de la visualisation du résumé des mesures clés** | Lors de l’utilisation de la visualisation Synthèse des mesures clés, la période de comparaison peut désormais se mettre à jour automatiquement, selon que l’option Période de comparaison que vous choisissez est relative à la période principale ou fixe. [En savoir plus](/help/analyze/analysis-workspace/visualizations/key-metric.md). | S.O. | jeudi 17 janvier 2024 |

{style="table-layout:auto"}

## Correctifs dans Adobe Analytics

* Correction des problèmes de classifications suivants : AN-314821 ; AN-326839 ; AN-332079 ; AN-332704 ; AN-332812 ; AN-332902 ; AN-332975 ; AN-333300 ; AN-333023 ; AN-333033 ; AN-; AN-333174 ; AN-333910 ; AN- ; AN- ; AN- ; AN- ; AN-; AN- ; AN-; AN- ; AN-AN-; AN- ; AN- ; AN- ; AN- ; AN- ; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN-
* Correction des problèmes du Créateur de règles de classifications suivants : AN-332390 ; AN-332573 ; AN-332718 ; AN-332927 ; AN-333248 ; AN-333953 ; AN-334647 ; AN-334736 ; AN-334910 ; AN-335642 ; AN-335683 ; AN-335811 ; AN- ; AN-; AN- ; AN-; AN- ; AN-; AN-; AN- ;
* Correction des problèmes A4T suivants : AN-334564 ; AN-336178 ;
* Correction des problèmes d’utilisation de l’appel au serveur suivants : AN-332568 ; AN-333105 ; AN-333167 ; AN-333983 ; AN-334209 ; AN-334278
* Correction des problèmes de Data Warehouse suivants : AN-333010 ; AN-333076 ; AN-330227 ; AN-331580 ; AN-333350 ; AN-334291 ; AN-334283 ; AN-334287 ; AN-334301 ; AN-334385 ; AN-; AN-334453 ; AN-334977 ; AN- ; AN- ; AN-; AN- ; AN-; AN- ; AN-; AN- ; AN-AN-;
* Correction des problèmes de flux de données suivants : AN-332241 ; AN-332366 ; AN-332617 ; AN-332654 ; AN-332702 ; AN-332723 ; AN-; AN-333014 ; AN-333166 ; AN-334037 ; AN-334125 ; AN-334211 ; AN-334216 ; AN- ; AN- ; AN-; AN- ; AN-; AN- ; AN-; AN- ; AN-AN-AN-AN-AN-; AN-AN; AN-; AN-; AN-AN; AN-; AN-AN; AN-; AN-AN; AN-; AN-AN; AN-; AN-AN; AN-; AN-AN-AN; AN-; AN-AN-AN
* Correction des problèmes de Report Builder suivants : AN-335246 ; AN-336311 ;
* Correction des problèmes Analysis Workspace suivants : AN-323760 ; AN-324191 ; AN-324913 ; AN-330126 ; AN-332808 ; AN-333168 ; AN-333382 ; AN-334839 ; AN-336040 ; AN-337043 ;

### Autres correctifs

AN-323975; AN-325383; AN-325809; AN-326787; AN-331611; AN-; AN-331818; AN-332124; AN-332272; AN-332911; AN-; AN-333070; AN-333302; AN-333377; AN-; AN-; AN-; AN-; AN-; AN-; AN-AN; AN-; AN-; AN-; AN-; AN- ; AN- ; AN- ; AN-

## Avis importants pour les administrateurs d’Adobe Analytics {#admin}

| Avis | Date d’ajout ou de mise à jour | Description |
| ----------- | ---------- | ---------- |
| Ajout d’objets membres de l’API Adobe | jeudi 17 janvier 2024 | Adobe peut ajouter des membres de requête et de réponse facultatifs (paires nom/valeur) aux objets API existants sans préavis ni modification du contrôle de version. Ces ajouts doivent être des modifications incessantes pour votre mise en oeuvre. Adobe vous recommande de vous référer à la documentation de l’API de tout outil tiers que vous intégrez à nos API afin que ces ajouts soient ignorés dans le traitement s’ils ne sont pas compris. Adobe ne supprimera pas les paramètres ni n’ajoutera les paramètres requis sans d’abord fournir une notification standard via les notes de mise à jour. |
| `getPageLoadTime` plugin deprecated | jeudi 10 janvier 2024 | Ce module externe n’est plus pris en charge. Son code utilise la méthode performance.timing, qui (selon MDN) a été [obsolète](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceTiming). La tâche sur un module externe mis à jour a commencé. |

{style="table-layout:auto"}

## Avis de fin de vie {#eol}

| Produit ou fonctionnalité en fin de vie | Date d’ajout ou de mise à jour | Description |
| --- | --- | --- |
| **Fin de vie de [!DNL Reports & Analytics]** | jeudi 10 janvier 2024 | À compter du **jeudi 17 janvier 2024**, Adobe prévoit dʼabandonner [!DNL Reports & Analytics] et ses rapports et fonctionnalités associés. [!DNL Reports & Analytics] sʼappuie sur des rapports, des visualisations et des technologies sous-jacentes qui ne répondent plus aux normes technologiques dʼAdobe. La plupart des fonctionnalités de [!DNL Reports & Analytics] sont disponibles dans [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=fr). Depuis la publication d’Analysis Workspace en 2015, les fonctionnalités de [!DNL Reports & Analytics] ont migré vers Analysis Workspace, de telle sorte quʼun seuil de parité en matière de workflow a été atteint. [Cet avis](https://spark.adobe.com/page/6WnF8JK6IRDhf/) décrit le processus de fin de vie.<p>Le 31 décembre 2023, nous allons mettre fin à de nombreuses fonctionnalités Reports &amp; Analytics associées, notamment : Rapports planifiés, Extractions de données et Rapports DL. Après le 31 décembre 2023, les rapports planifiés ne seront plus envoyés. En **avril 2023**, tous les rapports dont l’expiration était planifiée au-delà du 31 décembre 2023 ont été automatiquement mis à jour et leur expiration a été définie pour le 31 décembre 2023. En outre, vous ne pouvez plus planifier les rapports ultérieurs au-delà du 31 décembre 2023. |
| **Abandon de la fonctionnalité [!UICONTROL Listes de publication]** | jeudi 10 janvier 2024 | Dans le cadre de la fin de vie de Reports &amp; Analytics, [!UICONTROL Listes de publication] sont prévues pour atteindre la fin de vie le **17 janvier 2024**. Vous ne pourrez pas créer de [!UICONTROL listes de publication] ou y accéder pour envoyer ou planifier des projets [!UICONTROL Analysis Workspace]. |
| **Fin de vie de Data Workbench** | mercredi 2 janvier 2024 | Adobe du Data Workbench de fin de vie efficace **31 décembre 2023**. Consultez l’[annonce de fin de vie du Data Workbench](https://express.adobe.com/page/GSu6oKOD88GAj/) pour plus d’informations. Contactez le gestionnaire de compte Adobe de votre entreprise pour toute question. |
| **Migration vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O** | 11 mai 2023 | Les clients et clientes de l’API Adobe Analytics et de Livestream qui utilisent les informations d’identification JWT d’Adobe I/O doivent migrer vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O avant le **1er janvier 2025**. Adobe I/O n’autorisera pas la création d’informations d’identification JWT à compter du 1er mai 2024. Les clients et clientes utilisant JWT doivent créer des informations d’identification de serveur à serveur OAuth ou migrer leurs informations d’identification JWT existantes vers des informations d’identification de serveur à serveur OAuth. Ils ou elles doivent également mettre à jour leurs applications clientes afin d’utiliser les nouvelles informations d’identification de serveur à serveur OAuth. <ul><li>[Migration des informations d’identification du compte de service (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guide de mise en œuvre pour les nouvelles et les anciennes applications avec OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilisation des nouvelles informations d’identification de serveur à serveur OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Questions fréquentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

Pour connaître les dernières mises à jour des versions d’AppMeasurement (version 2.25.0), reportez-vous aux [Notes de mise à jour d’AppMeasurement pour JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=fr).


## Ressources connexes

* [Notes de mise à jour précédentes pour 2023](/help/release-notes/2023.md)
* [Notes de mise à jour de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=fr)
* [Notes de mise à jour de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* Dernières mises à jour des [produits Adobe Experience Cloud](https://business.adobe.com/fr/products/adobe-experience-cloud-products.html)
