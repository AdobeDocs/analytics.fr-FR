---
title: Notes de mise à jour actuelles d’Adobe Analytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 987638b1a5601a4c5713611b463e4ec77479ed8d
workflow-type: tm+mt
source-wordcount: '968'
ht-degree: 45%

---

# Notes de mise à jour actuelles d’Adobe Analytics (version de juin 2025)

**Dernière mise à jour** : jeudi 18 juin 2025

Ces notes de mise à jour couvrent la période du 18 juin au 15 juillet 2025. Les mises à jour d’Adobe Analytics fonctionnent sur un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Nouvelles fonctionnalités ou améliorations {#features}

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Prise en charge des destinations sécurisées dans le nouveau Report Builder** | De nouvelles destinations d’exportation ont été ajoutées au complément Report Builder. Les destinations d’espace de stockage suivantes sont prises en charge : <ul><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>SAS Azure</li><li>RBAC Azure</li></ul> FTP n’est plus pris en charge en raison de problèmes de sécurité. (Lien vers la documentation à suivre) |  | Juin 18,2025 |
| **Nouvelle expérience d’aperçu** | Le panneau de prévisualisation, utilisé pour prévisualiser les segments, les mesures calculées, etc., utilise désormais une visualisation à barres horizontales au lieu d’une visualisation en anneau. |  | jeudi 18 juin 2025 |
| **Boîte de dialogue Modèle d’attribution modifié** | Vous pouvez désormais définir le conteneur et la période séparément dans la boîte de dialogue Modèle d’attribution. |  | Juin 18,2025 |
| **Mise à jour de la navigation vers l’interface utilisateur Attributs du client** | L’interface utilisateur Attributs du client est désormais accessible directement à partir du sélecteur d’applications dans Adobe Experience Cloud. |  | À confirmer |
| **Streaming Media : prend en charge les données de planning** | Vous pouvez désormais charger des données planifiées de contenu multimédia en flux continu précédent pour suivre plus facilement et plus précisément l’audience. Voici des exemples de contenu dynamique pris en charge avec le chargement planifié des données :<ul><li>Plateformes FAST (Free Ad Supported TV)</li><li>Flux locaux</li><li>Sports en direct</li></ul>Le chargement des données de planning vous permet d’effectuer le suivi des données d’audience pour des programmes individuels qui se sont exécutés au cours de la période que vous avez désignée dans le fichier de chargement. Vous pouvez même collecter des données d’audience pour des sujets ou des segments de programme spécifiques. Ces fonctionnalités sont disponibles quelle que soit la manière dont vous avez implémenté Streaming Media Collection.<p>Auparavant, il était difficile de lier précisément une session donnée à des programmes spécifiques lors de l’analyse du contenu en direct, et il n’était pas possible de lier une session donnée à des sujets individuels ou des segments de programme. En savoir plus |  | jeudi 25 juin 2025 |
| **Prise en charge du pré-rendu Chrome** | Contrôlez le comportement des bibliothèques de collecte de données lorsque Chrome effectue le pré-rendu d’une page. (Lien vers la documentation à suivre) |  | mardi 30 juin 2025 |

## Correctifs dans Adobe Analytics

**A4T** : AN-379045
**Advertising Analytics** : AN-377338
**Alertes** : AN-377229
**Analysis Workspace**: AN-378891; AN-379589; AN-379604; AN-381270; AN-382264; AN-382414;
**API 1.4** : AN-380188
**API 2.0** : AN-373078 ; AN-379006 ; AN-381248
**Classifications** : AN-379209 ; AN-379315 ; AN-379567 ; AN-379573 ; AN-379749 ; AN-379764 ; AN-379818 ; AN-380433 ; AN-381670 ; AN-381751 ; AN-381994 ; AN-382055 ; AN-382682 ; AN-383059 ; AN-383409
**Analyse des contributions** : AN-369822
**Flux de données** : AN-365552 ; AN-367158 ; AN-378288 ; AN-379754 ; AN-380433 ; AN-380855 ; AN-380959 ; AN-381115 ; AN-381657 ; AN-381931
**Data Warehouse**: AN-379244
**Platform** : AN-375847
**Règles de traitement** : AN-375157
**Report Builder**: AN-371395; AN-372174; AN-373815; AN-383194
**Appels au serveur** : AN-380930
**Journaux d’utilisation et d’accès** : AN-372130 ; AN-382123
**Suites de rapports virtuelles** : AN-382010


## Avis de fin de vie {#eol}

| Produit ou fonctionnalité en fin de vie | Date d’ajout ou de mise à jour | Description |
| --- | --- | --- |
| **Report Builder hérité** | jeudi 18 juin 2025 | L’ancien module complémentaire Report Builder sera mis hors service en juin 2026. Tous les utilisateurs doivent commencer à mettre à niveau leurs classeurs hérités vers le [nouveau Report Builder](https://experienceleague.adobe.com/fr/docs/analytics/analyze/report-builder/rb-overview). Le nouveau Report Builder est disponible à la fois pour les clients Adobe Analytics et Customer Journey Analytics. Elle offre une [quasi-parité des fonctionnalités](https://experienceleague.adobe.com/fr/docs/analytics/analyze/report-builder/convert-workbooks#unsupported) ainsi que de nombreuses nouvelles fonctionnalités pratiques et améliorations de l’interface utilisateur. Pour faciliter le processus de mise à niveau, le nouveau Report Builder comprend une fonctionnalité de conversion de classeur facile à utiliser. Le nouveau Report Builder n’est disponible que sous la forme d’un complément dans le magasin Microsoft. De nombreuses organisations nécessitent un processus d&#39;approbation interne avant que le complément ne puisse être mis à la disposition des utilisateurs. Veuillez allouer du temps à ce processus et commencer à travailler avec votre organisation dès maintenant afin de vous assurer que vous disposez de suffisamment de temps pour mettre à niveau vos classeurs avant la date de fin de vie. |
| **Accès via les domaines hérités ou via l’authentification SSO héritée** | 10 avril 2025 | Adobe prévoit de mettre à jour la manière dont les utilisateurs et utilisatrices accèdent à Adobe Analytics afin d’améliorer la sécurité et de rationaliser votre expérience de connexion. Dans le cadre de cette opération, l’accès par le biais des domaines hérités ou de l’authentification SSO héritée, y compris `my.omniture.com`, sera définitivement arrêté le **2 janvier 2026**. Après cette date, les identifiants de connexion hérités et l’authentification SSO héritée ne fonctionneront plus. Tous les utilisateurs et utilisatrices devront se connecter via `experience.adobe.com` à l’aide de leurs identifiants Adobe Experience Cloud. Si vous avez besoin d’aide avec votre Experience Cloud ID, contactez l’administration Adobe Analytics de votre entreprise ou l’[Assistance clientèle Adobe](https://helpx.adobe.com/fr/contact.html). |
| **Migration vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O** | 17 janvier 2025 | Les clients et clientes de l’API Adobe Analytics et de Livestream qui utilisent les informations d’identification JWT d’Adobe I/O doivent migrer vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O avant le **30 juin 2025**. Adobe I/O n’autorisera pas la création d’informations d’identification JWT à compter du 1er mai 2024. Les clients et clientes utilisant JWT doivent créer des informations d’identification de serveur à serveur OAuth ou migrer leurs informations d’identification JWT existantes vers des informations d’identification de serveur à serveur OAuth. Ils ou elles doivent également mettre à jour leurs applications clientes afin d’utiliser les nouvelles informations d’identification de serveur à serveur OAuth. <ul><li>[Migration des informations d’identification du compte de service (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration)</li><li>[Guide de mise en œuvre pour les nouvelles et les anciennes applications avec OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation)<li>[Utilisation des nouvelles informations d’identification de serveur à serveur OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation)</li><li>[Questions fréquentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs)</li></ul> |
| **API Adobe Analytics (version 1.4)** | 17 juillet 2024 | Le **12 août 2026**, les services d’API hérités d’Analytics suivants arriveront en fin de vie et seront fermés. Les intégrations actuelles créées à l’aide de ces services cesseront de fonctionner :<ul><li>API Adobe Analytics (version 1.4)</li><li>Authentification WSSE Adobe Analytics</li></ul><p>Les intégrations qui utilisent l’API Adobe Analytics (version 1.4) doivent migrer vers l’[API Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), tandis que les intégrations WSSE doivent migrer vers un protocole d’authentification basé sur OAuth dans [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Pour obtenir des réponses aux questions courantes et d’autres conseils, reportez-vous à la [FAQ sur la fin de vie des API Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md).</p> |



## AppMeasurement

Pour connaître les dernières mises à jour des versions d’AppMeasurement, reportez-vous aux [notes de mise à jour d’AppMeasurement](https://github.com/adobe/appmeasurement/releases).


## Ressources connexes

* [Notes de mise à jour précédentes pour 2025](/help/release-notes/2025.md)
* [Notes de mise à jour de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=fr)
* [Notes de mise à jour du module complémentaire Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* Dernières mises à jour des [produits Adobe Experience Cloud](https://business.adobe.com/fr/products/adobe-experience-cloud-products.html)
