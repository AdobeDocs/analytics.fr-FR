---
title: Notes de mise à jour actuelles d’Adobe Analytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 2d42a824510fa03825a10da3837801ee662f687c
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 51%

---

# Notes de mise à jour actuelles d’Adobe Analytics (version du 23 octobre 2024)


**Dernière mise à jour** : jeudi 23 octobre 2024

Ces notes de mise à jour portent sur la période du 16 octobre 2024 à la fin de l’année 2024. Les mises à jour d’Adobe Analytics fonctionnent sur un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Nouvelles fonctionnalités ou améliorations {#features}

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Nouveau Report Builder pour Adobe Analytics** | La nouvelle application de Report Builder apporte une mise à jour majeure à Adobe Analytics, notamment de meilleures performances, une interface utilisateur rationalisée, une prise en charge et une prise en charge des API 2.0 pour Microsoft Excel sous Mac, Windows et les navigateurs Web. Cette application peut être utilisée avec l’application héritée, mais pas sur le même fichier. Une fonctionnalité de mise à niveau est fournie pour mettre à niveau les classeurs hérités vers la nouvelle application. [En savoir plus](https://experienceleague.adobe.com/en/docs/analytics/analyze/report-builder/report-buider-overview) |  | 16 octobre 2024 |
| **Exportation JSON pour la migration de l’implémentation des balises vers les balises SDK Web** | Cette mise à jour de l’extension des balises Analytics est liée à la migration vers le SDK Web. Vous pouvez utiliser cette mise à jour de l’extension Adobe Analytics dans le cadre de votre workflow pour recréer vos configurations d’extension avec l’extension SDK Web. Dans l’extension des balises Adobe Analytics, vous pouvez afficher les paramètres d’eVars, de props et d’événements au format JSON, qui peuvent être exportés pour modification et inclus dans l’extension du SDK Web. |  | jeudi 23 octobre 2024 |

## Correctifs dans Adobe Analytics

Analysis Workspace : AN-356287 ; AN-358435 ; AN-359456 ; AN-359826 ; AN-360215
Outils d’administration : AN-342485 ; AN-347931 ; AN-348704 ; AN-357723 ; AN-358453 ; AN-358717 ; AN-359548 ; AN-360136
Classifications : AN-359025; AN-359283; AN-359368; AN-359710; AN-359752; AN-359759; AN-359799; AN-359887; AN-360543; AN-360566; AN-; AN-360612; AN-360741; AN-; AN-
Analyses entre appareils : AN-359210
Attributs du client : AN-357897
Collecte de données : AN-351131 ; AN-351309 ; AN-355678 ; AN-359856
Flux de données : AN-359699
API de réparation des données : AN-360256
Sources de données : AN-359290
Data Warehouse : AN-359820
Alertes de dépassement : AN-358132


## Avis importants pour les administrateurs d’Adobe Analytics {#admin}

| Avis | Date d’ajout ou de mise à jour | Description |
| ----------- | ---------- | ---------- |
| **Les clients non Campaign perdront l&#39;accès aux Triggers** | 16 octobre 2024 | Le 30 janvier 2025, les clients Adobe Analytics qui n’ont pas de licence Adobe Campaign perdront l’accès à la possibilité de configurer et d’utiliser [Triggers](https://experienceleague.adobe.com/en/docs/core-services/interface/services/triggers). Les clients doivent soit acheter Campaign, soit planifier l&#39;arrêt de l&#39;utilisation de Triggers, soit consulter d&#39;autres outils d&#39;Adobe offrant des fonctionnalités Triggers. |
| **Champs XDM de détails d’implémentation supplémentaires automatiquement mappés** | 11 septembre 2024 | Lors de l’utilisation d’Edge Network Adobe Experience Platform pour envoyer des données à Adobe Analytics, les champs XDM `xdm.implementationdetails.name` et `xdm.implementationdetails.environment` sont désormais toujours mappés sur les variables de données contextuelles `c.a.x.implementationdetails.name` et `c.a.x.implementationdetails.environment`. Auparavant, certains scénarios empêchaient le renseignement de ces valeurs. Ajustez les règles de traitement appropriées en fonction de la disponibilité de ces valeurs. |

## Avis de fin de vie {#eol}

| Produit ou fonctionnalité en fin de vie | Date d’ajout ou de mise à jour | Description |
| --- | --- | --- |
| **Abandon de l’API Adobe Analytics (version 1.4)** | 17 juillet 2024 | Le **12 août 2026**, les services d’API hérités d’Analytics suivants atteindront leur fin de vie et seront fermés, et les intégrations actuelles créées à l’aide de ces services cesseront de fonctionner :<ul><li>API Adobe Analytics (version 1.4)</li><li>Authentification WSSE Adobe Analytics</li></ul><p>Les intégrations qui utilisent l’API Adobe Analytics (version 1.4) doivent migrer vers l’[API Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), tandis que les intégrations WSSE doivent migrer vers un protocole d’authentification basé sur OAuth dans [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Pour obtenir des réponses aux questions courantes et d’autres conseils, reportez-vous à la [FAQ sur la fin de vie des API Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md).</p> |
| **Migration vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O** | 11 mai 2023 | Les clients et clientes de l’API Adobe Analytics et de Livestream qui utilisent les informations d’identification JWT d’Adobe I/O doivent migrer vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O avant le **1er janvier 2025**. Adobe I/O n’autorisera pas la création d’informations d’identification JWT à compter du 1er mai 2024. Les clients et clientes utilisant JWT doivent créer des informations d’identification de serveur à serveur OAuth ou migrer leurs informations d’identification JWT existantes vers des informations d’identification de serveur à serveur OAuth. Ils ou elles doivent également mettre à jour leurs applications clientes afin d’utiliser les nouvelles informations d’identification de serveur à serveur OAuth. <ul><li>[Migration des informations d’identification du compte de service (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guide de mise en œuvre pour les nouvelles et les anciennes applications avec OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilisation des nouvelles informations d’identification de serveur à serveur OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Questions fréquentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |


## AppMeasurement

Pour connaître les dernières mises à jour des versions d’AppMeasurement (version 2.26.0), reportez-vous aux [Notes de mise à jour d’AppMeasurement pour JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=fr).


## Ressources connexes

* [Notes de mise à jour précédentes pour 2024](/help/release-notes/2024.md)
* [Notes de mise à jour de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=fr)
* [Notes de mise à jour du module complémentaire Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* Dernières mises à jour des [produits Adobe Experience Cloud](https://business.adobe.com/fr/products/adobe-experience-cloud-products.html)
