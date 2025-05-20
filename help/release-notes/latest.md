---
title: Notes de mise à jour actuelles d’Adobe Analytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 9c6da2c1ed5bc2c016da16a5bb821f0064e1ae4f
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 61%

---

# Notes de mise à jour actuelles d’Adobe Analytics (version de mai 2025)

**Dernière mise à jour** : jeudi 14 mai 2025

Ces notes de mise à jour couvrent la période allant du xx avril au 18 juin 2025. Les mises à jour d’Adobe Analytics fonctionnent sur un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Nouvelles fonctionnalités ou améliorations {#features}

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Le panneau de gauche d’Analysis Workspace ne s’ouvre plus et se ferme au survol** | Le panneau de gauche d’Analysis Workspace permet d’ajouter des éléments tels que des composants, des panneaux et des visualisations à votre projet. L’option permettant d’ouvrir temporairement le panneau de gauche en pointant sur l’une des icônes à l’extrême gauche n’est plus disponible. Il vous suffit de cliquer sur l’une de ces icônes pour garder le panneau ouvert, puis de cliquer sur la même icône pour le fermer. |  | vendredi 29 mai 2025 |


## Correctifs dans Adobe Analytics

**Alertes** : AN-378351
**Analysis Workspace** : AN-363521 ; AN-367366 ; AN-373575 ; AN-374238 ; AN-374295 ; AN-374382 ; AN-376938 ; AN-377176 ; AN-377467 ; AN-377942
**Transfert de ressources** : AN-373381
**Classifications** : AN-373166 ; AN-373479 ; AN-376074 ; AN-377337 ; AN-377505
**Composants** : AN-314468
**Flux de données** : AN-370241 ; AN-375267 ; AN-376940
**Sources de données** : AN-375259
**Data Warehouse**: AN-370415; AN-372090;
**Platform** : AN-365681 ; AN-372306 ; AN-372616 ;
**Rapports en temps réel** : AN-365681
**Report Builder**: AN-371395
**Segmentation** : AN-373576 ; AN-375858
**Suites de rapports virtuelles** : AN-377948 ; AN-377952
**Règles Vista** : AN-373292

## Avis importants pour les administrateurs d’Adobe Analytics {#admin}

| Avis | Date d’ajout ou de mise à jour | Description |
| ----------- | ---------- | ---------- |
| **Le panneau de gauche d’Analysis Workspace ne s’ouvre plus et se ferme au survol** | Le panneau de gauche d’Analysis Workspace permet d’ajouter des éléments tels que des composants, des panneaux et des visualisations à votre projet. L’option permettant d’ouvrir temporairement le panneau de gauche en pointant sur l’une des icônes à l’extrême gauche n’est plus disponible. Il vous suffit de cliquer sur l’une de ces icônes pour garder le panneau ouvert, puis de cliquer sur la même icône pour le fermer. |  | vendredi 29 mai 2025 |


## Avis de fin de vie {#eol}

| Produit ou fonctionnalité en fin de vie | Date d’ajout ou de mise à jour | Description |
| --- | --- | --- |
| **Accès via les domaines hérités ou via l’authentification SSO héritée** | 10 avril 2025 | Adobe prévoit de mettre à jour la manière dont les utilisateurs et utilisatrices accèdent à Adobe Analytics afin d’améliorer la sécurité et de rationaliser votre expérience de connexion. Dans le cadre de cette opération, l’accès par le biais des domaines hérités ou de l’authentification SSO héritée, y compris `my.omniture.com`, sera définitivement arrêté le **2 janvier 2026**. Après cette date, les identifiants de connexion hérités et l’authentification SSO héritée ne fonctionneront plus. Tous les utilisateurs et utilisatrices devront se connecter via `experience.adobe.com` à l’aide de leurs identifiants Adobe Experience Cloud. Si vous avez besoin d’aide avec votre Experience Cloud ID, contactez l’administration Adobe Analytics de votre entreprise ou l’[Assistance clientèle Adobe](https://helpx.adobe.com/fr/contact.html). |
| **Migration vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O** | 17 janvier 2025 | Les clients et clientes de l’API Adobe Analytics et de Livestream qui utilisent les informations d’identification JWT d’Adobe I/O doivent migrer vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O avant le **30 juin 2025**. Adobe I/O n’autorisera pas la création d’informations d’identification JWT à compter du 1er mai 2024. Les clients et clientes utilisant JWT doivent créer des informations d’identification de serveur à serveur OAuth ou migrer leurs informations d’identification JWT existantes vers des informations d’identification de serveur à serveur OAuth. Ils ou elles doivent également mettre à jour leurs applications clientes afin d’utiliser les nouvelles informations d’identification de serveur à serveur OAuth. <ul><li>[Migration des informations d’identification du compte de service (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration)</li><li>[Guide de mise en œuvre pour les nouvelles et les anciennes applications avec OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation)<li>[Utilisation des nouvelles informations d’identification de serveur à serveur OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation)</li><li>[Questions fréquentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs)</li></ul> |
| **Abandon de l’API Adobe Analytics (version 1.4)** | 17 juillet 2024 | Le **12 août 2026**, les services d’API hérités d’Analytics suivants arriveront en fin de vie et seront fermés. Les intégrations actuelles créées à l’aide de ces services cesseront de fonctionner :<ul><li>API Adobe Analytics (version 1.4)</li><li>Authentification WSSE Adobe Analytics</li></ul><p>Les intégrations qui utilisent l’API Adobe Analytics (version 1.4) doivent migrer vers l’[API Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), tandis que les intégrations WSSE doivent migrer vers un protocole d’authentification basé sur OAuth dans [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Pour obtenir des réponses aux questions courantes et d’autres conseils, reportez-vous à la [FAQ sur la fin de vie des API Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md).</p> |


## AppMeasurement

Pour connaître les dernières mises à jour des versions d’AppMeasurement, reportez-vous aux [notes de mise à jour d’AppMeasurement](https://github.com/adobe/appmeasurement/releases).


## Ressources connexes

* [Notes de mise à jour précédentes pour 2025](/help/release-notes/2025.md)
* [Notes de mise à jour de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=fr)
* [Notes de mise à jour du module complémentaire Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* Dernières mises à jour des [produits Adobe Experience Cloud](https://business.adobe.com/fr/products/adobe-experience-cloud-products.html)
