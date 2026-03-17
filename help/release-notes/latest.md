---
title: Notes de mise à jour actuelles d’Adobe Analytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: d61dc175eed0737ce8fc43506712dedf5341367c
workflow-type: tm+mt
source-wordcount: '1291'
ht-degree: 52%

---

# Notes de mise à jour actuelles d’Adobe Analytics (mars 2026)

**Dernière mise à jour** : jeudi 11 mars 2026

Ces notes de mise à jour couvrent la période de publication de mars 2026. Les mises à jour d’Adobe Analytics fonctionnent sur un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Nouvelles fonctionnalités ou améliorations {#features}

| Fonctionnalité et description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ---- |
| **Tri des tableaux par plusieurs colonnes** <br/>Vous pouvez désormais trier les données d’un tableau à structure libre selon plusieurs colonnes dans Analysis Workspace, qu’il s’agisse de dimensions ou de mesures.<p>Lorsque vous triez des données sur plusieurs colonnes, les données sont triées en fonction de la priorité que vous attribuez à chaque colonne. Le score de priorité s’affiche en regard de l’icône de tri.</p><p>Pour plus d’informations, voir [Filtrer et trier les tableaux à structure libre](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).</p> | jeudi 28 janvier 2026 | jeudi 4 mars 2026 <p>(Initialement prévu pour le 18 février 2026)</p> |
| **Report Builder : visibilité de l’administrateur sur tous les classeurs planifiés**<br/> Le complément Report Builder Excel inclut une nouvelle option de filtre qui permet aux administrateurs de voir tous les classeurs planifiés pour une organisation donnée, quelle que soit la personne qui les a planifiés. Cette option de filtre n’est disponible que pour les administrateurs et administratrices Analytics. Elle est disponible dans les onglets Classeur et Hérité lors de l’affichage de classeurs planifiés.<p>La possibilité d’afficher tous les classeurs planifiés est particulièrement utile lors de la migration de classeurs entre des équipes distribuées, car elle permet aux administrateurs de localiser facilement tous les classeurs hérités avant de les migrer.</p><p>Auparavant, les administrateurs ne pouvaient afficher que les classeurs planifiés, et non ceux planifiés par d’autres utilisateurs.</p><p>Pour plus d’informations, voir [Classeurs planifiés gérés](/help/analyze/report-builder/manage-schedules-reportbuilder.md).</p> | | mercredi 10 mars 2026 |
| **Mise à jour de la fonction Nombre approximatif d’éléments distincts**<br/> L’algorithme probabiliste HLL utilisé dans la fonction Nombre approximatif d’éléments distincts sera bientôt mis à jour. La sortie résultante pour les nombres utilisant cette fonction peut changer légèrement par rapport aux nombres historiques, comme suit :</p><ul><li>Lorsque vous comptez de très petites quantités de valeurs uniques, les résultats seront améliorés pour utiliser des décomptes exacts plutôt que des estimations.</li><li>Lorsque vous comptabilisez des éléments de plus grande taille, les estimations de comptage conservent la même précision qu’avant cette mise à jour (les estimations sont exactes à moins de 5 % du nombre exact, 95 % du temps).</li></ul><p>Pour plus d&#39;informations sur la fonction Nombre approximatif d&#39;éléments distincts, voir [Nombre approximatif d&#39;éléments distincts](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md#approximate-count-distinct) dans [Fonctions avancées](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md)</p> | | mercredi 10 mars 2026 |
| **Tutoriel pratique pour Analysis Workspace**<br/> Un nouveau tutoriel pratique est désormais disponible pour guider les nouveaux utilisateurs à travers les principes de base de l’utilisation des panneaux, des visualisations et des composants dans Analysis Workspace. <p>Pour plus d’informations, voir [Page de destination Adobe Analytics](/help/analyze/landing.md).</p> | | jeudi 18 mars 2026 |
| **Appliquer une répartition à un panneau**<br/> Vous pouvez désormais appliquer une répartition à un panneau. Lors de l’application d’une répartition au niveau du panneau, la répartition est appliquée à toutes les colonnes de tous les tableaux à structure libre du panneau. | Mars 2026 | Mai 2026 |
| **Services de médias en flux continu : prennent en charge les données de planning** <br/>Vous pouvez désormais charger les données planifiées du contenu multimédia en flux continu précédent en direct pour suivre plus facilement et plus précisément l’audience.<p>Les éléments suivants sont des exemples de contenu en direct qui sont pris en charge avec le chargement de données de planning :</p><ul><li>Plateformes FAST (Free Ad Supported TV)</li><li>Flux locaux</li><li>Sports en direct</li></ul><p>Le chargement des données de planning vous permet de suivre les audiences des programmes individuels qui ont été diffusés pendant la période que vous avez indiquée dans le fichier de chargement. Vous pouvez même recueillir des données d’audience pour des sujets ou des segments de programme spécifiques.</p><p>Ces fonctionnalités sont disponibles quelle que soit la manière dont vous avez mis en œuvre Streaming Media Collection.</p><p>Auparavant, il était difficile de relier avec précision une session donnée à des programmes spécifiques lors de l’analyse du contenu en direct, et il n’était pas possible de relier une session donnée à des sujets individuels ou à des segments de programmes.</p><p>Pour plus d’informations, voir [Charger des données de planning pour suivre le contenu en direct](https://experienceleague.adobe.com/fr/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 octobre 2025 | Premier semestre 2026<p>(Version initialement prévue pour le 29 octobre 2025)</p> |

## Correctifs dans Adobe Analytics

**Activity Map**:
**Analysis Workspace** : AN-440336, AN-440216, AN-440121, AN-438445, AN-438216, AN-437856, AN-437776, AN-437765, AN-437365, AN-432793, AN-432094, AN-431557, AN-431200, AN-429621, AN-429424, AN-427973, AN-426089, AN-425883 424359
**Classifications** : AN-440143, AN-439891, AN-439844, AN-438994, AN-438057, AN-438052, AN-437986, AN-437896, AN-435387, AN-435335, AN-435150, AN-433050, AN-432062, AN-431873 429642
**Flux de données et Data Warehouse** : AN-439441, AN-437086, AN-433064, AN-432121, AN-431755, AN-428239, AN-427049, AN-425036, AN-424972, AN-423509, AN-335417, AN-283958, AN-256948
**Migration** :
**Exports** : AN-432030
**Report Builder**: AN-437895, AN-437083, AN-434288, AN-434209, AN-433224, AN-430622
**Reporting** : AN-434545, AN-431206, AN-428043
**Rapports planifiés** :
**Segmentation** :
**Autre** : AN-440076, AN-434783, AN-434542, AN-434233, AN-433368, AN-432138, AN-431322, AN-431012, AN-429067, AN-423285


## Avis de fin de vie {#eol}

| Produit ou fonctionnalité en fin de vie | Date d’ajout ou de mise à jour | Description |
| --- | --- | --- |
| **Améliorations du traitement Livestream** | jeudi 14 janvier 2026 | Adobe prévoit d’apporter des améliorations et des modifications au formatage des payloads LiveStream. Ces mises à jour offrent une meilleure parité entre LiveStream et d’autres fonctionnalités d’Adobe Analytics, telles qu’Analysis Workspace. Un point d’entrée de prévisualisation est disponible et vous permet de tester les modifications planifiées. Consultez les [notes de mise à jour de LiveStream](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/release-notes/) pour obtenir la liste complète des modifications et les détails sur les points d’entrée de prévisualisation. Adobe prévoit une transition définitive vers le format de payload mis à jour le 13 avril 2026. |
| **Suppression des suites de chiffrement TLS 1.2** | jeudi 11 février 2026 | Avis aux administrateurs : Adobe prévoit de supprimer la prise en charge des suites de chiffrement TLS 1.2 suivantes des serveurs de collecte de données Adobe le 27 mai 2026.<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li></ul><p>Aucune action du client n’est requise pour la plupart des implémentations. Cette modification affecte principalement les données Analytics envoyées à partir d’applications natives héritées qui utilisent des bibliothèques TLS obsolètes, ainsi qu’un petit nombre de visiteurs web sur des navigateurs ou des systèmes d’exploitation obsolètes. La suppression de la prise en charge de ces suites de chiffrement améliore la sécurité et aligne Adobe sur les normes de chiffrement modernes. Moins de 0,1 % du trafic de collecte de données repose actuellement sur ces suites de chiffrement.</p> |
| **Report Builder hérité** | 18 juin 2025 | L’ancien module complémentaire Report Builder sera supprimé en juin 2026. Tous les utilisateurs et utilisatrices doivent commencer à mettre à niveau leurs anciens classeurs vers le [nouveau Report Builder](/help/analyze/report-builder/rb-overview.md). Le nouveau Report Builder est disponible pour les clientes et clients d’Adobe Analytics et de Customer Journey Analytics. Il assure la [quasi-parité des fonctionnalités](/help/analyze/report-builder/convert-workbooks.md#unsupported), et propose de nombreuses nouvelles fonctionnalités pratiques et des améliorations de l’interface d’utilisation. Pour faciliter le processus de mise à niveau, le nouveau Report Builder comprend une fonction de conversion facile des classeurs. Le nouveau Report Builder n’est disponible que sous forme de module complémentaire dans Microsoft Store. De nombreuses organisations exigent un processus d’approbation interne avant que le module complémentaire ne soit mis à la disposition des utilisateurs et utilisatrices. Prévoyez suffisamment de temps pour ce processus et commencez à travailler dès maintenant avec votre organisation afin de disposer de suffisamment de temps pour mettre à niveau vos classeurs avant la date de fin de validité. |
| **Accès via les domaines hérités ou via l’authentification SSO héritée** | 10 avril 2025 | Adobe prévoit de mettre à jour la manière dont les utilisateurs et utilisatrices accèdent à Adobe Analytics afin d’améliorer la sécurité et de rationaliser votre expérience de connexion. Dans le cadre de cette opération, l’accès par le biais des domaines hérités ou de l’authentification SSO héritée, y compris `my.omniture.com`, sera définitivement arrêté le **2 janvier 2026**. Après cette date, les identifiants de connexion hérités et l’authentification SSO héritée ne fonctionneront plus. Tous les utilisateurs et utilisatrices devront se connecter via `experience.adobe.com` à l’aide de leurs identifiants Adobe Experience Cloud. Si vous avez besoin d’aide avec votre Experience Cloud ID, contactez l’administration Adobe Analytics de votre entreprise ou l’[Assistance clientèle Adobe](https://helpx.adobe.com/fr/contact.html?lang=fr). |
| **API Adobe Analytics (version 1.4)** | 17 juillet 2024 | Le **12 août 2026**, les services d’API hérités d’Analytics suivants arriveront en fin de vie et seront fermés. Les intégrations actuelles créées à l’aide de ces services cesseront de fonctionner :<ul><li>API Adobe Analytics (version 1.4)</li><li>Authentification WSSE Adobe Analytics</li></ul><p>Les intégrations qui utilisent l’API Adobe Analytics (version 1.4) doivent migrer vers l’[API Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/?lang=fr), tandis que les intégrations WSSE doivent migrer vers un protocole d’authentification basé sur OAuth dans [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Pour obtenir des réponses aux questions courantes et d’autres conseils, reportez-vous à la [FAQ sur la fin de vie des API Adobe Analytics 1.4](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/).</p> |


## AppMeasurement

Pour connaître les dernières mises à jour des versions d’AppMeasurement, reportez-vous aux [notes de mise à jour d’AppMeasurement](https://github.com/adobe/appmeasurement/releases).


## Ressources connexes

* [Notes de mise à jour précédentes pour 2025](/help/release-notes/2025.md)
* [Notes de mise à jour de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=fr)
* [Notes de mise à jour des services de médias en streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* Dernières mises à jour des [produits Adobe Experience Cloud](https://business.adobe.com/fr/products/adobe-experience-cloud-products.html)
