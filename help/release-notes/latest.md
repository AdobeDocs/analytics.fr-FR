---
title: Notes de mise à jour actuelles d’Adobe Analytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
TQID: https://experienceleague.adobe.com/yw30Yij2NBaeuWFqxD4-VH1Hysf8dxOpxHUwsFCYEw8
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d095671a-1355-40aa-8b5f-06c33c68080bid: d3cdead0-685a-4489-9250-4bb709942f66id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 2be38df3df510c4e460497be8c085ed2a26b4760
workflow-type: tm+mt
source-wordcount: 1365
ht-degree: 60%

---

# Notes de mise à jour actuelles d’Adobe Analytics (mai 2026)

**Dernière mise à jour** : 13 mai 2026

Ces notes de mise à jour couvrent la période de publication de mai 2026. Les mises à jour d’Adobe Analytics fonctionnent sur un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Nouvelles fonctionnalités ou améliorations {#features}

| Fonctionnalité et description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ---- |
| **Serveurs MCP pour Adobe Analytics** <br/>Les serveurs MCP (Model Context Protocol) d’Analytics permettent de connecter un client MCP pris en charge à Adobe Analytics. Une fois connecté, votre client MCP peut appeler des outils spécifiques au produit pour récupérer les données, exécuter des requêtes ou effectuer des opérations prises en charge dans le cadre d’un processus LLM ou d’un processus agentique. Pour plus d’informations, voir [Serveurs MCP Analytics](https://developer.adobe.com/analytics-mcp/docs/).<p>Si vous avez utilisé ces serveurs MCP pendant la période bêta, notez qu’il existe différentes URL entre les points d’entrée bêta et de production. Veillez à ce que tous les workflows d’agent créés pendant la période bêta soient mis à jour afin d’utiliser les points d’entrée de production avant le 31 mai.</p> | | 5 Mai 2026 |
| Zone de travail de Parcours **dans Adobe Analytics** la zone de travail de Parcours <br/>dans Analysis Workspace est une visualisation qui vous permet d’obtenir des informations détaillées sur un parcours utilisateur défini en analysant la manière dont les utilisateurs procèdent ou quittent le parcours. Il vous permet de créer un graphique flexible de nœuds et de flèches représentant n’importe quelle combinaison d’événements, d’éléments de dimension et de segments inclus dans le parcours. Les données sont mises à jour lorsque vous faites glisser des nœuds sur la zone de travail ou que vous réorganisez les événements et les conditions du parcours.<p>Auparavant, la zone de travail de parcours n’était disponible que pour Customer Journey Analytics.</p><p>Pour en savoir plus sur la zone de travail de Parcours dans Adobe Analytics, consultez la présentation de la zone de travail de Parcours [](/help/analyze/analysis-workspace/visualizations/journey-canvas/journey-canvas.md). </p><p>Pour savoir comment créer une visualisation de zone de travail de Parcours dans Adobe Analytics, voir [Configurer la zone de travail de Parcours ](/help/analyze/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).</p> | 18 Mai 2026 | 5 Juin 2026 |
| **Guide de création de rapports de l’API de modèle d’attribution** <br/>Un nouveau Guide de rapport du modèle d’attribution de l’API Adobe Analytics 2.0 est disponible. Ce guide explique comment inclure des données d’objet de modèle d’attribution dans les rapports de l’API Dimension.<p>Pour plus d’informations, voir [Modèles d’attribution d’API ](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/dimensions/attmodel).</p> | | Mai 2026 |
| **Services de médias en streaming : prise en charge des données de planning** <br/>Vous pouvez désormais charger des données planifiées antérieures de contenu de médias en streaming et en direct afin de suivre l’audience plus facilement et avec plus de précision.<p>Les éléments suivants sont des exemples de contenu en direct qui sont pris en charge avec le chargement de données de planning :</p><ul><li>Plateformes FAST (Free Ad Supported TV)</li><li>Flux locaux</li><li>Sports en direct</li></ul><p>Le chargement des données de planning vous permet de suivre les audiences des programmes individuels qui ont été diffusés pendant la période que vous avez indiquée dans le fichier de chargement. Vous pouvez même recueillir des données d’audience pour des sujets ou des segments de programme spécifiques.</p><p>Ces fonctionnalités sont disponibles quelle que soit la manière dont vous avez mis en œuvre Streaming Media Collection.</p><p>Auparavant, il était difficile de relier avec précision une session donnée à des programmes spécifiques lors de l’analyse du contenu en direct, et il n’était pas possible de relier une session donnée à des sujets individuels ou à des segments de programmes.</p><p>Pour plus d’informations, voir [Charger des données de planning pour suivre le contenu en direct](https://experienceleague.adobe.com/fr/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 octobre 2025 | Premier semestre 2026<p>(Version initialement prévue pour le 29 octobre 2025)</p> |

{style="table-layout:auto"}

## Correctifs dans Adobe Analytics

**Activity Map**:
**** : AN-446522, AN-445779, AN-445759, AN-444676, AN-442813, AN-441943, AN-441717, AN-441538, AN-441123, AN-440976, AN-440952, AN-440919, AN-440599, AN-439797, AN-434855, AN-429777, AN-429048, AN-428892 428189 425215
**Classifications** : AN-447743, AN-447296, AN-447130, AN-446552, AN-446324, AN-446040, AN-445841, AN-445753, AN-444992, AN-444979, AN-444428, AN-444332, AN-443507, AN-442906, AN-442232, AN-442207, AN-442133, AN-442035, AN-441901, AN-441807, AN-441671, AN-441333, AN-441302 441267 441132 441085 441048 440846 440727 440716 440496 440429 432100
**Flux de données et Data Warehouse** : AN-447344, AN-446654, AN-445126, AN-444492, AN-442802, AN-442211, AN-442048, AN-441719, AN-441534, AN-441300, AN-441183, AN-441011, AN-440625
**Migration** : AN-442467, AN-440380, AN-440357
**Exports** :
**** : AN-448697, AN-447128, AN-441148, AN-441136, AN-438147, AN-425150
**Création de rapports** : AN-445123, AN-444869, AN-443453, AN-443275, AN-443148, AN-442464, AN-442148, AN-441811, AN-441506, AN-441149, AN-441119, AN-440545, AN-440511, AN-440300, AN-431409, AN-423359 406242
**Suites de rapports** :
**Rapports planifiés** :
**Segmentation** :
**Autre** : AN-449159, AN-444661, AN-439429, AN-439423, AN-430988, AN-397985


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
* [Notes de mise à jour des services de streaming multimédia](https://experienceleague.adobe.com/fr/docs/media-analytics/using/release-notes/release-notes)
* Dernières mises à jour des produits Adobe CX Enterprise [](https://business.adobe.com/fr/products/adobe-experience-cloud-products.html)
