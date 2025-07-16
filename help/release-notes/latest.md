---
title: Notes de mise à jour actuelles d’Adobe Analytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 00d716f12a7372ca94f09ddfddd7ffb55d4b1dd2
workflow-type: tm+mt
source-wordcount: '755'
ht-degree: 86%

---

# Notes de mise à jour actuelles d’Adobe Analytics (version de juillet 2025)

**Dernière mise à jour** : jeudi 16 juillet 2025

Ces notes de mise à jour couvrent la période du 7 juillet au 15 août 2025. Les mises à jour d’Adobe Analytics fonctionnent sur un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Nouvelles fonctionnalités ou améliorations {#features}

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Champs TNT Livestream avec algorithmes** | Livestream est en cours de renouvellement pour s’assurer que la technologie continue d’être moderne et stable. Dans le cadre de cette actualisation, si votre champ TNT contient un algorithme, nous commencerons à incorporer le champ TNT dans la sortie Livestream. Toutefois, seuls les éléments précédemment pris en charge sont concernés : `campaignId`, `recipeId`, `trafficType`, `actionId` et `actionName`. Le schéma TNT global pour Livestream reste inchangé. |   | 7 juillet 2025 |
| **Mise à jour de la navigation vers l’interface d’utilisation des attributs du client ou de la cliente** | L’interface d’utilisation des attributs du client ou de la cliente est désormais accessible directement depuis le sélecteur d’applications dans Adobe Experience Cloud. | mercredi 1 juillet 2025 | À confirmer |
| **Médias en streaming : prise en charge des données de planning** | Vous pouvez désormais charger des données planifiées antérieures de contenu de médias en streaming et en direct afin de suivre l’audience plus facilement et avec plus de précision. Les éléments suivants sont des exemples de contenu en direct qui sont pris en charge avec le chargement de données de planning :<ul><li>Plateformes FAST (Free Ad Supported TV)</li><li>Flux locaux</li><li>Sports en direct</li></ul>Le chargement des données de planning vous permet de suivre les audiences des programmes individuels qui ont été diffusés pendant la période que vous avez indiquée dans le fichier de chargement. Vous pouvez même recueillir des données d’audience pour des sujets ou des segments de programme spécifiques. Ces fonctionnalités sont disponibles quelle que soit la manière dont vous avez mis en œuvre Streaming Media Collection.<p>Auparavant, il était difficile de relier avec précision une session donnée à des programmes spécifiques lors de l’analyse du contenu en direct, et il n’était pas possible de relier une session donnée à des sujets individuels ou à des segments de programmes. En savoir plus |  | 25 juin 2025 |

## Correctifs dans Adobe Analytics

**Activity Map** : AN-360987
**Analysis Workspace**: AN-378094; AN-380979; AN-382908; AN-387652;
**Classifications** : AN-382412 ; AN-383157 ; AN-384616 ; AN-384803 ; AN-385933 ; AN-387320 ; AN-387351 ; AN-387832 ; AN-387833 ; AN-387839 ; AN-387915 ;
**Collecte de données** : AN-387661
**Flux de données** : AN-375172 ; AN-384369 ; AN-387859 ; AN-387952 ; AN-388155 ;
**Platform** : AN-382813 ; AN-386627 ; AN-386815
**Confidentialité** : AN-384390
**Report Builder**: AN-388035
**Reporting** : AN-380441
**Rapports planifiés** : AN-378280 ; AN-378331
**Comparaison des segments** : AN-368766


## Avis de fin de vie {#eol}

| Produit ou fonctionnalité en fin de vie | Date d’ajout ou de mise à jour | Description |
| --- | --- | --- |
| **Report Builder hérité** | 18 juin 2025 | L’ancien module complémentaire Report Builder sera supprimé en juin 2026. Tous les utilisateurs et utilisatrices doivent commencer à mettre à niveau leurs anciens classeurs vers le [nouveau Report Builder](https://experienceleague.adobe.com/fr/docs/analytics/analyze/report-builder/rb-overview). Le nouveau Report Builder est disponible pour les clientes et clients d’Adobe Analytics et de Customer Journey Analytics. Il assure la [quasi-parité des fonctionnalités](https://experienceleague.adobe.com/fr/docs/analytics/analyze/report-builder/convert-workbooks#unsupported), et propose de nombreuses nouvelles fonctionnalités pratiques et des améliorations de l’interface d’utilisation. Pour faciliter le processus de mise à niveau, le nouveau Report Builder comprend une fonction de conversion facile des classeurs. Le nouveau Report Builder n’est disponible que sous forme de module complémentaire dans Microsoft Store. De nombreuses organisations exigent un processus d’approbation interne avant que le module complémentaire ne soit mis à la disposition des utilisateurs et utilisatrices. Prévoyez suffisamment de temps pour ce processus et commencez à travailler dès maintenant avec votre organisation afin de disposer de suffisamment de temps pour mettre à jour vos classeurs avant la date de fin de validité. |
| **Accès via les domaines hérités ou via l’authentification SSO héritée** | 10 avril 2025 | Adobe prévoit de mettre à jour la manière dont les utilisateurs et utilisatrices accèdent à Adobe Analytics afin d’améliorer la sécurité et de rationaliser votre expérience de connexion. Dans le cadre de cette opération, l’accès par le biais des domaines hérités ou de l’authentification SSO héritée, y compris `my.omniture.com`, sera définitivement arrêté le **2 janvier 2026**. Après cette date, les identifiants de connexion hérités et l’authentification SSO héritée ne fonctionneront plus. Tous les utilisateurs et utilisatrices devront se connecter via `experience.adobe.com` à l’aide de leurs identifiants Adobe Experience Cloud. Si vous avez besoin d’aide avec votre Experience Cloud ID, contactez l’administration Adobe Analytics de votre entreprise ou l’[Assistance clientèle Adobe](https://helpx.adobe.com/fr/contact.html). |
| **API Adobe Analytics (version 1.4)** | 17 juillet 2024 | Le **12 août 2026**, les services d’API hérités d’Analytics suivants arriveront en fin de vie et seront fermés. Les intégrations actuelles créées à l’aide de ces services cesseront de fonctionner :<ul><li>API Adobe Analytics (version 1.4)</li><li>Authentification WSSE Adobe Analytics</li></ul><p>Les intégrations qui utilisent l’API Adobe Analytics (version 1.4) doivent migrer vers l’[API Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), tandis que les intégrations WSSE doivent migrer vers un protocole d’authentification basé sur OAuth dans [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Pour obtenir des réponses aux questions courantes et d’autres conseils, reportez-vous à la [FAQ sur la fin de vie des API Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md).</p> |


## AppMeasurement

Pour connaître les dernières mises à jour des versions d’AppMeasurement, reportez-vous aux [notes de mise à jour d’AppMeasurement](https://github.com/adobe/appmeasurement/releases).


## Ressources connexes

* [Notes de mise à jour précédentes pour 2025](/help/release-notes/2025.md)
* [Notes de mise à jour de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=fr)
* [Notes de mise à jour du module complémentaire Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* Dernières mises à jour des [produits Adobe Experience Cloud](https://business.adobe.com/products/adobe-experience-cloud-products.html?lang=fr)
