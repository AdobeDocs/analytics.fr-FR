---
title: Notes de mise à jour actuelles d’Adobe Analytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
TQID: 'https://experienceleague.adobe.com/yw30Yij2NBaeuWFqxD4-VH1Hysf8dxOpxHUwsFCYEw8'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
  - id: a421fb65-2c82-457a-921c-28c46b697a39
subfeature_v2:
  - id: d89ba969-e026-48bf-927e-e9df2f1e34f3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 2258ee4b539ec7ce7366c427fede2c5b8483db7f
workflow-type: tm+mt
source-wordcount: 1246
ht-degree: 43%

---

# Notes de mise à jour actuelles d’Adobe Analytics (août 2026)

**Dernière mise à jour** : 5 août 2026

Ces notes de mise à jour couvrent la période de publication d’août 2026. Les mises à jour d’Adobe Analytics fonctionnent sur un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Nouvelles fonctionnalités ou améliorations {#features}

| Fonctionnalité et description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ---- |
| **Extension Activity Map : actualisation de l’interface utilisateur** <br/>l’extension de recouvrement Activity Map a une apparence mise à jour, ainsi que des améliorations sous-jacentes qui prennent en charge les améliorations à venir.<p>Pour plus d’informations sur l’extension de recouvrement Activity Map, voir [Interface de l’extension Activity Map](/help/analyze/activity-map/overlay/overview.md).</p> | | 5 Août 2026<p>(Initialement prévu pour fin juillet)</p> |
| **Améliorations de la zone de travail de Parcours**<br> Les améliorations de la zone de travail de Parcours suivantes sont désormais disponibles :<ul><li>Comparez le parcours à une période précédente. Comparez le parcours actuel au parcours 4 semaines avant, 2 trimestres avant, 1 an avant ou à une période personnalisée.</li><li>Pour un nœud sélectionné, affichez les principaux éléments de dimension qui se trouvent après le nœud sélectionné à tout moment dans le parcours. Utilisez cette option lorsque le nœud sélectionné est l’événement clé de votre analyse et que vous souhaitez voir ce que les personnes font à tout moment par la suite.<p>Auparavant, seuls les principaux nœuds immédiats pouvaient être affichés avant ou après le nœud sélectionné. </p></li><li>Modifiez la forme et le style des flèches entre les nœuds. Faites glisser des flèches entre les nœuds pour modifier la forme (courbure) de la flèche, puis cliquez avec le bouton droit sur une flèche pour modifier son style de l’une des manières suivantes : pleine, tirets, pointillés, tirets ou animés.</li></ul><p></p>Pour plus d’informations, consultez [Configuration d’une visualisation Zone de travail de parcours](/help/analyze/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md). | | 18 Août 2026 |
| **Limiter les segments à la période du rapport**<br/> Les données d’un rapport Workspace peuvent s’étendre au-delà de la période du rapport lorsqu’un segment inclut des composants de période.<p>Une nouvelle option est désormais disponible. Elle vous permet de limiter les résultats à la période du rapport, quels que soient les composants de date inclus dans le segment. <p>Cette option est disponible lors de la création ou de la modification d’un segment dont le conteneur de niveau supérieur est Visiteur.</p><p>Pour plus d’informations, voir [Création de segments](/help/components/segmentation/segmentation-workflow/seg-build.md#components).</p> | 26 Août 2026 | 9 septembre 2026 |
| **Référence des canaux marketing de l’API Analytics**<br/> Utilisez la référence des canaux marketing de l’API Adobe Analytics 2.0 pour récupérer les informations des canaux marketing Analytics. Consultez la [référence des canaux marketing de l’API Analytics](https://developer.adobe.com/analytics-apis/docs/2.0/apis/marketing-channels). | | 1Er Août 2026 |
| **Guide du point d’entrée des canaux marketing de l’API Analytics**<br/> Le guide du point d’entrée des canaux marketing de l’API Adobe Analytics 2.0 fournit des instructions et des exemples pour l’utilisation du point d’entrée. Consultez le [guide du point d’entrée des canaux marketing de l’API Analytics](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/marketing-channels). | | 1Er Août 2026 |
| **FAQ sur la fin de vie de l’API Analytics 1.4**<br/> La FAQ sur la fin de vie de l’API Analytics 1.4 fournit des informations sur le développement récent des API 2.0 pour aider les clients qui quittent les API 1.4. | | 10 Août 2026 |

### Correctifs dans Adobe Analytics

**&#x200B;**&#x200B;: AN-404862
**&#x200B;**&#x200B;: AN-466867, AN-465995, AN-465315, AN-465313, AN-464375, AN-463634, AN-463248, AN-463175, AN-463049, AN-462347, AN-462124, AN-461922, AN-458398, AN-457849, AN-455002, AN-453357, AN-456863, AN-459816, AN-459034, AN-460774, AN-460671, AN-457760, AN-443594
**Classifications** : AN-467138, AN-467118, AN-467069, AN-466054, AN-465987, AN-465636, AN-465380, AN-464650, AN-464286, AN-463688, AN-462413, AN-462252, AN-462141, AN-462063, AN-462005, AN-461862, AN-461806, AN-461777, AN-461158, AN-460954, AN-460905, AN-460850, AN-460803, AN-460272, AN-460023, AN-459814, AN-459367, AN-459328, AN-459300, AN-459279, AN-459006, AN-458417, AN-458403, AN-457829, AN-457400, AN-454408, AN-449670, AN-460956, AN-459269, AN-458789, AN-461778, AN-461191, AN-460996 460506 459988 459854 458994 457561 457055 454224 454172 459473 459277 459026 455270
**Flux de données et Data Warehouse** : AN-465273, AN-464245, AN-462435, AN-461000, AN-460700, AN-459225, AN-459192
**Migration** : AN-458185, AN-454285, AN-459239
**Exports** :
**&#x200B;**&#x200B;: AN-465346, AN-464768, AN-464580, AN-464301, AN-463048, AN-462800, AN-457042, AN-461033, AN-459042, AN-454250, AN-451735, AN-450776, AN-450200, AN-451665
**Reporting** : AN-467107, AN-459010, AN-455619, AN-459530, AN-454103
**Suites de rapports** : AN-464246, AN-463756, AN-462101
**Rapports planifiés** : AN-455009, AN-460037, AN-462093
**Segmentation** : AN-459002, AN-457730, AN-457146
**Autre** : AN-467386, AN-466935, AN-462116, AN-458836, AN-451292, AN-454160, AN-458354, AN-455771, AN-426869, AN-437975

### Avis de fin de vie {#eol}

| Produit ou fonctionnalité en fin de vie | Date d’ajout ou de mise à jour | Description |
| --- | --- | --- |
| **Report Builder hérité** | 18 juin 2025 | L’ancien module complémentaire Report Builder sera supprimé en juin 2026. Tous les utilisateurs et utilisatrices doivent commencer à mettre à niveau leurs anciens classeurs vers le [nouveau Report Builder](/help/analyze/report-builder/rb-overview.md). Le nouveau Report Builder est disponible pour les clientes et clients d’Adobe Analytics et de Customer Journey Analytics. Il assure la [quasi-parité des fonctionnalités](/help/analyze/report-builder/convert-workbooks.md#unsupported), et propose de nombreuses nouvelles fonctionnalités pratiques et des améliorations de l’interface d’utilisation. Pour faciliter le processus de mise à niveau, le nouveau Report Builder comprend une fonction de conversion facile des classeurs. Le nouveau Report Builder n’est disponible que sous forme de module complémentaire dans Microsoft Store. De nombreuses organisations exigent un processus d’approbation interne avant que le module complémentaire ne soit mis à la disposition des utilisateurs et utilisatrices. Prévoyez suffisamment de temps pour ce processus et commencez à travailler dès maintenant avec votre organisation afin de disposer de suffisamment de temps pour mettre à niveau vos classeurs avant la date de fin de validité. |
| **API Adobe Analytics (version 1.4)** | 17 juillet 2024 | Le **12 août 2026**, les services d’API hérités d’Analytics suivants arriveront en fin de vie et seront fermés. Les intégrations actuelles créées à l’aide de ces services cesseront de fonctionner :<ul><li>API Adobe Analytics (version 1.4)</li><li>Authentification WSSE Adobe Analytics</li></ul><p>Les intégrations qui utilisent l’API Adobe Analytics (version 1.4) doivent migrer vers l’[API Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/?lang=fr), tandis que les intégrations WSSE doivent migrer vers un protocole d’authentification basé sur OAuth dans [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Pour obtenir des réponses aux questions courantes et d’autres conseils, reportez-vous à la [FAQ sur la fin de vie des API Adobe Analytics 1.4](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/).</p> |

## AppMeasurement

Pour connaître les dernières mises à jour des versions d’AppMeasurement, reportez-vous aux [notes de mise à jour d’AppMeasurement](https://github.com/adobe/appmeasurement/releases).

## Fonctionnalités reportées

| Fonctionnalité et description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| -----------|-----------|-----------|
| **Services de médias en streaming : prise en charge des données de planning** <br/>Vous pouvez désormais charger des données planifiées antérieures de contenu de médias en streaming et en direct afin de suivre l’audience plus facilement et avec plus de précision.<p>Les éléments suivants sont des exemples de contenu en direct qui sont pris en charge avec le chargement de données de planning :</p><ul><li>Plateformes FAST (Free Ad Supported TV)</li><li>Flux locaux</li><li>Sports en direct</li></ul><p>Le chargement des données de planning vous permet de suivre les audiences des programmes individuels qui ont été diffusés pendant la période que vous avez indiquée dans le fichier de chargement. Vous pouvez même recueillir des données d’audience pour des sujets ou des segments de programme spécifiques.</p><p>Ces fonctionnalités sont disponibles quelle que soit la manière dont vous avez mis en œuvre Streaming Media Collection.</p><p>Auparavant, il était difficile de relier avec précision une session donnée à des programmes spécifiques lors de l’analyse du contenu en direct, et il n’était pas possible de relier une session donnée à des sujets individuels ou à des segments de programmes.</p><p>Pour plus d’informations, voir [Chargement des données de planning pour suivre le contenu en direct](https://experienceleague.adobe.com/fr/docs/media-analytics/using/media-use-cases/track-schedule-data). | 29 octobre 2025 | À confirmer<p>(Initialement prévu pour le 29 octobre 2025)</p> |


>[!MORELIKETHIS]
>
>* [Notes de mise à jour précédentes pour 2026](/help/release-notes/2026.md)
>* [Notes de mise à jour de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=fr)
>* [Notes de mise à jour des services de médias en streaming](https://experienceleague.adobe.com/fr/docs/media-analytics/using/release-notes/release-notes)
>* Dernières mises à jour des [produits Adobe CX Enterprise](https://business.adobe.com/fr/products/adobe-experience-cloud-products.html)

