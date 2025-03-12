---
title: Notes de mise à jour actuelles d’Adobe Analytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 2b13f649d286e9eb707f2dd22c068b9742c51c70
workflow-type: tm+mt
source-wordcount: '730'
ht-degree: 54%

---

# Notes de mise à jour actuelles d’Adobe Analytics (version de mars 2025)

**Dernière mise à jour** : jeudi 12 mars 2025

Ces notes de mise à jour couvrent la période du 5 mars au mai 2025. Les mises à jour d’Adobe Analytics fonctionnent sur un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Nouvelles fonctionnalités ou améliorations {#features}

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Mise à jour du champs de données contextuelles Analytics`a.locale`** | Cette mise à jour modifie la manière dont le `a.locale` de champ de données contextuelles Analytics est défini lors de la collecte de données via Experience Edge. Lorsque des données sont envoyées à Adobe Analytics à l’aide d’Experience Edge, les champs Analytics sont renseignés en fonction d’un mappage de champs XDM. Le mappage de `c.a.locale` fait référence à un champ XDM non standard, `xdm.environment.language`. Ce champ sera mis à jour pour référencer le champ correct, `xdm.environment._dc.language`.<p>Le mappage continuera à référencer des `xdm.environment.language` à des fins de rétrocompatibilité. Pour la continuité, si les deux champs sont définis, `xdm.environment.language` est prioritaire. Vous pouvez consulter la liste complète des mappages de XDM vers les champs Analytics standard [ici](https://experienceleague.adobe.com/fr/docs/analytics/implementation/aep-edge/xdm-var-mapping). | | 5 mars 2025 |
| **Guide de mise à niveau de Customer Journey Analytics** | Permet de générer un guide détaillé pour la mise à niveau d’Adobe Analytics vers Customer Journey Analytics. Ce guide est adapté à votre entreprise et prend en compte votre environnement Adobe Analytics actuel, les utilisations prévues de Customer Journey Analytics et les compromis que votre entreprise souhaite réaliser pour gagner du temps.<p>Pour commencer à générer votre guide personnalisé, connectez-vous à [!DNL Customer Journey Analytics], puis sélectionnez **[!UICONTROL Mettre à niveau vers Customer Journey Analytics]** dans l’onglet **[!UICONTROL Workspace]**.<p>[En savoir plus](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-recommendations#recommended-upgrade-steps-for-most-organizations) |  | mercredi 11 mars 2025 |
| **dimensions Data Warehouse uniquement** | À partir de mai 2025, Adobe commencera à définir des dimensions (variables personnalisées telles que des eVars et des props) qui présentent une cardinalité extrêmement élevée sur « Data Warehouse uniquement ». Les variables à cardinalité élevée ont de nombreuses valeurs distinctes ; par exemple, la date et l’heure ou les UUID. Ces dimensions ne seront plus disponibles pour la création de rapports dans Analysis Workspace.<p>Les dimensions susceptibles d’être modifiées dépassent les limites de faible trafic très tôt dans le mois. Avec ces types de dimensions, les rapports dans Analysis Workspace qui sont basés sur cette dimension ne sont pas utiles, car les données à signaler ne représentent qu’une mince tranche des valeurs initiales qui ont été collectées.<p>Étant donné que Data Warehouse n’impose pas de limites de faible trafic, vous pouvez toujours créer des rapports ou des segments utiles basés sur ces types de dimensions. | | Mai 2025 |


## Correctifs dans Adobe Analytics

**Activity Map** : AN-361038
**Outils d’administration** : AN-362178 ; AN-369483
**API Analytics 1.4** : AN-369615
**Analysis Workspace**: AN-353491; AN-363403; AN-367230; AN-367313; AN-368582; AN-369821; AN-370227;
**Classifications** : AN-369848 ; AN-370196 ; AN-370226 ; AN-370437
**Flux de données** : AN-366162 ; AN-368906 ; AN-369066 ; AN-369087 ; AN-369225 ; AN-369798
**Gouvernance des données** : AN-365157
**Sources de données** : AN-367550
**Platform** : AN-363931
**Report Builder**: AN-367460; AN-368975

## Avis importants pour les administrateurs d’Adobe Analytics {#admin}

| Avis | Date d’ajout ou de mise à jour | Description |
| ----------- | ---------- | ---------- |
| S.O. |  |  |

## Avis de fin de vie {#eol}

| Produit ou fonctionnalité en fin de vie | Date d’ajout ou de mise à jour | Description |
| --- | --- | --- |
| **Migration vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O** | 17 janvier 2025 | Les clients et clientes de l’API Adobe Analytics et de Livestream qui utilisent les informations d’identification JWT d’Adobe I/O doivent migrer vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O avant le **30 juin 2025**. Adobe I/O n’autorisera pas la création d’informations d’identification JWT à compter du 1er mai 2024. Les clients et clientes utilisant JWT doivent créer des informations d’identification de serveur à serveur OAuth ou migrer leurs informations d’identification JWT existantes vers des informations d’identification de serveur à serveur OAuth. Ils ou elles doivent également mettre à jour leurs applications clientes afin d’utiliser les nouvelles informations d’identification de serveur à serveur OAuth. <ul><li>[Migration des informations d’identification du compte de service (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guide de mise en œuvre pour les nouvelles et les anciennes applications avec OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilisation des nouvelles informations d’identification de serveur à serveur OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Questions fréquentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **Abandon de l’API Adobe Analytics (version 1.4)** | 17 juillet 2024 | Le **12 août 2026**, les services d’API hérités d’Analytics suivants arriveront en fin de vie et seront fermés. Les intégrations actuelles créées à l’aide de ces services cesseront de fonctionner :<ul><li>API Adobe Analytics (version 1.4)</li><li>Authentification WSSE Adobe Analytics</li></ul><p>Les intégrations qui utilisent l’API Adobe Analytics (version 1.4) doivent migrer vers l’[API Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), tandis que les intégrations WSSE doivent migrer vers un protocole d’authentification basé sur OAuth dans [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Pour obtenir des réponses aux questions courantes et d’autres conseils, reportez-vous à la [FAQ sur la fin de vie des API Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md).</p> |


## AppMeasurement

Pour connaître les dernières mises à jour des versions d’AppMeasurement (version 2.27.0), reportez-vous aux [notes de mise à jour d’AppMeasurement for JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=fr).


## Ressources connexes

* [Notes de mise à jour précédentes pour 2025](/help/release-notes/2025.md)
* [Notes de mise à jour de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=fr)
* [Notes de mise à jour du module complémentaire Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* Dernières mises à jour des [produits Adobe Experience Cloud](https://business.adobe.com/fr/products/adobe-experience-cloud-products.html)
