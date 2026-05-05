---
title: Notes de mise à jour actuelles d’Adobe Analytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 6aa5bc2679a367d050e0d67c0621943f9893d0e0
workflow-type: tm+mt
source-wordcount: '1240'
ht-degree: 79%

---

# Notes de mise à jour actuelle d’Adobe Analytics (avril 2026)

**Dernière mise à jour**: 22 avril 2026

Ces notes de mise à jour couvrent la période des versions d’avril 2026. Les mises à jour d’Adobe Analytics fonctionnent sur un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Nouvelles fonctionnalités ou améliorations {#features}

| Fonctionnalité et description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ---- |
| **Serveurs MCP pour Adobe Analytics** <br/>Les serveurs MCP (Model Context Protocol) d’Analytics permettent de connecter un client MCP pris en charge à Adobe Analytics. Une fois connecté, votre client MCP peut appeler des outils spécifiques au produit pour récupérer les données, exécuter des requêtes ou effectuer des opérations prises en charge dans le cadre d’un processus LLM ou d’un processus agentique. Pour plus d’informations, voir [Serveurs MCP Analytics](https://developer.adobe.com/analytics-mcp/docs/).<p>Si vous avez utilisé ces serveurs MCP pendant la période bêta, notez qu’il existe différentes URL entre les points d’entrée bêta et de production. Veillez à ce que tous les workflows d’agent créés pendant la période bêta soient mis à jour afin d’utiliser les points d’entrée de production avant le 31 mai.</p> | | 5 Mai 2026 |
| **Services de médias en streaming : prise en charge des données de planning** <br/>Vous pouvez désormais charger des données planifiées antérieures de contenu de médias en streaming et en direct afin de suivre l’audience plus facilement et avec plus de précision.<p>Les éléments suivants sont des exemples de contenu en direct qui sont pris en charge avec le chargement de données de planning :</p><ul><li>Plateformes FAST (Free Ad Supported TV)</li><li>Flux locaux</li><li>Sports en direct</li></ul><p>Le chargement des données de planning vous permet de suivre les audiences des programmes individuels qui ont été diffusés pendant la période que vous avez indiquée dans le fichier de chargement. Vous pouvez même recueillir des données d’audience pour des sujets ou des segments de programme spécifiques.</p><p>Ces fonctionnalités sont disponibles quelle que soit la manière dont vous avez mis en œuvre Streaming Media Collection.</p><p>Auparavant, il était difficile de relier avec précision une session donnée à des programmes spécifiques lors de l’analyse du contenu en direct, et il n’était pas possible de relier une session donnée à des sujets individuels ou à des segments de programmes.</p><p>Pour plus d’informations, voir [Charger des données de planning pour suivre le contenu en direct](https://experienceleague.adobe.com/fr/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 octobre 2025 | Premier semestre 2026<p>(Version initialement prévue pour le 29 octobre 2025)</p> |
| **Formatages supplémentaires des périodes de l’API**<br/> Deux nouveaux formats sont désormais pris en charge pour spécifier des périodes dans les demandes de rapport de l’API Analytics 2.0. L’un est une formule de date et l’autre un format mixte. [En savoir plus](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/#date-range-field--supported-formats) | | Mars 2026 |
| **Dimension facultative dans les demandes de rapport de l’API**<br/> Aucun objet de dimension n’est requis dans les demandes d’API de rapport. Si aucune dimension n’est spécifiée, la réponse affiche les données d’un rapport Totaux. [En savoir plus](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/#using-dimension-in-report-payload-requests) | | Mars 2026 |
| **Rapport API avancé avec tendance par date**<br/> Nouveau guide de rapport avancé avec tendance par date de l’API Adobe Analytics 2.0. Créez des rapports API de tendance par date avancés à l’aide de segments et de comparaisons de périodes. [En savoir plus](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/advanced/) | | Mars 2026 |

## Correctifs dans Adobe Analytics

**Activity Map**:
**&#x200B;**&#x200B;: AN-442813, AN-442410, AN-441943, AN-441717, AN-434855, AN-431409, AN-429777, AN-429048, AN-428892, AN-428189, AN-425215
**Classifications** : AN-443453, AN-443275, AN-443148, AN-442906, AN-442232, AN-442207, AN-442148, AN-442133, AN-441937, AN-441901, AN-441807, AN-441671, AN-441333, AN-441302, AN-441149, AN-441132, AN-441085, AN-441048, AN-440846, AN-440727, AN-440716 440511 440496 432100
**Flux de données et Data Warehouse** : AN-442211, AN-441719, AN-441183, AN-441011, AN-440625, AN-438953
**Migration** : AN-442467, AN-440380, AN-440357
**Exports** :
**&#x200B;**&#x200B;: AN-441136, AN-438147, AN-425150
**Reporting** : AN-441506, AN-440919, AN-440545, AN-440300
**Suites de rapports** : AN-439429, AN-439423, AN-430988
**Rapports planifiés** :
**Segmentation** :
**Autre** : AN-423359, AN-406242, AN-397985


## Avis de fin de vie {#eol}

| Produit ou fonctionnalité en fin de vie | Date d’ajout ou de mise à jour | Description |
| --- | --- | --- |
| **Améliorations du traitement Livestream** | jeudi 14 janvier 2026 | Adobe prévoit d’apporter des améliorations et des modifications au formatage des payloads LiveStream. Ces mises à jour offrent une meilleure parité entre LiveStream et d’autres fonctionnalités d’Adobe Analytics, telles qu’Analysis Workspace. Un point d’entrée de prévisualisation est disponible et vous permet de tester les modifications planifiées. Consultez les [notes de mise à jour de LiveStream](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/release-notes/) pour obtenir la liste complète des modifications et les détails sur les points d’entrée de prévisualisation. Adobe prévoit une transition définitive vers le format de payload mis à jour le 13 avril 2026. |
| **Suppression des suites de chiffrement TLS 1.2** | 11 février 2026 | Avis aux administrateurs et administratrices : Adobe prévoit de supprimer la prise en charge des suites de chiffrement TLS 1.2 suivantes des serveurs de collecte de données Adobe le 27 mai 2026.<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_GCM_SHA256`</li><li>`TLS_RSA_WITH_AES_256_GCM_SHA384`</li></ul><p>Aucune action du client ou de la cliente n’est requise pour la plupart des implémentations. Cette modification affecte principalement les données Analytics envoyées à partir d’applications natives héritées qui utilisent des bibliothèques TLS obsolètes, ainsi qu’un petit nombre de visiteurs et visiteuses web sur des navigateurs ou des systèmes d’exploitation obsolètes. La suppression de la prise en charge de ces suites de chiffrement améliore la sécurité et aligne Adobe sur les normes de chiffrement modernes. Moins de 0,1 % du trafic de collecte de données repose actuellement sur ces suites de chiffrement.</p> |
| **Report Builder hérité** | 18 juin 2025 | L’ancien module complémentaire Report Builder sera supprimé en juin 2026. Tous les utilisateurs et utilisatrices doivent commencer à mettre à niveau leurs anciens classeurs vers le [nouveau Report Builder](/help/analyze/report-builder/rb-overview.md). Le nouveau Report Builder est disponible pour les clientes et clients d’Adobe Analytics et de Customer Journey Analytics. Il assure la [quasi-parité des fonctionnalités](/help/analyze/report-builder/convert-workbooks.md#unsupported), et propose de nombreuses nouvelles fonctionnalités pratiques et des améliorations de l’interface d’utilisation. Pour faciliter le processus de mise à niveau, le nouveau Report Builder comprend une fonction de conversion facile des classeurs. Le nouveau Report Builder n’est disponible que sous forme de module complémentaire dans Microsoft Store. De nombreuses organisations exigent un processus d’approbation interne avant que le module complémentaire ne soit mis à la disposition des utilisateurs et utilisatrices. Prévoyez suffisamment de temps pour ce processus et commencez à travailler dès maintenant avec votre organisation afin de disposer de suffisamment de temps pour mettre à niveau vos classeurs avant la date de fin de validité. |
| **Accès via les domaines hérités ou via l’authentification SSO héritée** | 10 avril 2025 | Adobe prévoit de mettre à jour la manière dont les utilisateurs et utilisatrices accèdent à Adobe Analytics afin d’améliorer la sécurité et de rationaliser votre expérience de connexion. Dans le cadre de cette opération, l’accès par le biais des domaines hérités ou de l’authentification SSO héritée, y compris `my.omniture.com`, sera définitivement arrêté le **2 janvier 2026**. Après cette date, les identifiants de connexion hérités et l’authentification SSO héritée ne fonctionneront plus. Tous les utilisateurs et utilisatrices devront se connecter via `experience.adobe.com` à l’aide de leurs identifiants Adobe Experience Cloud. Si vous avez besoin d’aide avec votre Experience Cloud ID, contactez l’administration Adobe Analytics de votre entreprise ou l’[Assistance clientèle Adobe](https://helpx.adobe.com/contact.html?lang=fr). |
| **API Adobe Analytics (version 1.4)** | 17 juillet 2024 | Le **12 août 2026**, les services d’API hérités d’Analytics suivants arriveront en fin de vie et seront fermés. Les intégrations actuelles créées à l’aide de ces services cesseront de fonctionner :<ul><li>API Adobe Analytics (version 1.4)</li><li>Authentification WSSE Adobe Analytics</li></ul><p>Les intégrations qui utilisent l’API Adobe Analytics (version 1.4) doivent migrer vers l’[API Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/?lang=fr), tandis que les intégrations WSSE doivent migrer vers un protocole d’authentification basé sur OAuth dans [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Pour obtenir des réponses aux questions courantes et d’autres conseils, reportez-vous à la [FAQ sur la fin de vie des API Adobe Analytics 1.4](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/).</p> |


## AppMeasurement

Pour connaître les dernières mises à jour des versions d’AppMeasurement, reportez-vous aux [notes de mise à jour d’AppMeasurement](https://github.com/adobe/appmeasurement/releases).


## Ressources connexes

* [Notes de mise à jour précédentes pour 2025](/help/release-notes/2025.md)
* [Notes de mise à jour de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=fr)
* [Notes de mise à jour des services de streaming multimédia](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* Dernières mises à jour des [produits Adobe Experience Cloud](https://business.adobe.com/fr/products/adobe-experience-cloud-products.html)
