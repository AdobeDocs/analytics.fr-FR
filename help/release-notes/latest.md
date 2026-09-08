---
title: Notes de mise à jour actuelles d’Adobe Analytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics
feature: Release Notes
hold: true
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
TQID: 'https://experienceleague.adobe.com/yw30Yij2NBaeuWFqxD4-VH1Hysf8dxOpxHUwsFCYEw8'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7id: fd307ce7-56f5-4ee3-af68-a7833ff6e85eid: a421fb65-2c82-457a-921c-28c46b697a39
subfeature_v2: id: d89ba969-e026-48bf-927e-e9df2f1e34f3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d095671a-1355-40aa-8b5f-06c33c68080bid: d3cdead0-685a-4489-9250-4bb709942f66id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 8645907799594d2eb2d6bcf56f93ac1cc42578f8
workflow-type: tm+mt
source-wordcount: 1098
ht-degree: 50%

---

# Notes de mise à jour actuelles d’Adobe Analytics (septembre 2026)

**Dernière mise à jour** : 8 septembre 2026

Ces notes de mise à jour couvrent la période de publication de septembre 2026. Les mises à jour d’Adobe Analytics fonctionnent sur un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Nouvelles fonctionnalités ou améliorations {#features}

| Fonctionnalité et description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ---- |
| **Limiter les segments à la période du rapport**<br/> Les données d’un rapport Workspace peuvent s’étendre au-delà de la période du rapport lorsqu’un segment inclut des composants de période.<p>Une nouvelle option est désormais disponible. Elle vous permet de limiter les résultats à la période du rapport, quels que soient les composants de date inclus dans le segment. <p>Cette option est disponible lors de la création ou de la modification d’un segment dont le conteneur de niveau supérieur est Visiteur.</p><p>Pour plus d’informations, voir [Création de segments](/help/components/segmentation/segmentation-workflow/seg-build.md#components).</p> | 26 Août 2026 | 9 septembre 2026 |
| **Mises à jour de la détection des robots**<br/> Lors de l’utilisation de la collecte de données Edge avec le SDK Web, les mises à jour de détection des robots suivantes sont disponibles :<ul><li>Vous pouvez désormais créer des règles de détection des robots pour identifier les exceptions dans le trafic qui seraient autrement traitées comme générées par des robots. Les règles existantes et futures continueront à marquer par défaut le trafic correspondant comme généré par les robots.</li><li>Les règles de robots personnalisées s’exécutent désormais avant les règles de détection de robots IAB. Cette modification n’affecte pas les scores de robots, mais les noms de règle de robots associés à un événement peuvent changer.</li></ul><p>Remarque : cette mise à jour s’applique uniquement aux implémentations de la collecte de données Edge qui utilisent le SDK Web. Elle ne s’applique pas aux bibliothèques plus anciennes telles qu’AppMeasurement.</p></p><p>(Lien vers la documentation à suivre.)</p> | | Début Septembre 2026 |
| **Intégration de**<br/> connectez Adobe Brand Visibility aux données Adobe Analytics de votre entreprise afin de mesurer la manière dont les découvertes pilotées par l’IA se traduisent par un engagement réel sur le site web et des résultats commerciaux.<p>(Lien vers la documentation à suivre.)</p> | | Septembre 2026 |
| **Mises à jour de l’API des ensembles de classifications**<br/> La documentation de l’API des ensembles de classifications comprend désormais des informations mises à jour de point d’entrée et de paramètre pour configurer les requêtes de l’API des ensembles de classifications.<p>Pour plus d’informations, consultez le [guide sur les points d’entrée des classifications](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/).</p> | 5 septembre 2026 | 30 septembre 2026 |
| **Guide de codage des éléments d’ID de date dans les guides des rapports de l’API 2.0**<br/> Les guides des rapports de tendance de date de l’API Adobe Analytics 2.0 incluent désormais de nouvelles sections expliquant comment les paramètres et les valeurs de `itemId` de date sont codés. Cela peut vous aider à configurer et à migrer vers les services d’API 2.0 à partir des API 1.4 désormais obsolètes.<p>Pour plus d’informations, consultez le [guide sur les rapports des indicateurs de performance clés](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/kpi) et le [guide des rapports avancés](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/advanced).</p> | 5 septembre 2026 | 30 septembre 2026 |

### Correctifs dans Adobe Analytics

**** : AN-488579, AN-487247
**** : AN-487374, AN-487119, AN-468907, AN-468810, AN-468363, AN-468096, AN-467414, AN-466986, AN-466982, AN-465073, AN-463571, AN-462373
**Classifications** : AN-490825, AN-490802, AN-490549, AN-490472, AN-487782, AN-487286, AN-486531, AN-478859, AN-469929, AN-469033, AN-468944, AN-468827, AN-468592, AN-468326, AN-467115, AN-466995, AN-465636, AN-465616 465380 464911 464338 463677 462729 462577 461040 459316
**Flux de données et Data Warehouse** : AN-487624, AN-487287, AN-479923, AN-479166, AN-479109, AN-468483
**Migration** :
**Exports** : AN-467131
**** : AN-487486, AN-478944, AN-470036, AN-468589, AN-468436, AN-456747, AN-456700, AN-442695
**Reporting** : AN-468621, AN-465383, AN-463924
**Suites de rapports** : AN-468484, AN-468460, AN-465385
**Rapports planifiés** :
**Segmentation** : AN-486561
**Autre** : AN-488549, AN-467426, AN-465265, AN-464645, AN-459714, AN-459323, AN-454514

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
| **Services de médias en streaming : prise en charge des données de planning** <br/>Vous pouvez désormais charger des données planifiées antérieures de contenu de médias en streaming et en direct afin de suivre l’audience plus facilement et avec plus de précision.<p>Voici quelques exemples de contenu en direct pris en charge avec le chargement des données de planning :</p><ul><li>Plateformes FAST (Free Ad Supported TV)</li><li>Flux locaux</li><li>Sports en direct</li></ul><p>Le chargement des données de planning vous permet de suivre les données d’audience de chaque programme diffusé pendant la période que vous indiquez dans le fichier de chargement. Vous pouvez même recueillir des données d’audience pour des sujets ou des segments de programme spécifiques.</p><p>Ces fonctionnalités sont disponibles quelle que soit la manière dont vous avez mis en œuvre Streaming Media Collection.</p><p>Auparavant, il était difficile d’associer avec précision une session donnée à des programmes spécifiques lors de l’analyse du contenu en direct, et il était impossible de l’associer à des sujets ou à des segments de programme individuels.</p><p>Pour plus d’informations, voir [Chargement des données de planning pour suivre le contenu en direct](https://experienceleague.adobe.com/fr/docs/media-analytics/using/media-use-cases/track-schedule-data). | 29 octobre 2025 | À confirmer<p>(Initialement prévu pour le 29 octobre 2025)</p> |


>[!MORELIKETHIS]
>
>* [Notes de mise à jour précédentes pour 2026](/help/release-notes/2026.md)
>* [Notes de mise à jour de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=fr)
>* [Notes de mise à jour des services de médias en streaming](https://experienceleague.adobe.com/fr/docs/media-analytics/using/release-notes/release-notes)
>* Dernières mises à jour des [produits Adobe CX Enterprise](https://business.adobe.com/fr/products/adobe-experience-cloud-products.html)

