---
title: Dernières notes de mise à jour dʼAnalytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: f996448224ffebd57023c8d8e4eeeccb4d6e2a47
workflow-type: ht
source-wordcount: '920'
ht-degree: 100%

---

# Notes de mise à jour actuelles d’Adobe Analytics (Juillet 2023)

**Dernière mise à jour** : 10 juillet 2023

Les mises à jour dʼAdobe Analytics suivent une [modèle de diffusion continue](releases.md), ce qui permet un déploiement plus flexible et progressif des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Nouvelles fonctionnalités ou améliorations {#features}

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Configuration des emplacements de stockage du compte cloud pour l’ingestion de données de classification** | Vous pouvez désormais gérer les emplacements de stockage des comptes Cloud utilisés pour l’automatisation des jeux de classifications. [En savoir plus](/help/components/locations/configure-import-accounts.md)<p> | S.O. | 10 juillet 2023 |
| **Améliorations du filtre de réparation des données** | Trois améliorations de filtrage ont été ajoutées à la réparation des données :<ul><li>Filtrez selon une variable pour modifier une seconde variable. Par exemple, si `eVar2` contient « @ », supprimez `eVar3`.</li><li>Filtre de valeurs numériques ou non-numériques</li><li>Appliquez plusieurs filtres avec un ET. Par exemple, où `eVar2="a"` ET `eVar3="b"`</li></ul>[En savoir plus](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/) | 21 juin 2023 | 12 juillet 2023 |
| **Destinations sécurisées pour l’export des flux de données** | Les flux de données peuvent désormais être envoyés vers les destinations d’espace de stockage suivantes :<ul><li>Amazon S3</li><li>RBAC Azure</li><li>SAS Azure</li><li>Google Cloud Platform</li></ul>Les destinations auparavant disponibles (FTP, SFTP, S3 et Azure Blob) ne sont plus recommandées. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/create-feed.html?lang=fr) | 12 juin 2023 | 13 juillet 2023 |
| **Nouvelle variable AppMeasurement** | La variable `decodeLinkParameters` prend en charge les cas Edge où les implémentations codent des caractères multi-octet dans les variables de suivi des liens. La plupart des implémentations nʼont pas besoin de définir cette variable. [En savoir plus](../implement/vars/config-vars/decodelinkparameters.md) |  | 17 juillet 2023 |

{style="table-layout:auto"}

## Correctifs dans Adobe Analytics

AN-307816 ; AN-318111 ; AN-318584 ; AN-318828 ; AN-320440 ; AN-320568 ; AN-320616 ; AN-321013 ; AN-321513 ; AN-321520 ; AN-321757 ; AN-321820 ; AN-321917 ; AN-322034 ; AN-322135 ; AN-322140 ; AN-322142 ; AN-322251 ; AN-322353 ; AN-322378 ; AN-322383 ; AN-322427 ; AN-322458 ; AN-322543 ; AN-322630 ; AN-322637 ; AN-322638 ; AN-322647 ; AN-322728 ; AN-322732 ; AN-322777 ; AN-322817 ; AN-322957 ; AN-322958 ; AN-323035 ; AN-323074 ; AN-323150 ; AN-323196 ; AN-323197 ; AN-323205 ; AN-323206 ; AN-323217 ; AN-323224 ; AN-323225 ; AN-323244 ; AN-323257 ; AN-323277 ; AN-323280 ; AN-323293 ; AN-323309 ; AN-323318 ; AN-323468 ; AN-323476 ; AN-323514 ; AN-323572 ; AN-323592 ; AN-323782 ; AN-323835

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
