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
source-git-commit: 13d4b15d7069a52f4953a49aa0f1f5b7cb16ae77
workflow-type: tm+mt
source-wordcount: 890
ht-degree: 63%

---

# Notes de mise à jour actuelles d’Adobe Analytics (juillet 2026)

**Dernière mise à jour** : 8 juillet 2026

Ces notes de mise à jour couvrent la période de publication de juillet 2026. Les mises à jour d’Adobe Analytics fonctionnent sur un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Nouvelles fonctionnalités ou améliorations {#features}

| Fonctionnalité et description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ---- |
| **Analyse des sous-accès** <br/>L’analyse des sous-accès vous permet d’analyser les données de produit à un niveau plus granulaire que le niveau d’accès. Au lieu de filtrer les accès entiers, vous pouvez segmenter les produits individuels dans les accès. <p>Par exemple, vous pouvez segmenter une catégorie de produits spécifique sans inclure tous les autres produits achetés dans la même commande.</p><p>Pour plus d’informations, voir [&#x200B; Analyse des sous-accès &#x200B;](/help/components/segmentation/sub-hit.md).</p> | 8 juillet | Fin juillet 2026 |
| **Guide des fonctionnalités de recherche de l’API AA 2.0** <br/>Utilisez les fonctionnalités de recherche pour [renvoyer un sous-ensemble d’éléments de dimension dans les rapports](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/search-filters).<p>Pour plus d’informations, voir [Fonctionnalités de recherche](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/search-filters) dans le guide de point d’entrée des rapports sur Adobe Developer. | | 1er juillet 2026 |
| **Automatisation des rapports récurrents à l’aide des API AA** <br/>configurez des rapports Adobe Analytics récurrents automatiques pour votre pipeline de données avec de nouvelles mesures selon un calendrier précis avec l’API de rapport. <p>Pour plus d’informations, consultez le [Guide d’automatisation des points d’entrée des rapports récurrents d’Analytics](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/recurring) sur Adobe Developer.</p> | | 1er juillet 2026 |
| **Nouveaux paramètres de développement pour AA** <br/>Utilisez les nouveaux paramètres de développement de l’API Dimension pour récupérer les champs de configuration eVar pour les types d’attribution, les expirations, les types de données et le marchandisage. <p>Pour plus d’informations, consultez les guides [Référence de l’API](https://developer.adobe.com/analytics-apis/docs/2.0/apis/#operation/dimensions_getDimensions) et [Point d’entrée des dimensions](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/dimensions/) sur Adobe Developer.</p> | | 1er juillet 2026 |

### Correctifs dans Adobe Analytics

**Activity Map** :
**&#x200B;**&#x200B;: AN-449890, AN-457527, AN-451161, AN-459034, AN-458071, AN-458398
**Classifications** : AN-453318, AN-456739, AN-455828, AN-455270, AN-460272, AN-459367, AN-459239, AN-458418, AN-458417
**Flux de données et Data Warehouse** : AN-456945, AN-460700
**Migration** :
**Exports** :
**&#x200B;**&#x200B;: AN-457533, AN-453683
**Reporting** : AN-447692, AN-451259, AN-455713
**Suites de rapports** :
**Rapports planifiés** : AN-450715
**Segmentation** :
**Autre** : AN-453982, AN-455771

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
| **Services de médias en streaming : prise en charge des données de planning** <br/>Vous pouvez désormais charger des données planifiées antérieures de contenu de médias en streaming et en direct afin de suivre l’audience plus facilement et avec plus de précision.<p>Les éléments suivants sont des exemples de contenu en direct qui sont pris en charge avec le chargement de données de planning :</p><ul><li>Plateformes FAST (Free Ad Supported TV)</li><li>Flux locaux</li><li>Sports en direct</li></ul><p>Le chargement des données de planning vous permet de suivre les audiences des programmes individuels qui ont été diffusés pendant la période que vous avez indiquée dans le fichier de chargement. Vous pouvez même recueillir des données d’audience pour des sujets ou des segments de programme spécifiques.</p><p>Ces fonctionnalités sont disponibles quelle que soit la manière dont vous avez mis en œuvre Streaming Media Collection.</p><p>Auparavant, il était difficile de relier avec précision une session donnée à des programmes spécifiques lors de l’analyse du contenu en direct, et il n’était pas possible de relier une session donnée à des sujets individuels ou à des segments de programmes.</p><p>Pour plus d’informations, voir [Charger des données de planning pour suivre le contenu en direct](https://experienceleague.adobe.com/fr/docs/media-analytics/using/media-use-cases/track-schedule-data) | 29 octobre 2025 | À confirmer<p>(Initialement prévu pour le 29 octobre 2025)</p> |


>[!MORELIKETHIS]
>
>* [Notes de mise à jour précédentes pour 2026](/help/release-notes/2026.md)
>* [Notes de mise à jour de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=fr)
>* [Notes de mise à jour des services de médias en streaming](https://experienceleague.adobe.com/fr/docs/media-analytics/using/release-notes/release-notes)
>* Dernières mises à jour des [produits Adobe CX Enterprise](https://business.adobe.com/fr/products/adobe-experience-cloud-products.html)

