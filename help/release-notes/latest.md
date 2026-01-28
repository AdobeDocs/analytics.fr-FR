---
title: Notes de mise à jour actuelles d’Adobe Analytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 39a87f6d9cfd3c80c1762f30c9b0aa8c51b90838
workflow-type: tm+mt
source-wordcount: '1226'
ht-degree: 49%

---

# Notes de mise à jour actuelles d’Adobe Analytics (janvier 2026)

**Dernière mise à jour** : jeudi 14 janvier 2026

Ces notes de mise à jour couvrent la période de publication de janvier 2026. Les mises à jour d’Adobe Analytics fonctionnent sur un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Nouvelles fonctionnalités ou améliorations {#features}

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Créateur de règles d’ensembles de classifications** | La fonctionnalité [Créateur de règles](/help/components/classifications/sets/manage/rules.md) est désormais disponible dans les ensembles de classifications. Vous définissez des règles dans le contexte d’un ensemble de classifications. Les règles sont appliquées (lorsqu’elles sont activées) à toutes les combinaisons de suites de rapports et de dimensions clés qui sont abonnées à l’ensemble de classifications.</p> |  | samedi 23 janvier 2026 |
| **Flux de données améliorés** | Les améliorations suivantes sont désormais disponibles pour les flux de données :<ul><li>Amélioration de l’expérience utilisateur.</li><li>Nouvelle expérience de création et de gestion de modèles de colonne.</li><li>Vous pouvez maintenant choisir quand créer un modèle de colonne à réutiliser dans les futurs flux de données. Vous pouvez également supprimer, modifier et copier des modèles.<br/>Auparavant, chaque flux de données créé entraînait un nouveau modèle de colonne, ce qui entraînait un grand nombre de modèles de colonne inutilisés et aucun moyen de les supprimer ou de les gérer.</li><li>Ajoutez et filtrez par balises.</li><li>Afficher l’historique des tâches liées aux flux de données. (Date de début de la période de requête, date de début, date de fin, etc.)</li><li>Renvoyer ou retraiter des flux de données. (À partir de la page Historique des tâches)</li><li>Autorisez les accès en retard. Vous pouvez désormais inclure les données arrivées après la fin du traitement des données par la tâche de flux de données dans la fréquence de création de rapports définie.</li><li>Lors du choix d’une date de fin pour un flux de données, la date de fin que vous choisissez est incluse comme dernier jour du flux de données.<br/>Auparavant, la date de fin était exclue du flux de données.</li><li>Une fréquence d’exportation de 15 minutes est désormais possible, mais n’est pas disponible par défaut. Pour que cette option soit disponible dans votre environnement, vous devez d’abord contacter l’assistance clientèle d’Adobe et demander que votre suite de rapports soit configurée pour prendre en charge les exportations de 15 minutes.</li></ul><p>**Remarque :** grâce à ces améliorations, les URL des pages de flux de données dans Adobe Analytics sont également mises à jour. Mettez à jour les signets existants pour pointer vers les nouvelles pages de flux de données d’ici le 30 avril 2026.</p>(Lien vers la documentation à suivre.)</p> | mercredi 20 janvier 2026 | mercredi 10 février 2026 |
| **Trier les tableaux sur plusieurs colonnes** | Vous pouvez désormais trier les données d’un tableau à structure libre selon plusieurs colonnes dans Analysis Workspace, qu’il s’agisse de dimensions ou de mesures.<p>Lorsque vous triez des données pour plusieurs colonnes, les données sont triées en fonction de la priorité que vous attribuez à chaque colonne. La numérotation de priorité s’affiche en regard de l’icône de tri.</p><p>Pour plus d’informations, voir [Filtrer et trier les tableaux à structure libre](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).</p> | jeudi 28 janvier 2026 | jeudi 18 février 2026 |
| **Services de médias en streaming : prise en charge des données de planning** | Vous pouvez désormais charger des données planifiées antérieures de contenu de médias en streaming et en direct afin de suivre l’audience plus facilement et avec plus de précision.<p>Les éléments suivants sont des exemples de contenu en direct qui sont pris en charge avec le chargement de données de planning :</p><ul><li>Plateformes FAST (Free Ad Supported TV)</li><li>Flux locaux</li><li>Sports en direct</li></ul><p>Le chargement des données de planning vous permet de suivre les audiences des programmes individuels qui ont été diffusés pendant la période que vous avez indiquée dans le fichier de chargement. Vous pouvez même recueillir des données d’audience pour des sujets ou des segments de programme spécifiques.</p><p>Ces fonctionnalités sont disponibles quelle que soit la manière dont vous avez mis en œuvre Streaming Media Collection.</p><p>Auparavant, il était difficile de relier avec précision une session donnée à des programmes spécifiques lors de l’analyse du contenu en direct, et il n’était pas possible de relier une session donnée à des sujets individuels ou à des segments de programmes.</p><p>Pour plus d’informations, voir [Charger des données de planning pour suivre le contenu en direct](https://experienceleague.adobe.com/fr/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 octobre 2025 | Premier semestre 2026<p>(Version initialement prévue pour le 29 octobre 2025)</p> |

## Correctifs dans Adobe Analytics

**Activity Map**:
**Analysis Workspace** : AN-423389, AN-422636, AN-422482, AN-422027, AN-421134, AN-420187, AN-406271, AN-406188, AN-405997, AN-405983, AN-405796, AN-405033, AN-404893, AN-404871, AN-404842, AN-404713, AN-404502, AN-404353, AN-404352, AN-404048, AN-402523 396149 390990 390728 390646 383484 376980 371729 347570
**Classifications** : AN-423985, AN-423092, AN-423067, AN-422913, AN-422908, AN-422793, AN-422785, AN-422745, AN-422705, AN-422422, AN-422126, AN-422098, AN-422077, AN-422058, AN-421999, AN-421698, AN-421351, AN-406583, AN-406295, AN-406123 406052 404743 404372
**Collecte de données** : AN-422488
**Flux de données et Data Warehouse** : AN-423186, AN-422789, AN-422239, AN-421552, AN-421393, AN-421339, AN-421231, AN-420149, AN-406345, AN-406217, AN-405073, AN-404822, AN-404774, AN-389691
**Confidentialité** :
**Report Builder**: AN-422120, AN-421937, AN-406296, AN-402951, AN-399748
**Rapports** :
**Rapports planifiés** : AN-423087, AN-422686
**Comparaison des segments** :
**Autre** : AN-423401, AN-422819, AN-422775, AN-422626, AN-422238, AN-422160, AN-422071, AN-421687, AN-420045, AN-404891, AN-404608, AN-390912, AN-


## Avis de fin de vie {#eol}

| Produit ou fonctionnalité en fin de vie | Date d’ajout ou de mise à jour | Description |
| --- | --- | --- |
| **Améliorations du traitement Livestream** | jeudi 14 janvier 2026 | Adobe prévoit d’apporter des améliorations et des modifications au formatage des payloads LiveStream. Ces mises à jour offrent une meilleure parité entre LiveStream et d’autres fonctionnalités d’Adobe Analytics, telles qu’Analysis Workspace. Un point d’entrée de prévisualisation est disponible et vous permet de tester les modifications planifiées. Consultez les [notes de mise à jour de LiveStream] pour obtenir la liste complète des modifications et les détails sur les points d’entrée de prévisualisation. Adobe prévoit une transition définitive vers le format de payload mis à jour le 13 avril 2026. |
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
