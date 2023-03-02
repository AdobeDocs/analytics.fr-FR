---
title: Dernières notes de mise à jour dʼAnalytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 6c6682202e8780ddb9bf96a4bdd61ff0558c9f09
workflow-type: tm+mt
source-wordcount: '1125'
ht-degree: 83%

---

# Notes de mise à jour actuelles d’Adobe Analytics (Février 2023)

**Dernière mise à jour** : le 27 février 2023

Les mises à jour dʼAdobe Analytics suivent une [modèle de diffusion continue](releases.md), ce qui permet un déploiement plus flexible et progressif des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités nouvelles ou mises à jour dans Adobe Analytics

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Mise à jour de l’interface utilisateur pour les libellés de confidentialité des données** | La nouvelle mouture de l’interface simplifie le processus de création, de gestion et de modification des libellés de confidentialité des données pour les composants des suites de rapports. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/data-labels/gdpr-setup-reportsuite.html?lang=fr) | S.O. | 8 février 2023 |
| **Masquer les périodes de comparaison dans les cartes de performance mobiles** | À l’aide du bouton (bascule) **[!UICONTROL Inclure les dates de comparaison]**, vous pouvez afficher ou masquer les dates de comparaison dans les cartes de performance mobiles. | S.O. | 8 février 2023 |
| **Mises à jour du calendrier dans Workspace** | <ul><li>Ancrer les dates du panneau : vous pouvez créer des composants de la période par rapport au calendrier du panneau. [En savoir plus](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#relative-panel-dates).</li><li>Mises à jour des styles de calendrier : les styles de calendrier de l’ensemble de l’interface utilisateur ont été mis à niveau afin de présenter un workflow plus cohérent et facile à utiliser.</li><li>Mises à jour de la formule de calendrier : si vous utilisez des dates relatives, toutes les formules de calendrier refléteront le début de la période du panneau. [En savoir plus](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#formula-relative-dates)</li></ul> | S.O. | 8 février 2023 |
| **Mises à jour des plages de dates des panneaux** | Dans Workspace, nous avons ajouté les améliorations suivantes :<ul><li>À compter de la version de février, les aperçus de composants et de données seront basés sur la période du panneau et non sur les 90 derniers jours. </li><li>Tous les éléments de dimension affichés seront disponibles en fonction de la période du panneau.</li><li>Tous les aperçus de date dans les créateurs de segments et de mesures calculées sont basés sur la période du panneau (sauf si vous y accédez à partir des gestionnaires de composants, qui n’ont pas de panneau associé, ils seront toujours basés sur les 90 derniers jours).</li><li>Tous les aperçus de données affichent des données ou des composants en fonction de la période du panneau.</li></ul> | S.O. | 8 février 2023 |
| **Filtrage des lignes/colonnes pour la diffusion en continu du connecteur source Adobe Analytics** | Le connecteur source Analytics dans Adobe Experience Platform permet désormais de filtrer les données Analytics utilisées pour renseigner les profils dans [Real-Time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=fr). Le filtrage au niveau des lignes permet de réduire le nombre d’événements associés aux profils. Le filtrage au niveau des colonnes contribue à réduire la richesse des événements eux-mêmes, ce qui vous permet d’optimiser l’utilisation des droits sur les profils. Ce filtrage s’applique uniquement aux données envoyées à Real-Time Customer Profile et au [Service d’identités](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=fr). **Le filtrage n’a aucune incidence sur les données envoyées au lac de données en vue de leur utilisation dans des applications telles que Customer Journey Analytics.**. [En savoir plus](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=fr#filtering-for-profile) | S.O. | Resprogrammé au 29 mars 2023 |

{style=&quot;table-layout:auto&quot;}

## Correctifs dans Adobe Analytics  

AN-302282 ; AN-303127 ; AN-303541 ; AN-303550 ; AN-305282 ; AN-306504 ; AN-307351 ; AN-307496 ; AN-307530 ; AN-307947 ; AN-308497 ; AN- ; AN-308610 ; AN-308777 ; AN-308994 ; AN-309143 ; AN-309404 ; AN-309414 ; AN-309445 ; AN-309575 ; AN-309630 ; AN-309658 ; AN-309690 ; AN-309742 ; AN-309861 ; AN-309967 ; AN-309973 ; AN-310059 ; AN-310132 ; AN-310168 ; AN-310238 ; AN-310241 ; AN-310301 ; AN-310318 ; AN-310324 ; AN-310335 ; AN-310338 ; AN-310460 ; AN-310500 ; AN-310684 ; AN-310690 ; AN-311010 ; AN-311022 ; AN-311043 ; AN-311125 ; AN-311250 ; AN-311370 ; AN-311458 ;

## Avis importants pour les administrateurs d’Adobe Analytics

| Avis | Date d’ajout  ou de mise à jour | Description |
| ----------- | ---------- | ---------- |
| **Mise à jour des recherches d’appareils en raison des indications du client Google** | 27 février 2023 | L’utilisation des conseils aux clients, prévue pour le 16 février 2023, a été reportée afin de mieux garantir la qualité des recherches d’appareils à l’aide de conseils. Nous passerons à la première phase de la version pour la prise en charge des conseils aux clients le 27 février 2023. Si tout se passe bien, nous passerons à la deuxième et dernière phase de la version le jeudi 2 mars 2023. [En savoir plus](/help/technotes/client-hints.md). |
| **Disponibilité du connecteur source Analytics** | 15 février 2023 | Le 28 février 2023, le connecteur source Analytics sera disponible dans le nouveau centre de données Adobe Experience Platform situé au Canada. |
| **Migration automatique vers l’architecture du jeu de classifications** | 8 février 2023 | Au cours des prochains mois, Adobe prévoit de migrer toutes les classifications de toutes les organisations vers l’architecture de classification la plus récente. La fin de la migration est estimée en mai 2023. Aucune action de la part du client ou de la cliente n’est requise et aucun temps d’arrêt n’est attendu. Cette nouvelle architecture présente de nombreux avantages, notamment :<ul><li>Réduction significative du temps de traitement (72 heures → 24 heures)</li><li>L’interface utilisateur des [Jeux de classifications](/help/components/classifications/sets/overview.md) peut être utilisée</li><li>L’option permettant d’utiliser à l’avenir les données de classification dans Adobe Experience Platform via le [Connecteur source Adobe Analytics pour les données de classification](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html)</li></ul>Notez les modifications suivantes qui peuvent avoir un impact sur le workflow de votre entreprise :<ul><li>Lors de l’utilisation du navigateur ou de l’importation FTP, « [!UICONTROL Remplacer en cas de conflit] » est toujours activé.</li><li>Lors de l’utilisation du navigateur ou de l’importation FTP, l’option permettant d’exporter immédiatement après l’importation n’est plus prise en charge.</li><li>Le point d’entrée `GetDimensions` de l’API Analytics 2.0 renvoie désormais des identifiants de chaîne pour les classifications au lieu des identifiants numériques. Les identifiants numériques peuvent toujours être utilisés, mais Adobe recommande d’utiliser les nouveaux identifiants de chaîne si possible. Les identifiants numériques peuvent être récupérés à l’aide du paramètre de chaîne de requête `?expansion=hidden`.</li></ul>Si vous souhaitez obtenir un calendrier de migration plus précis pour votre organisation ou pour toute autre question, contactez l’assistance clientèle d’Adobe. [En savoir plus](/help/components/classifications/sets/overview.md). |

{style=&quot;table-layout:auto&quot;}

## Avis de fin de vie

| Produit ou fonctionnalité en fin de vie | Date d’ajout ou de mise à jour | Description |
| --- | --- | --- |
| **Fin de vie de certaines fonctionnalités de planification dans Reports &amp; Analytics et Report Builder** | 9 février 2023 | Les fonctionnalités de planification suivantes ont été abandonnées le 31 janvier 2023 :<ul><li>L’option « se terminent après x occurrences » pour les tâches horaires dans Report Builder</li><li>La possibilité de planifier de nouveaux rapports et de télécharger des extractions de données dans Reports and Analytics</li></ul><p>**Remarque** : nous avions décidé d’abandonner ces fonctionnalités en avril 2022 avant de changer d’avis. Nous avons également envoyé une notification indiquant que ces fonctionnalités étaient temporairement restaurées et qu’elles seraient abandonnées pour de bon le 31 janvier 2023. |
| **Abandon de la fonctionnalité [!UICONTROL Listes de publication]** | 29 septembre 2022 | Dans le cadre de la fin de vie de Reports &amp; Analytics, les listes de publication sont programmées pour atteindre la fin de vie en **décembre 2023**. Vous ne pourrez pas créer de listes de publication ou y accéder pour envoyer ou planifier des projets Analysis Workspace. |
| **Fin de vie de Data Workbench** | 14 septembre 2022 | Adobe a l’intention d’abandonner Data Workbench à compter du **31 décembre 2023**. Consultez l’[annonce de fin de vie du Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=fr) pour plus d’informations. Contactez le gestionnaire de compte Adobe de votre entreprise pour toute question. |
| **Fin de vie de [!DNL Reports & Analytics]** | 4 janvier 2022 | À compter du **31 décembre 2023**, Adobe prévoit dʼabandonner [!DNL Reports & Analytics] et ses rapports et fonctionnalités associés. [!DNL Reports & Analytics] sʼappuie sur des rapports, des visualisations et des technologies sous-jacentes qui ne répondent plus aux normes technologiques dʼAdobe. La plupart des fonctionnalités de [!DNL Reports & Analytics] sont disponibles dans [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=fr). Depuis la publication d’Analysis Workspace en 2015, les fonctionnalités de [!DNL Reports & Analytics] ont migré vers Analysis Workspace, de telle sorte quʼun seuil de parité en matière de workflow a été atteint. [Cet avis](https://spark.adobe.com/page/6WnF8JK6IRDhf/) décrit le processus de fin de vie. |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

Pour connaître les dernières mises à jour des versions d’AppMeasurement (version 2.23.0), reportez-vous aux [Notes de mise à jour d’AppMeasurement pour JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=fr).


## Ressources connexes

* [Notes de mise à jour précédentes pour 2022](/help/release-notes/2022.md)
* [Notes de mise à jour de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=fr)
* [Notes de mise à jour de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* Dernières mises à jour des [produits Adobe Experience Cloud](https://business.adobe.com/fr/products/adobe-experience-cloud-products.html)
