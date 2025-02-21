---
title: Notes de mise à jour actuelles d’Adobe Analytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: f738c0767a952d8c53f526056708dddf427e1880
workflow-type: tm+mt
source-wordcount: '697'
ht-degree: 57%

---

# Notes de mise à jour actuelles d’Adobe Analytics (version de février 2025)

**Dernière mise à jour** : 21 février 2024

Ces notes de mise à jour couvrent la période du 11 février à la mi-mars 2025. Les mises à jour d’Adobe Analytics fonctionnent sur un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Nouvelles fonctionnalités ou améliorations {#features}

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Période de conservation de l’ID de transaction** | La période de conservation des ID de transaction de 90 jours a été étendue à 25 mois. La variable `transactionID` identifie de manière unique une transaction afin que l’accès puisse être lié aux données chargées via la fonctionnalité Sources de données. En savoir plus [ici](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/page-vars/transactionid) et [ici](https://experienceleague.adobe.com/en/docs/analytics/import/data-sources/transactionid). |  | vendredi 20 février 2025 |
| **Référence de l’API des flux de données** | La [référence](https://adobedocs.github.io/analytics-2.0-apis/?urls.primaryName=Data%20Feeds%20APIs) pour l’API des flux de données est désormais disponible. |  | 30 janvier 2025 |
| **API Livestream - Implémentation du client** | Utilisez l’implémentation du client Livestream pour utiliser les données Livestream. [En savoir plus](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/clientcode/) |  | mercredi 18 février 2025 |
| **Mettre à jour vers l’API Classifications** | Vous pouvez désormais supprimer du serveur des champs ou des clés de classification individuels. Cela fournit une alternative à la suppression d’un jeu de données de classification entier avec la méthode DELETE. [En savoir plus](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/remove-values/) |  | mercredi 18 février 2025 |
| **Mise à jour des`a.locale`** de champs de données contextuelles Analytics | Mise à jour de la façon dont le `a.locale` de champ de données contextuelles Analytics est défini lors de la collecte de données via Experience Edge. Lorsque des données sont envoyées à Adobe Analytics à l’aide d’Experience Edge, les champs Analytics sont renseignés en fonction d’un mappage de champs XDM. Le mappage de `c.a.locale` fait référence à un champ XDM non standard, `xdm.environment.language`. Ce champ sera mis à jour pour référencer le champ correct, `xdm.environment._dc.language`.  Le mappage continuera à référencer des `xdm.environment.language` à des fins de rétrocompatibilité. Pour la continuité, si les deux champs sont définis, `xdm.environment.language` est prioritaire. Vous pouvez consulter la liste complète des mappages de XDM vers les champs Analytics standard [ici](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/xdm-var-mapping). | | jeudi 5 mars 2025 |


## Correctifs dans Adobe Analytics

**Analysis Workspace**: AN-359974; AN-366212; AN-368460
**Classifications** : AN-367186 ; AN-367328 ; AN-368548
**Migration des composants** : AN-364529 ; AN-366398 ; AN-367509 ;
**Flux de données** : AN-365685 ; AN-366745 ; AN-367256 ; AN-367349 ; AN-368363
**Data Warehouse**: AN-368178; AN-368331;
**Application mobile** : AN-367137
**Platform** : AN-351924 ; AN-365540 ; AN-365866 ; AN-366898 ; AN-367856 ; AN-367933
**Report Builder**: AN-366456; AN-366655;
**Suites de rapports virtuelles** : AN-367411
**Règles VISTA** : AN-365331

## Avis importants pour les administrateurs d’Adobe Analytics {#admin}

| Avis | Date d’ajout ou de mise à jour | Description |
| ----------- | ---------- | ---------- |
| **La clientèle qui n’utilise pas Campaign n’aura plus accès à Triggers** | 16 octobre 2023 | Le 30 janvier 2025, les clients Adobe Analytics qui ne disposent pas d’une licence Adobe Campaign ont perdu l’accès à la possibilité de configurer et de consommer des [Triggers](https://experienceleague.adobe.com/fr/docs/core-services/interface/services/triggers). Pour conserver cet accès, il est nécessaire d’acheter Campaign, d’envisager l’arrêt de l’utilisation de Triggers, ou de se tourner vers d’autres outils Adobe proposant des fonctionnalités similaires. |

## Avis de fin de vie {#eol}

| Produit ou fonctionnalité en fin de vie | Date d’ajout ou de mise à jour | Description |
| --- | --- | --- |
| **Migration vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O** | 17 janvier 2025 | Les clients et clientes de l’API Adobe Analytics et de Livestream qui utilisent les informations d’identification JWT d’Adobe I/O doivent migrer vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O avant le **30 juin 2025**. Adobe I/O n’autorisera pas la création d’informations d’identification JWT à compter du 1er mai 2024. Les clients et clientes utilisant JWT doivent créer des informations d’identification de serveur à serveur OAuth ou migrer leurs informations d’identification JWT existantes vers des informations d’identification de serveur à serveur OAuth. Ils ou elles doivent également mettre à jour leurs applications clientes afin d’utiliser les nouvelles informations d’identification de serveur à serveur OAuth. <ul><li>[Migration des informations d’identification du compte de service (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guide de mise en œuvre pour les nouvelles et les anciennes applications avec OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilisation des nouvelles informations d’identification de serveur à serveur OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Questions fréquentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **Abandon de l’API Adobe Analytics (version 1.4)** | 17 juillet 2024 | Le **12 août 2026**, les services d’API hérités d’Analytics suivants arriveront en fin de vie et seront fermés. Les intégrations actuelles créées à l’aide de ces services cesseront de fonctionner :<ul><li>API Adobe Analytics (version 1.4)</li><li>Authentification WSSE Adobe Analytics</li></ul><p>Les intégrations qui utilisent l’API Adobe Analytics (version 1.4) doivent migrer vers l’[API Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), tandis que les intégrations WSSE doivent migrer vers un protocole d’authentification basé sur OAuth dans [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Pour obtenir des réponses aux questions courantes et d’autres conseils, reportez-vous à la [FAQ sur la fin de vie des API Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md).</p> |


## AppMeasurement

Pour connaître les dernières mises à jour des versions d’AppMeasurement (version 2.26.0), reportez-vous aux [Notes de mise à jour d’AppMeasurement pour JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=fr).


## Ressources connexes

* [Notes de mise à jour précédentes pour 2024](/help/release-notes/2024.md)
* [Notes de mise à jour de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=fr)
* [Notes de mise à jour du module complémentaire Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* Dernières mises à jour des [produits Adobe Experience Cloud](https://business.adobe.com/fr/products/adobe-experience-cloud-products.html)
