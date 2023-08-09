---
title: Notes de mise à jour actuelles d’Adobe Analytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 00fd63b7486382da5506d16540bb949c52541c6d
workflow-type: tm+mt
source-wordcount: '895'
ht-degree: 79%

---

# Notes de mise à jour actuelles d’Adobe Analytics (Août 2023)

**Dernière mise à jour** : 9 août 2023

Ces notes de mise à jour portent sur la période du 9 août au 13 septembre 2023. Les mises à jour dʼAdobe Analytics suivent une [modèle de diffusion continue](releases.md), ce qui permet un déploiement plus flexible et progressif des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Nouvelles fonctionnalités ou améliorations {#features}

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Jeux de classifications dans API 2.0** | Fournit les méthodes de l’API Adobe Analytics 2.0 pour enregistrer, supprimer, récupérer, importer et exporter des données de jeu de classifications. | S.O. | 31 août 2023 |
| **Gestionnaire des activités de rapport** | Le Gestionnaire des activités de création de rapports offre aux administrateurs une visibilité détaillée de la consommation de rapports pour chaque suite de rapports, ce qui permet aux administrateurs de diagnostiquer facilement les problèmes de capacité, puis de les résoudre pendant les heures de pointe de la création de rapports. [En savoir plus](/help/admin/admin/reporting-activity.md) | S.O. | 6 septembre 2023 |

{style="table-layout:auto"}

## Correctifs dans Adobe Analytics

* Correction d’un problème en raison duquel les événements personnalisés n’étaient pas chargés. (AN-324163)
* Correction d’un problème qui empêchait la modification des libellés des légendes dans une visualisation. (AN-323246)

AN-315605; AN-316306; AN-317494; AN-317844; AN-320424; AN-; AN-320597; AN-320680; AN-320869; AN-321624; AN-; AN-321693; AN-322009; AN-322244; AN-; AN-; AN-; AN-; AN-; AN-; AN-AN; AN-; AN-; AN-; AN-; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN-AN ; AN- ; AN- ; AN-AN ; AN- ; AN-AN-AN-AN-AN-ET-AN-; AN ; AN-AN-AN-AN-AN-ET-AN-AN AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN-AN ; AN- ; AN- ; AN-AN ; AN- ; AN-AN-AN-AN-AN-ET-AN-; AN ; AN-AN-AN-AN-AN-ET-AN-AN AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN- ; AN-AN ; AN- ; AN-AN- ; AN-AN-AN-AN-AN-AN-


## Avis importants pour les administrateurs d’Adobe Analytics {#admin}

| Remarque | Date d’ajout ou de mise à jour | Description |
| ----------- | ---------- | ---------- |
| **Expiration après 37 mois des ID d’achat et d’événement (sérialisation des événements)** | 10 juillet 2023 | Une prochaine version du moteur de traitement des accès Analytics, prévue pour le **13 juillet 2023**, introduit l’expiration après 37 mois des identifiants d’achat et d’événement (sérialisation des événements). Actuellement, les ID d’achat et d’événement n’expirent jamais dans Adobe Analytics. Dès qu’un ID d’achat ou d’événement est affiché ou utilisé, il sera marqué comme un duplicata lors de tout accès ultérieur, peu importe la date. Avec la nouvelle version du moteur de traitement :<ul><li>Les ID d’achat et d’événement expirent toujours après 37 mois.</li><li>Si 37 mois se sont écoulés depuis que l’ID d’achat ou d’événement a été affiché, il n’est plus considéré comme un duplicata d’achat ou d’événement.</li><li> Si vous « réutilisez » les ID d’achat ou d’événement datant de plus de 37 mois, ils ne sont plus considérés comme des duplicatas.</li></ul> |
| **Migration vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O** | 11 mai 2023 | Les clients et clientes de l’API Adobe Analytics et de Livestream qui utilisent les informations d’identification JWT d’Adobe I/O doivent migrer vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O avant le **1er janvier 2025**. Pour en savoir plus et connaître le calendrier, consultez l’avis de fin de vie dans le tableau ci-dessous. |

{style="table-layout:auto"}

## Avis de fin de vie {#eol}

| Produit ou fonctionnalité en fin de vie | Date d’ajout ou de mise à jour | Description |
| --- | --- | --- |
| **Migration vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O** | 11 mai 2023 | Les clients et clientes de l’API Adobe Analytics et de Livestream qui utilisent les informations d’identification JWT d’Adobe I/O doivent migrer vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O avant le **1er janvier 2025**. Adobe I/O n’autorisera pas la création d’informations d’identification JWT à compter du 1er mai 2024. Les clients et clientes utilisant JWT doivent créer des informations d’identification de serveur à serveur OAuth ou migrer leurs informations d’identification JWT existantes vers des informations d’identification de serveur à serveur OAuth. Ils ou elles doivent également mettre à jour leurs applications clientes afin d’utiliser les nouvelles informations d’identification de serveur à serveur OAuth. <ul><li>[Migration des informations d’identification du compte de service (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guide de mise en œuvre pour les nouvelles et les anciennes applications avec OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilisation des nouvelles informations d’identification de serveur à serveur OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Questions fréquentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **Fin de vie de [!DNL Reports & Analytics]** | 7 mars 2023 | À compter du **31 décembre 2023**, Adobe prévoit dʼabandonner [!DNL Reports & Analytics] et ses rapports et fonctionnalités associés. [!DNL Reports & Analytics] sʼappuie sur des rapports, des visualisations et des technologies sous-jacentes qui ne répondent plus aux normes technologiques dʼAdobe. La plupart des fonctionnalités de [!DNL Reports & Analytics] sont disponibles dans [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=fr). Depuis la publication d’Analysis Workspace en 2015, les fonctionnalités de [!DNL Reports & Analytics] ont migré vers Analysis Workspace, de telle sorte quʼun seuil de parité en matière de workflow a été atteint. [Cet avis](https://spark.adobe.com/page/6WnF8JK6IRDhf/) décrit le processus de fin de vie.<p>Le 31 décembre 2023, nous allons mettre fin à de nombreuses fonctionnalités Reports &amp; Analytics associées, notamment : Rapports planifiés, Extractions de données et Rapports DL. Après le 31 décembre 2023, les rapports planifiés ne seront plus envoyés. En **avril 2023**, tous les rapports dont l’expiration était planifiée au-delà du 31 décembre 2023 seront automatiquement mis à jour et expireront le 31 décembre 2023. En outre, vous ne pouvez plus planifier les rapports ultérieurs au-delà du 31 décembre 2023. |
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
