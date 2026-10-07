---
title: Notes de mise à jour actuelles d’Adobe Analytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
TQID: 'https://experienceleague.adobe.com/yw30Yij2NBaeuWFqxD4-VH1Hysf8dxOpxHUwsFCYEw8'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
    internal-label: Integrations
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: d89ba969-e026-48bf-927e-e9df2f1e34f3
    internal-label: Release notes
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: b72328485bde3759519f77c1c3e9509ade6ce2d4
workflow-type: tm+mt
source-wordcount: '966'
ht-degree: 53%
---
# Notes de mise à jour actuelles d’Adobe Analytics (octobre 2026)

**Dernière mise à jour** : 7 octobre 2026

Ces notes de mise à jour couvrent la période de publication d’octobre 2026. Les mises à jour d’Adobe Analytics fonctionnent sur un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Nouvelles fonctionnalités ou améliorations {#features}

| Fonctionnalité et description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ---- |
| **Autorisation en lecture seule pour le serveur MCP Adobe Analytics**<br/> Les administrateurs peuvent désormais donner aux utilisateurs et utilisatrices un accès en lecture seule au serveur MCP Adobe Analytics. Le nouvel élément d’autorisation [!UICONTROL MCP Read Only] permet aux utilisateurs et utilisatrices d’accéder à tous les outils en lecture seule, sans leur permettre de créer des projets, des segments ou des mesures calculées.<p>L’élément d’autorisation [!UICONTROL Accès MCP] existant est renommé [!UICONTROL Accès complet MCP]. Les utilisateurs et utilisatrices bénéficiant de cette autorisation conservent l’accès à tous les outils, y compris ceux qui créent, modifient ou suppriment des composants.</p><p>Pour plus d’informations, voir [Serveur Adobe Analytics MCP](https://developer.adobe.com/analytics-mcp/docs/aa/).</p> | | 6 Octobre 2026 |
| **Générer automatiquement des descriptions de composant** <br/>Vous pouvez désormais générer automatiquement des descriptions pour les dimensions, les mesures, les mesures calculées, les segments et les périodes. Cela permet aux utilisateurs de Workspace de savoir quels composants utiliser, en particulier dans les organisations qui disposent de bibliothèques de composants volumineuses. <p>Vous pouvez générer une description pour un seul composant ou générer des descriptions pour de nombreux composants en même temps.</p> <p>(Lien vers la documentation à suivre.)<!--For more information, see [Automatically generate descriptions](/help/components/add-component-descriptions.md#automatically-generate-descriptions).--></p> | | 28 Octobre 2026 |
| **Intégration de**<br/> connectez Adobe Brand Visibility aux données Adobe Analytics de votre entreprise afin de mesurer la manière dont les découvertes pilotées par l’IA se traduisent par un engagement réel sur le site web et des résultats commerciaux.<p>(Lien vers la documentation à suivre.)</p> | | Octobre 2026 |
| **CX Enterprise Coworker : analyser les données d’Adobe Analytics dans le Module de conversation des collègues** <br/>Le Module de conversation d’Adobe CX Enterprise Coworker peut désormais effectuer une analyse avancée des données, auparavant possible uniquement dans Analysis Workspace. Le Module de conversation avec les collègues accède aux données de vos suites de rapports Adobe Analytics, ce qui vous permet d’explorer ces données et d’obtenir des réponses aux invites en langage naturel.<p>(Lien vers la documentation à suivre.)</p> | 2 Octobre 2026 | À confirmer<p>(Initialement prévu pour le 25 septembre 2026)</p> |

### Correctifs dans Adobe Analytics

**** : AN-494609, AN-493182
**** : AN-495340, AN-494789, AN-493307, AN-468900
**Classifications** : AN-498043, AN-496619, AN-496468, AN-496217, AN-496133, AN-495567, AN-494651, AN-494345, AN-494312, AN-494261, AN-493645, AN-493507, AN-493336, AN-492869, AN-492812, AN-492751, AN-492750, AN-492741, AN-491032, AN-490802 490796 467849
**Flux de données et Data Warehouse** : AN-494937, AN-493065, AN-489796, AN-479109
**Migration** : AN-489850, AN-468014
**Exports** : AN-494337, AN-486563
**** : AN-496602, AN-494224, AN-493737, AN-493508, AN-493505, AN-492806, AN-468981, AN-454376
**Reporting** : AN-493637, AN-461260
**Suites de rapports** : AN-496773, AN-495227, AN-494981, AN-494372, AN-494370, AN-493629
**Rapports planifiés** : AN-491103
**Segmentation** :
**Autre** : AN-496398, AN-494453, AN-492494

### Avis de fin de vie {#eol}

| Produit ou fonctionnalité en fin de vie | Date d’ajout ou de mise à jour | Description |
| --- | --- | --- |
| **Report Builder hérité** | 18 juin 2025 | L’ancien complément Report Builder a été retiré en juin 2026. Tous les utilisateurs et utilisatrices doivent commencer à mettre à niveau leurs anciens classeurs vers le [nouveau Report Builder](/help/analyze/report-builder/rb-overview.md). Le nouveau Report Builder est disponible pour les clientes et clients d’Adobe Analytics et de Customer Journey Analytics. Il assure la [quasi-parité des fonctionnalités](/help/analyze/report-builder/convert-workbooks.md#unsupported), et propose de nombreuses nouvelles fonctionnalités pratiques et des améliorations de l’interface d’utilisation. Pour faciliter le processus de mise à niveau, le nouveau Report Builder comprend une fonction de conversion facile des classeurs. Le nouveau Report Builder n’est disponible que sous forme de module complémentaire dans Microsoft Store. De nombreuses organisations exigent un processus d’approbation interne avant que le module complémentaire ne soit mis à la disposition des utilisateurs et utilisatrices. Prévoyez suffisamment de temps pour ce processus et commencez à travailler dès maintenant avec votre organisation afin de disposer de suffisamment de temps pour mettre à niveau vos classeurs avant la date de fin de validité. |
| **API Adobe Analytics (version 1.4)** | 17 juillet 2024 | Le **31 août 2026** les services d’API hérités d’Analytics suivants ont atteint leur fin de vie et ont été fermés, et les intégrations créées à l’aide de ces services ne fonctionnent plus :<ul><li>API Adobe Analytics (version 1.4)</li><li>Authentification WSSE Adobe Analytics</li></ul><p>Les intégrations qui utilisent l’API Adobe Analytics (version 1.4) doivent migrer vers l’[API Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/?lang=fr), tandis que les intégrations WSSE doivent migrer vers un protocole d’authentification basé sur OAuth dans [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Pour obtenir des réponses aux questions courantes et d’autres conseils, reportez-vous à la [FAQ sur la fin de vie des API Adobe Analytics 1.4](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/).</p> |

## AppMeasurement

Pour connaître les dernières mises à jour des versions d’AppMeasurement, reportez-vous aux [notes de mise à jour d’AppMeasurement](https://github.com/adobe/appmeasurement/releases).

## Fonctionnalités reportées

| Fonctionnalité et description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| -----------|-----------|-----------|
| **Services de médias en streaming : prise en charge des données de planning** <br/>Vous pouvez désormais charger des données planifiées antérieures de contenu de médias en streaming et en direct afin de suivre l’audience plus facilement et avec plus de précision.<p>Voici quelques exemples de contenu en direct pris en charge avec le chargement des données de planning :</p><ul><li>Plateformes FAST (Free Ad Supported TV)</li><li>Flux locaux</li><li>Sports en direct</li></ul><p>Le chargement des données de planning vous permet de suivre les données d’audience de chaque programme diffusé pendant la période que vous indiquez dans le fichier de chargement. Vous pouvez même recueillir des données d’audience pour des sujets ou des segments de programme spécifiques.</p><p>Ces fonctionnalités sont disponibles quelle que soit la manière dont vous avez mis en œuvre Streaming Media Collection.</p><p>Auparavant, il était difficile d’associer avec précision une session donnée à des programmes spécifiques lors de l’analyse du contenu en direct, et il était impossible de l’associer à des sujets ou à des segments de programme individuels.</p><p>Pour plus d’informations, voir [Chargement des données de planning pour suivre le contenu en direct](https://experienceleague.adobe.com/fr/docs/media-analytics/using/media-use-cases/track-schedule-data).</p> | 29 octobre 2025 | À confirmer<p>(Initialement prévu pour le 29 octobre 2025)</p> |


>[!MORELIKETHIS]
>
>* [Notes de mise à jour précédentes pour 2026](/help/release-notes/2026.md)
>* [Notes de mise à jour de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=fr)
>* [Notes de mise à jour des services de médias en streaming](https://experienceleague.adobe.com/fr/docs/media-analytics/using/release-notes/release-notes)
>* Dernières mises à jour des [produits Adobe CX Enterprise](https://business.adobe.com/fr/products/adobe-experience-cloud-products.html)

