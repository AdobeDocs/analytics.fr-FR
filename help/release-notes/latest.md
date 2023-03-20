---
title: Dernières notes de mise à jour dʼAnalytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: ca99382a39644dc422baaf7dbd5c4d95942455af
workflow-type: tm+mt
source-wordcount: '1208'
ht-degree: 88%

---

# Notes de mise à jour actuelles d’Adobe Analytics (Mars 2023)

**Dernière mise à jour** : le 10 mars 2023

Les mises à jour dʼAdobe Analytics suivent une [modèle de diffusion continue](releases.md), ce qui permet un déploiement plus flexible et progressif des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités nouvelles ou mises à jour dans Adobe Analytics {#features}

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Dictionnaire de données dans Analysis Workspace** | Le dictionnaire de données permet aux utilisateurs et utilisatrices, et aux administrateurs et administratrices, de suivre, de gérer et de mieux comprendre les composants (dimensions, mesures) dans leur environnement Analytics. [En savoir plus](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) | 15 mars 2023 | 29 mars 2023 |
| **Données dans les tableaux de bord mobiles** | Les données vous permettent d’ajouter plusieurs vues détaillées et personnalisables aux vignettes dans les projets de carte de performance mobile. Utilisez les données pour mieux comprendre les principaux moteurs de recherche, les mesures connexes et les différentes étapes du parcours client. Vous pouvez facilement parcourir ces vues pour mieux comprendre l’ensemble des données de vos mesures clés. [En savoir plus](/help/analyze/mobile-app/create-scorecard.md#create-data-story) | S.O. | 8 mars 2023 |
| **Dates d’expiration des projets planifiés** | Vous pouvez définir des dates d’expiration maximales allant jusqu’à un an pour les projets planifiés, quelle que soit la fréquence de planification. | S.O. | 8 mars 2023 |
| **Partage de liens pour les projets (aucune connexion requise)** - Accès réservé à la bêta privée | <p>Vous pouvez désormais partager des liens en lecture seule vers les projets Analysis Workspace avec des personnes qui n’ont pas accès à Adobe Analytics. Vous pouvez partager des liens de projet avec des personnes hors de votre entreprise, ou avec des personnes au sein de votre entreprise qui ne sont pas configurées pour Adobe Analytics. [En savoir plus](/help/analyze/analysis-workspace/curate-share/share-projects.md)</p> <p>Pour accéder à la version bêta privée, contactez l’équipe chargée de votre compte Adobe.</p> | 15 mars 2023 (version bêta privée) | Avril 2023 |
| **Mises à jour des périodes des panneaux** | Dans Workspace, nous avons ajouté les améliorations suivantes :<ul><li>À compter de la version de février, les éléments de dimension et les aperçus de données sont basés sur la période du panneau et non sur les 90 derniers jours. </li><li>Tous les éléments de dimension répertoriés reposent sur les données de la période du panneau. Si un élément de dimension contient des données en dehors de la période, vous pouvez afficher des données supplémentaires au-delà de la période au bas de la liste.</li><li>Les Dimensions qui ne comportent pas de données peuvent être affichées dans le rail de gauche. Cliquez sur Afficher d’autres options pour afficher les éléments de dimension avec les données en dehors de la période du panneau.</li><li>Les aperçus de données dans les créateurs de segments et de mesures calculées sont basés sur la période du panneau, sauf si vous y accédez à partir des gestionnaires de composants, qui n’ont pas de panneau associé et sont toujours basés sur les 90 derniers jours.</li><li>Les aperçus de données affichent des données ou des composants en fonction de la période du panneau.</li></ul> | S.O. | 8 février 2023 |

## Correctifs dans Adobe Analytics

AN-308177 ; AN-308727 ; AN-308846 ; AN-309591 ; AN-310614 ; AN-311544 ; AN-311570 ; AN-311665 ; AN-311948 ; AN-312108 ; AN-312114 ; AN-312142 ; AN-312143 ; AN-312389 ; AN-312391 ; AN-312431 ; AN-312453 ; AN-312454 ; AN-312458 ; AN-312503 ; AN-312533 ; AN-312682 ; AN-312698 ; AN-312714 ; AN-312738 ; AN-312807 ; AN-312829 ; AN-312849 ; AN-312875 ; AN-312980 ; AN-312997 ; AN-313059 ; AN-313077 ; AN-313110 ; AN-313195 ; AN-313196 ; AN-313258 ; AN-313554 ; AN-313580 ; AN-313702 ; AN-313820 ; AN-313844 ; AN-313859 ; AN-313879 ; AN-314273

## Avis importants pour les administrateurs d’Adobe Analytics {#admin}

| Avis | Date d’ajout ou de mise à jour | Description |
| ----------- | ---------- | ---------- |
| **Mise à jour des recherches d’appareils en raison des indications du client Google** | 27 février 2023 | L’utilisation des indications du client ou de la cliente, prévue pour le 16 février 2023, a été reportée afin de mieux garantir la qualité des recherches d’appareils à l’aide d’indications. Nous avons lancé la première phase de la version pour la prise en charge des indications du client ou de la cliente le 27 février 2023. La deuxième et dernière phase de la version a été achevée le jeudi 2 mars 2023. [En savoir plus](/help/technotes/client-hints.md) |
| **Disponibilité du connecteur source Analytics** | 15 février 2023 | Le 28 février 2023, le connecteur source Analytics a été mis à disposition dans le nouveau centre de données Adobe Experience Platform situé au Canada. |
| **Migration automatique vers l’architecture du jeu de classifications** | 8 février 2023 | Au cours des prochains mois, Adobe prévoit de migrer toutes les classifications de toutes les organisations vers l’architecture de classification la plus récente. La fin de la migration est estimée en mai 2023. Aucune action de la part du client ou de la cliente n’est requise et aucun temps d’arrêt n’est attendu. Cette nouvelle architecture présente de nombreux avantages, notamment :<ul><li>Réduction significative du temps de traitement (72 heures → 24 heures)</li><li>L’interface utilisateur des [Jeux de classifications](/help/components/classifications/sets/overview.md) peut être utilisée</li><li>L’option permettant d’utiliser à l’avenir les données de classification dans Adobe Experience Platform via le [Connecteur source Adobe Analytics pour les données de classification](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html?lang=fr)</li></ul>Notez les modifications suivantes qui peuvent avoir un impact sur le workflow de votre entreprise :<ul><li>Lors de l’utilisation du navigateur ou de l’importation FTP, « [!UICONTROL Remplacer en cas de conflit] » est toujours activé.</li><li>Lors de l’utilisation du navigateur ou de l’importation FTP, l’option permettant d’exporter immédiatement après l’importation n’est plus prise en charge.</li><li>Le point d’entrée `GetDimensions` de l’API Analytics 2.0 renvoie désormais des identifiants de chaîne pour les classifications au lieu des identifiants numériques. Les identifiants numériques peuvent toujours être utilisés, mais Adobe recommande d’utiliser les nouveaux identifiants de chaîne si possible. Les identifiants numériques peuvent être récupérés à l’aide du paramètre de chaîne de requête `?expansion=hidden`.</li></ul>Si vous souhaitez obtenir un calendrier de migration plus précis pour votre organisation ou pour toute autre question, contactez l’assistance clientèle d’Adobe. [En savoir plus](/help/components/classifications/sets/overview.md). |

{style="table-layout:auto"}

## Avis de fin de vie {#eol}

| Produit ou fonctionnalité en fin de vie | Date d’ajout ou de mise à jour | Description |
| --- | --- | --- |
| **Fin de vie de [!DNL Reports & Analytics]** | 7 mars 2023 | À compter du **31 décembre 2023**, Adobe prévoit dʼabandonner [!DNL Reports & Analytics] et ses rapports et fonctionnalités associés. [!DNL Reports & Analytics] sʼappuie sur des rapports, des visualisations et des technologies sous-jacentes qui ne répondent plus aux normes technologiques dʼAdobe. La plupart des fonctionnalités de [!DNL Reports & Analytics] sont disponibles dans [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=fr). Depuis la publication d’Analysis Workspace en 2015, les fonctionnalités de [!DNL Reports & Analytics] ont migré vers Analysis Workspace, de telle sorte quʼun seuil de parité en matière de workflow a été atteint. [Cet avis](https://spark.adobe.com/page/6WnF8JK6IRDhf/) décrit le processus de fin de vie.<p>Le 31 décembre 2023, nous allons mettre fin à de nombreuses fonctionnalités Reports &amp; Analytics associées, notamment : Rapports planifiés, Extractions de données et Rapports DL. Après le 31 décembre 2023, les rapports planifiés ne seront plus envoyés. En **avril 2023**, tous les rapports dont l’expiration était planifiée au-delà du 31 décembre 2023 seront automatiquement mis à jour et expireront le 31 décembre 2023. En outre, vous ne pouvez plus planifier les rapports ultérieurs au-delà du 31 décembre 2023. |
| **Fin de vie de la mesure [!UICONTROL Personnes]** | 9 mars 2023 | Avec l’abandon de la fonctionnalité [[!DNL Device Co-op]](https://experienceleague.adobe.com/docs/discontinued/using/device-co-op.html?lang=fr), la mesure Personnes liée à la coopération entre appareils n’est désormais plus pertinente. Le 8 mai 2023, nous supprimerons la variable [!UICONTROL Personnes] mesure. À ce stade, nous redirigerons ses données vers la mesure [!UICONTROL Visiteur unique] afin d’empêcher la ventilation des projets, des segments et des mesures calculées.<p>**Remarque** : la mesure [[!UICONTROL Personnes] liée aux analyses entre appareils](/help/components/metrics/people.md) n’est pas affectée par cette annonce. |
| **Abandon de la fonctionnalité [!UICONTROL Listes de publication]** | 29 septembre 2022 | Dans le cadre de la fin de vie de Reports &amp; Analytics, les [!UICONTROL listes de publication] sont programmées pour atteindre la fin de vie en **décembre 2023**. Vous ne pourrez pas créer de [!UICONTROL listes de publication] ou y accéder pour envoyer ou planifier des projets [!UICONTROL Analysis Workspace]. |
| **Fin de vie de Data Workbench** | 14 septembre 2022 | Adobe a l’intention d’abandonner Data Workbench à compter du **31 décembre 2023**. Consultez l’[annonce de fin de vie du Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=fr) pour plus d’informations. Contactez le gestionnaire de compte Adobe de votre entreprise pour toute question. |
| **Fin de vie de [!DNL Reports & Analytics]** | 4 janvier 2022 | À compter du **31 décembre 2023**, Adobe prévoit dʼabandonner [!DNL Reports & Analytics] et ses rapports et fonctionnalités associés. [!DNL Reports & Analytics] sʼappuie sur des rapports, des visualisations et des technologies sous-jacentes qui ne répondent plus aux normes technologiques dʼAdobe. La plupart des fonctionnalités de [!DNL Reports & Analytics] sont disponibles dans [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=fr). Depuis la publication d’Analysis Workspace en 2015, les fonctionnalités de [!DNL Reports & Analytics] ont migré vers Analysis Workspace, de telle sorte quʼun seuil de parité en matière de workflow a été atteint. [Cet avis](https://spark.adobe.com/page/6WnF8JK6IRDhf/) décrit le processus de fin de vie. |

{style="table-layout:auto"}

## AppMeasurement

Pour connaître les dernières mises à jour des versions d’AppMeasurement (version 2.23.0), reportez-vous aux [Notes de mise à jour d’AppMeasurement pour JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=fr).


## Ressources connexes

* [Notes de mise à jour précédentes pour 2022](/help/release-notes/2022.md)
* [Notes de mise à jour de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=fr)
* [Notes de mise à jour de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* Dernières mises à jour des [produits Adobe Experience Cloud](https://business.adobe.com/fr/products/adobe-experience-cloud-products.html)
