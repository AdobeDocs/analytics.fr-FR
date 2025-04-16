---
title: Notes de mise à jour actuelles d’Adobe Analytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: e2e387f20d5e5732ec1d7eb67a0c81df95e07a55
workflow-type: tm+mt
source-wordcount: '663'
ht-degree: 62%

---

# Notes de mise à jour actuelles d’Adobe Analytics (version d’avril 2025)

**Dernière mise à jour** : jeudi 16 avril 2025

Ces notes de mise à jour portent sur la période du 26 mars à mai 2025. Les mises à jour d’Adobe Analytics fonctionnent sur un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Nouvelles fonctionnalités ou améliorations {#features}

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Inventaire Analytics** | Cette page présente une vue d’ensemble complète de votre environnement Adobe Analytics, y compris le nombre de projets et de composants, les suites de rapports, les utilisateurs et utilisatrices, etc. En automatisant le processus d’inventaire, vous comprendrez rapidement l’effort nécessaire pour passer d’Adobe Analytics à Customer Journey Analytics. Cela rendra la transition plus facile et plus rapide. [En savoir plus](https://experienceleague.adobe.com/fr/docs/analytics/admin/admin-tools/analytics-inventory) |  | 26 mars 2025 |
| **Dimensions Data Warehouse uniquement** | Sur la base des commentaires des clients, nous avons décidé de réévaluer. Nous ne publierons pas la fonctionnalité de dimensions automatiques réservées à Data Warehouse comme annoncé précédemment. | | À confirmer |

## Correctifs dans Adobe Analytics

**A4T** : AN-370625 ; AN-371279 ; AN-371351
**Outils d’administration** : AN-365072 ; AN-371303
**Analysis Workspace** : AN-363831 ; AN-369554
**Classifications** : AN-370519 ; AN-370727 ; AN-370827 ; AN-370941 ; AN-370995 ; AN-371377 ; AN-371597 ; AN-371868 ; AN-371869 ; AN-372510 ; AN-372650 ; AN-373164 ; AN-373300 ; AN-373308 ; AN-373592
**Collecte de données** : AN-371877
**Flux de données** : AN-368676 ; AN-370225 ; AN-370514 ; AN-370521 ; AN-370687 ; AN-370761 ; AN-370911 ; AN-371047 ; AN-371542 ; AN-371627 ; AN-371746 ; AN-372708 ; AN-373068 ; AN-373179 ; AN-
**Data Warehouse** : AN-366649 ; AN-369817 ; AN-370705 ; AN-371127 ; AN-371995 ; AN-372596 ; AN-372940
**Canaux marketing** : AN-372308
**Application mobile** : AN-370287 ; AN-371335 ; AN-371374
**Platform** : AN-369510 ; AN-370435 ; AN-372150
**Report Builder**: AN-369830; AN-371395; AN-372983

## Avis importants pour les administrateurs d’Adobe Analytics {#admin}

| Avis | Date d’ajout ou de mise à jour | Description |
| ----------- | ---------- | ---------- |
| S.O. |  |  |

## Avis de fin de vie {#eol}

| Produit ou fonctionnalité en fin de vie | Date d’ajout ou de mise à jour | Description |
| --- | --- | --- |
| **Accès via les domaines hérités ou via l’authentification unique héritée** | vendredi 10 avril 2025 | Adobe prévoit de mettre à jour la manière dont les utilisateurs accèdent à Adobe Analytics afin d’améliorer la sécurité et de rationaliser votre expérience de connexion. Dans le cadre de cette opération, l’accès par le biais des domaines hérités ou de l’authentification unique héritée, y compris `my.omniture.com`, sera définitivement arrêté le 2 **janvier 2026**. Passée cette date, les identifiants de connexion et le SSO hérités ne fonctionneront plus. Tous les utilisateurs devront se connecter via `experience.adobe.com` à l’aide de leur identifiant Adobe Experience Cloud. Si vous avez besoin d’aide avec votre Experience Cloud ID, contactez l’administrateur Adobe Analytics de votre entreprise ou l’[Assistance clientèle Adobe](https://helpx.adobe.com/contact.html). |
| **Migration vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O** | 17 janvier 2025 | Les clients et clientes de l’API Adobe Analytics et de Livestream qui utilisent les informations d’identification JWT d’Adobe I/O doivent migrer vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O avant le **30 juin 2025**. Adobe I/O n’autorisera pas la création d’informations d’identification JWT à compter du 1er mai 2024. Les clients et clientes utilisant JWT doivent créer des informations d’identification de serveur à serveur OAuth ou migrer leurs informations d’identification JWT existantes vers des informations d’identification de serveur à serveur OAuth. Ils ou elles doivent également mettre à jour leurs applications clientes afin d’utiliser les nouvelles informations d’identification de serveur à serveur OAuth. <ul><li>[Migration des informations d’identification du compte de service (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guide de mise en œuvre pour les nouvelles et les anciennes applications avec OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilisation des nouvelles informations d’identification de serveur à serveur OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Questions fréquentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **Abandon de l’API Adobe Analytics (version 1.4)** | 17 juillet 2024 | Le **12 août 2026**, les services d’API hérités d’Analytics suivants arriveront en fin de vie et seront fermés. Les intégrations actuelles créées à l’aide de ces services cesseront de fonctionner :<ul><li>API Adobe Analytics (version 1.4)</li><li>Authentification WSSE Adobe Analytics</li></ul><p>Les intégrations qui utilisent l’API Adobe Analytics (version 1.4) doivent migrer vers l’[API Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), tandis que les intégrations WSSE doivent migrer vers un protocole d’authentification basé sur OAuth dans [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Pour obtenir des réponses aux questions courantes et d’autres conseils, reportez-vous à la [FAQ sur la fin de vie des API Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md).</p> |


## AppMeasurement

Pour connaître les dernières mises à jour des versions d’AppMeasurement, reportez-vous aux [notes de mise à jour d’AppMeasurement](https://github.com/adobe/appmeasurement/releases).


## Ressources connexes

* [Notes de mise à jour précédentes pour 2025](/help/release-notes/2025.md)
* [Notes de mise à jour de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=fr)
* [Notes de mise à jour du module complémentaire Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* Dernières mises à jour des [produits Adobe Experience Cloud](https://business.adobe.com/products/adobe-experience-cloud-products.html)
