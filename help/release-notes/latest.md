---
title: Notes de mise à jour actuelles d’Adobe Analytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: d7beee25af3551426eb905f0e727545de068b2d9
workflow-type: ht
source-wordcount: '882'
ht-degree: 100%

---

# Notes de mise à jour actuelles d’Adobe Analytics (version de janvier 2025)

**Dernière mise à jour** : 22 janvier 2024

Ces notes de mise à jour portent sur la période du 15 janvier 2025 à février 2025. Les mises à jour d’Adobe Analytics fonctionnent sur un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Nouvelles fonctionnalités ou améliorations {#features}

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Planification dans le nouveau Report Builder** | La planification vous permet de planifier vos nouveaux classeurs de Report Builder. Elle vous permet également de récupérer les métadonnées des anciennes tâches planifiées lors de la conversion de classeurs hérités. Ainsi, lorsque vous convertissez vos classeurs hérités en nouveaux classeurs et que vous les planifiez, vous les envoyez aux mêmes adresses e-mail et avec la même fréquence que les classeurs hérités. [En savoir plus](/help/analyze/report-builder/schedule-reportbuilder.md) |  | 22 janvier 2025 |
| **Amélioration des rapports (également appelés modèles) dans Analysis Workspace** | Diverses améliorations sont désormais disponibles pour les rapports (également appelés modèles) :<ul><li>Désormais appelés [!UICONTROL modèles] (et non plus [!UICONTROL rapports]).</li><li>Amélioration de l’expérience client pour l’affichage et la recherche de modèles, avec notamment la possibilité d’afficher les modèles dans une vue Colonne ou Carte.</li><li>Nouvel emplacement plus intuitif pour les modèles d’entreprise (sous **[!UICONTROL Espace de travail]** > **[!UICONTROL Modèles]**).</li><li>Auparavant, les modèles d’entreprise étaient accessibles à partir de la boîte de dialogue lors de la création d’un projet.</li><li>D’autres modèles préconfigurés sont disponibles.</li></ul>[En savoir plus](https://experienceleague.adobe.com/fr/docs/analytics/analyze/analysis-workspace/templates/use-templates).<p>Les administrateurs et administratrices peuvent créer des modèles et les enregistrer pour que d’autres personnes de leur société de connexion puissent les utiliser. [En savoir plus](https://experienceleague.adobe.com/fr/docs/analytics/analyze/analysis-workspace/templates/create-templates) | 15 janvier 2025 | 30 janvier 2025 |
| **Période de conservation de l’ID de transaction** | La période de conservation de l’ID de transaction de 90 jours sera étendue à 25 mois en février 2025. La variable `transactionID` identifie de manière unique une transaction afin que l’accès puisse être lié aux données chargées via la fonctionnalité Sources de données. (Lien vers la documentation à suivre) |  | 11 février 2025 |

## Correctifs dans Adobe Analytics

**A4T** : AN-355602, AN-365988
**Activity Map** : AN-365320
**Admin Console** : AN-363884
**Outils d’administration** : AN-356747, AN-358776
**Advertising Analytics** : AN-355488
**Analysis Workspace** : AN-345318, AN-354801, AN-357052, AN-358975, AN-362886, AN-363831, AN-364124, AN-365257, AN-365319, AN-365462, AN-366194
**API Analytics 1.4** : AN-358059
**Classifications** : AN-360049, AN-360424, AN-360745, AN-362208, AN-362345, AN-362560, AN-362576, AN-362633, AN-362653, AN-362762, AN-362815, AN-362881, AN-362885, AN-362973, AN-363343, AN-363558, AN-363860, AN-364239, AN-364480, AN-364451, AN-364528, AN-364548, AN-364552, AN-364585, AN-364598, AN-364643, AN-364715, AN-364912, AN-364997, AN-365081, AN-365189, AN-365197, AN-365203, AN-365431, AN-365647, AN-365794, AN-366546
**Migration des composants** : AN-362236, AN-365429
**Analyse des contributions** : AN-360146
**Flux de données** : AN-356997, AN-362470, AN-362498, AN-362775, AN-363323, AN-363413, AN-363569, AN-364063, AN-364142, AN-364294, AN-364298, AN-364325, AN-364367, AN-364594, AN-364995, AN-365127, AN-365272, AN-365519, AN-365760, AN-366152
**API de réparation des données** : AN-362773, AN-362874
**Sources de données** : AN-360745, AN-362202, AN-364566
**Entrepôt de données** : AN-361447, AN-362616, AN-364524, AN-365108
**Application mobile** : AN-362856, AN-365270
**Alertes de dépassement** : AN-355594; AN-364547
**Plateforme** : AN-358914, AN-360205, AN-362990, AN-364550, AN-365454, AN-365485
**Report Builder** : AN-363478, AN-364433, AN-365610
**Gestionnaire des activités de rapport** : AN-362440
**Segmentation** : AN-359921
**Règles VISTA** : AN-362927

## Avis importants pour les administrateurs d’Adobe Analytics {#admin}

| Avis | Date d’ajout ou de mise à jour | Description |
| ----------- | ---------- | ---------- |
| **La clientèle qui n’utilise pas Campaign n’aura plus accès à Triggers** | 16 octobre 2023 | Le 30 janvier 2025, la clientèle Adobe Analytics qui ne dispose pas d’une licence Adobe Campaign perdra l’accès à la configuration et à l’utilisation de [Triggers](https://experienceleague.adobe.com/fr/docs/core-services/interface/services/triggers). Pour conserver cet accès, il est nécessaire d’acheter Campaign, d’envisager l’arrêt de l’utilisation de Triggers, ou de se tourner vers d’autres outils Adobe proposant des fonctionnalités similaires. |

## Avis de fin de vie {#eol}

| Produit ou fonctionnalité en fin de vie | Date d’ajout ou de mise à jour | Description |
| --- | --- | --- |
| **Migration vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O** | 17 janvier 2025 | Les clients et clientes de l’API Adobe Analytics et de Livestream qui utilisent les informations d’identification JWT d’Adobe I/O doivent migrer vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O avant le **30 juin 2025**. Adobe I/O n’autorisera pas la création d’informations d’identification JWT à compter du 1er mai 2024. Les clients et clientes utilisant JWT doivent créer des informations d’identification de serveur à serveur OAuth ou migrer leurs informations d’identification JWT existantes vers des informations d’identification de serveur à serveur OAuth. Ils ou elles doivent également mettre à jour leurs applications clientes afin d’utiliser les nouvelles informations d’identification de serveur à serveur OAuth. <ul><li>[Migration des informations d’identification du compte de service (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guide de mise en œuvre pour les nouvelles et les anciennes applications avec OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilisation des nouvelles informations d’identification de serveur à serveur OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Questions fréquentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **Abandon de l’API Adobe Analytics (version 1.4)** | 17 juillet 2024 | Le **12 août 2026**, les services d’API hérités d’Analytics suivants arriveront en fin de vie et seront fermés. Les intégrations actuelles créées à l’aide de ces services cesseront de fonctionner :<ul><li>API Adobe Analytics (version 1.4)</li><li>Authentification WSSE Adobe Analytics</li></ul><p>Les intégrations qui utilisent l’API Adobe Analytics (version 1.4) doivent migrer vers l’[API Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), tandis que les intégrations WSSE doivent migrer vers un protocole d’authentification basé sur OAuth dans [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Pour obtenir des réponses aux questions courantes et d’autres conseils, reportez-vous à la [FAQ sur la fin de vie des API Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md).</p> |


## AppMeasurement

Pour connaître les dernières mises à jour des versions d’AppMeasurement (version 2.26.0), reportez-vous aux [Notes de mise à jour d’AppMeasurement pour JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=fr).


## Ressources connexes

* [Notes de mise à jour précédentes pour 2024](/help/release-notes/2024.md)
* [Notes de mise à jour de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=fr)
* [Notes de mise à jour du module complémentaire Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* Dernières mises à jour des [produits Adobe Experience Cloud](https://business.adobe.com/fr/products/adobe-experience-cloud-products.html)
