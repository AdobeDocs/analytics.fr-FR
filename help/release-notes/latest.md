---
title: Dernières notes de mise à jour dʼAnalytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 2ba6ffc7f632975ca16fa02ee79d467d4d53f076
workflow-type: tm+mt
source-wordcount: '1053'
ht-degree: 43%

---

# Notes de mise à jour actuelles d’Adobe Analytics (février 2023)

**Dernière mise à jour** : le 9 février 2023

Les mises à jour dʼAdobe Analytics suivent une [modèle de diffusion continue](releases.md), ce qui permet un déploiement plus flexible et progressif des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités nouvelles ou mises à jour dans Adobe Analytics

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Mise à jour de l’interface utilisateur pour les étiquettes relatives à la Confidentialité des données** | L’interface mise à jour simplifie le processus de création, de gestion et de modification des étiquettes de confidentialité des données pour les composants de la suite de rapports. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/data-labels/gdpr-setup-reportsuite.html?lang=en) | S.O. | 8 février 2023 |
| **Masquage des plages de dates de comparaison dans les Fiches d’évaluation mobiles** | Avec les Fiches d’évaluation mobiles, vous pouvez activer/désactiver la variable **[!UICONTROL Inclure des dates de comparaison]** pour afficher ou masquer les dates de comparaison. | S.O. | 8 février 2023 |
| **Mises à jour du calendrier dans Workspace** | <ul><li>Dates du panneau d’ancrage : Vous pouvez définir les composants de période par rapport au calendrier du panneau. [En savoir plus](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#relative-panel-dates)</li><li>Mises à jour de style du calendrier : Les styles de calendrier de l’ensemble de l’interface utilisateur ont été mis à niveau afin de présenter un workflow plus cohérent et plus facile à utiliser.</li><li>Mises à jour de la formule du calendrier : Si vous utilisez des dates relatives, toutes les formules de calendrier refléteront le début de la période du panneau. [En savoir plus](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#formula-relative-dates)</li></ul> | S.O. | 8 février 2023 |
| **Filtrage des lignes/colonnes pour la diffusion en continu du connecteur source Adobe Analytics** | Le connecteur source Analytics dans Adobe Experience Platform permet désormais de filtrer les données Analytics utilisées pour renseigner les profils dans [Profil client en temps réel](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=fr). Le filtrage au niveau des lignes permet de réduire le nombre d’événements associés aux profils. Le filtrage au niveau des colonnes contribue à réduire la richesse des événements eux-mêmes, ce qui vous permet d’optimiser l’utilisation des droits sur les profils. Ce filtrage s’applique uniquement aux données envoyées à Real-time Customer Profile et [Identity Service](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=fr). **Le filtrage n’a aucune incidence sur les données envoyées au lac de données en vue de leur utilisation dans des applications telles que Customer Journey Analytics.**. [En savoir plus](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en#filtering-for-profile) | S.O. | 22 février 2023 |

{style=&quot;table-layout:auto&quot;}

## Correctifs dans Adobe Analytics

-302282 ; AN-303127 ; AN-303541 ; AN-303550 ; AN-305282 ; AN-306504 ; AN-307351 ; AN-307496 ; AN-307530 ; AN-307947 ; AN-308497 ; AN- ; AN-308610 ; AN-308777 ; AN-308994 ; AN-309143 ; AN-309404 ; AN-309414 ; AN-309445 ; AN-309575 ; AN-309630 ; AN-309658 ; AN-309690 ; AN-309742 ; AN-309861 ; AN-309967 ; AN-309973 ; AN-310059 ; AN-310132 ; AN-310168 ; AN-310238 ; AN-310241 ; AN-310301 ; AN-310318 ; AN-310324 ; AN-310335 ; AN-310338 ; AN-310460 ; AN-310500 ; AN-310684 ; AN-310690 ; AN-311010 ; AN-311022 ; AN-311043 ; AN-311125 ; AN-311250 ; AN-311370 ; AN-311458

## Avis importants pour les administrateurs d’Adobe Analytics

| Avis | Date d’ajout ou de mise à jour | Description |
| ----------- | ---------- | ---------- |
| **Migration automatique vers l’architecture du jeu de classifications** | 8 février 2023 | Au cours des prochains mois, Adobe prévoit de migrer toutes les classifications de toutes les organisations vers la dernière architecture de classification. La migration des derniers clients est estimée pour mai 2023. Aucune action de la part du client n’est requise et aucun temps d’arrêt n’est attendu. Cette nouvelle architecture présente de nombreux avantages, notamment :<ul><li>Réduction significative du temps de traitement (72 heures → 24 heures)</li><li>La possibilité d’utiliser la variable [Jeux de classifications](/help/components/classifications/sets/overview.md) Interface utilisateur</li><li>L’option permettant d’utiliser des données de classification dans Adobe Experience Platform à l’avenir via le [Connecteur source Adobe Analytics pour les données de classification](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html)</li></ul>Notez les modifications suivantes qui peuvent avoir un impact potentiel sur le workflow de votre entreprise :<ul><li>Lors de l’utilisation du navigateur ou de l’importation FTP,[!UICONTROL Remplacer en cas de conflit]&quot; est toujours activé.</li><li>Lorsque vous utilisez le navigateur ou l’importation FTP, l’option permettant d’exporter immédiatement après l’importation n’est plus prise en charge.</li><li>API Analytics 2.0 `GetDimensions` Le point de terminaison renvoie désormais des identifiants de chaîne pour les classifications au lieu des identifiants numériques. Les identifiants numériques peuvent toujours être utilisés, mais Adobe recommande d’utiliser les nouveaux identifiants de chaîne si possible. Les identifiants numériques peuvent être récupérés à l’aide de la variable `?expansion=hidden` paramètre de chaîne de requête.</li></ul>Contactez l’assistance clientèle d’Adobe si vous souhaitez un planning de migration plus spécifique pour votre entreprise ou si vous avez des questions/préoccupations concernant cette migration. [En savoir plus](/help/components/classifications/sets/overview.md) |
| **Mise à jour des recherches d’appareils en raison des indications du client Google** | 25 janvier 2023 | L’utilisation des conseils du client dans la recherche de périphérique démarrera le **16 février 2023**. <p> <p>Depuis octobre 2022, il est possible de collecter les conseils du client avec le SDK Web ou les bibliothèques JavaScript AppMeasurement. Mais les indices client ne seront pas intégrés à la recherche d’appareils avant février 2023. À ce moment-là, Adobe commencera à utiliser des conseils client en plus de l’agent utilisateur lors de la génération de certaines informations sur les appareils pour les accès provenant de navigateurs Chrome et Microsoft Edge, par exemple. Cette mesure fait suite au projet de Google qui consiste à réduire progressivement les informations présentées à partir de la chaîne Agent-utilisateur à la place des données transmises par les indications du client. <p> <p>Dans le cadre de cette modification, Adobe utilisera Device Atlas pour toutes les recherches de périphériques liées à la chaîne Agent-utilisateur. [En savoir plus](/help/technotes/client-hints.md) |

{style=&quot;table-layout:auto&quot;}

## Avis de fin de vie (EOL)

| Produit ou fonctionnalité en fin de vie | Date d’ajout ou de mise à jour | Description |
| --- | --- | --- |
| **Abandon de certaines fonctionnalités de planification de Reports &amp; Analytics et de Report Builder** | 9 février 2023 | Les fonctionnalités de planification suivantes ont été abandonnées le 31 janvier 2023 :<ul><li>Option &quot;fin après x occurrences&quot; pour les tâches horaires en Report Builder</li><li>Possibilité de planifier de nouveaux rapports et de télécharger des extractions de données dans Reports and Analytics</li></ul><p>**Remarque**: Nous avons initialement mis fin à ces fonctionnalités en avril 2022, mais avons annulé la modification. Nous avons également envoyé une notification indiquant que ces fonctionnalités étaient temporairement restaurées et qu’elles seraient arrêtées le 31 janvier 2023. |
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
