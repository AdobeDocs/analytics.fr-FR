---
title: Notes de mise à jour actuelles d’Adobe Analytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: ht
source-wordcount: '1147'
ht-degree: 100%

---

# Notes de mise à jour actuelles d’Adobe Analytics (version d’août 2025)

**Dernière mise à jour** : 13 août 2025

Ces notes de mise à jour portent sur la période du 13 août au 16 septembre 2025. Les mises à jour d’Adobe Analytics fonctionnent sur un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Nouvelles fonctionnalités ou améliorations {#features}

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analyser le trafic de l’IA avec un nouvel élément de dimension de type Référent** | En octobre, un nouvel élément de dimension de type Référent sera disponible pour vous aider à analyser le trafic provenant des outils d’IA. <p>Ce nouvel élément de dimension de type Référent, appelé Outils d’IA conversationnelle, regroupera les domaines référents des principaux outils d’IA permettant d’examiner les tendances pour le groupe dans son ensemble. La liste initiale des domaines référents dans cette nouvelle catégorie comprend (sans s’y limiter) les éléments suivants :</p><ul><li>chatgpt.com</li><li>claude.ai</li><li>m365.cloud.microsoft</li><li>grok.com</li><li>gemini.google.com</li><li>perplexity.ai</li></ul><p>Le nouvel élément de dimension sera disponible dans tous les outils liés à Adobe Analytics, notamment Analysis Workspace, Report Builder, Data Warehouse, les flux de données, etc.</p><p>Tenez compte des points suivants lors de l’utilisation de ce nouvel élément de dimension :</p><ul><li>Il n’est pas toujours possible de distinguer le trafic du référent provenant des résultats fournis dans le « mode IA » d’un moteur de recherche de celui provenant des clics publicitaires des résultats de recherche traditionnels.</li><li>Le nouvel élément de dimension Outils d’IA dédiée à la conversation se concentre sur les principaux fournisseurs ayant le plus de trafic. Une nouvelle tendance révèle un nombre croissant de sites d’emprunt d’identité avec des domaines similaires aux principaux fournisseurs d’outils d’IA. Cela est probablement dû à la facilité avec laquelle les personnes ou les groupes peuvent créer leurs propres outils d’IA et les héberger sur Internet. Comme il s’agit d’un espace qui évolue rapidement, contactez l’équipe d’assistance d’Adobe si vous constatez qu’un site populaire n’est pas inclus.</li><li>La dimension de type Référent, y compris le nouvel élément de dimension Outils d’IA dédiée aux conversations, est disponible uniquement pour les données traitées par Adobe Analytics. </li></ul><p>(Lien vers la documentation à suivre.)</p> |   | Octobre 2025 |
| **Les projets téléchargés au format PDF sont enregistrés sur votre poste de travail.** | Lors du téléchargement d’un projet au format PDF, le fichier est enregistré dans le dossier des téléchargements de votre poste de travail. <p>Auparavant, le téléchargement d’un projet au format PDF ouvrait le fichier PDF dans un nouvel onglet du navigateur avec une URL unique.</p><p>Pour obtenir plus d’informations, consultez [Téléchargement des projets et des données](/help/analyze/analysis-workspace/curate-share/download-send.md).</p> |  | 25 août 2025 |
| **Les projets supprimés sont immédiatement indisponibles par URL et sont supprimés des diffusions planifiées.** | Les projets supprimés sont immédiatement supprimés des diffusions planifiées et ne sont plus accessibles par leur URL.<p>Auparavant, les projets étaient inclus dans les diffusions planifiées et étaient accessibles avec leur URL pendant 60 jours après leur suppression.</p><p>Pour plus d’informations sur la suppression de projets, consultez [Vue d’ensemble des projets](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md).</p> | | Fin août 2025 |
| **Services de médias en streaming : mise à jour des champs XDM pour la collecte des données des médias en streaming dans Adobe Experience Platform** | Lors de la collecte de données des médias en streaming dans Adobe Experience Platform, les chemins d’accès aux champs XDM affichés dans la section « Chemin d’accès au champ XDM » de la documentation des paramètres des médias de streaming ne doivent plus être utilisés. Au lieu de cela, la clientèle qui a implémenté le connecteur source Analytics pour collecter des données de médias en streaming dans Platform avant le 9 mai 2025 doit migrer ses configurations existantes vers les chemins d’accès aux champs mediaReporting, comme indiqué sous l’en-tête « Chemin d’accès aux champs XDM de création de rapports » de la documentation des paramètres de médias en streaming.<p> Ces chemins d’accès aux champs se trouvent sur les pages suivantes et sont marqués comme « obsolètes » : [Paramètres audio et vidéo](https://experienceleague.adobe.com/fr/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Paramètres de publicité](https://experienceleague.adobe.com/fr/docs/media-analytics/using/implementation/variables/ad-parameters), [Paramètres de chapitre](https://experienceleague.adobe.com/fr/docs/media-analytics/using/implementation/variables/chapter-parameters), [Paramètres d’état du lecteur](https://experienceleague.adobe.com/fr/docs/media-analytics/using/implementation/variables/player-state-parameters) et [Paramètres de qualité](https://experienceleague.adobe.com/fr/docs/media-analytics/using/implementation/variables/quality-parameters). (Aucune action n’est requise de la part de la clientèle qui implémente le connecteur source Analytics après le 9 mai 2025 et qui utilise déjà uniquement les chemins XDM mediaReporting.)</p><p>L’ingestion des données sur les chemins d’accès aux champs XDM obsolètes se poursuivra jusqu’à la fin octobre 2025. Après cela, les chemins d’accès aux champs obsolètes seront intégralement supprimés et ne seront plus visibles dans l’interface d’utilisation de schéma Adobe Experience Platform, et les données seront envoyées uniquement à l’aide des chemins d’accès aux champs mediaReporting.</p><p>Pour plus d’informations, consultez [Migrer une implémentation du connecteur Source Analytics vers des champs de médias en streaming XDM mis à jour](https://experienceleague.adobe.com/fr/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields).</p><p>Pour obtenir de l’aide concernant la migration, contactez les services Adobe Consulting ou l’équipe en charge des comptes. </p> |  | Octobre 2025 |

## Correctifs dans Adobe Analytics

**Activity Map** : AN-389205 ; AN-384186
**Analysis Workspace** : AN-390102 ; AN-389066 ; AN-388841 ; AN-388687 ; AN-388478 ; AN-387089 ; AN-387044 ; AN-384560 ; AN-379213 ; AN-351639
**Classifications** : AN-390442 ; AN-390385 ; AN-389953 ; AN-389703 ; AN-389321 ; AN-389116 ; AN-388833 ; AN-388717 ; AN-387987 ; AN-383329
**Collecte de données** : AN-389320
**Flux de données and Data Warehouse** : AN-389702 ; AN-388136 ; AN-387779 ; AN-384369 ; AN-383075 ; AN-380307
**Confidentialité** :
**Report Builder** : AN-389336 ; AN-382775
**Reporting** : AN-390398
**Rapports planifiés** :
**Comparaison de segments** :
**Autres** : AN-388180 ; AN-383164 ; AN-366532


## Avis de fin de vie {#eol}

| Produit ou fonctionnalité en fin de vie | Date d’ajout ou de mise à jour | Description |
| --- | --- | --- |
| **Report Builder hérité** | 18 juin 2025 | L’ancien module complémentaire Report Builder sera supprimé en juin 2026. Tous les utilisateurs et utilisatrices doivent commencer à mettre à niveau leurs anciens classeurs vers le [nouveau Report Builder](https://experienceleague.adobe.com/fr/docs/analytics/analyze/report-builder/rb-overview). Le nouveau Report Builder est disponible pour les clientes et clients d’Adobe Analytics et de Customer Journey Analytics. Il assure la [quasi-parité des fonctionnalités](https://experienceleague.adobe.com/fr/docs/analytics/analyze/report-builder/convert-workbooks#unsupported), et propose de nombreuses nouvelles fonctionnalités pratiques et des améliorations de l’interface d’utilisation. Pour faciliter le processus de mise à niveau, le nouveau Report Builder comprend une fonction de conversion facile des classeurs. Le nouveau Report Builder n’est disponible que sous forme de module complémentaire dans Microsoft Store. De nombreuses organisations exigent un processus d’approbation interne avant que le module complémentaire ne soit mis à la disposition des utilisateurs et utilisatrices. Prévoyez suffisamment de temps pour ce processus et commencez à travailler dès maintenant avec votre organisation afin de disposer de suffisamment de temps pour mettre à jour vos classeurs avant la date de fin de validité. |
| **Accès via les domaines hérités ou via l’authentification SSO héritée** | 10 avril 2025 | Adobe prévoit de mettre à jour la manière dont les utilisateurs et utilisatrices accèdent à Adobe Analytics afin d’améliorer la sécurité et de rationaliser votre expérience de connexion. Dans le cadre de cette opération, l’accès par le biais des domaines hérités ou de l’authentification SSO héritée, y compris `my.omniture.com`, sera définitivement arrêté le **2 janvier 2026**. Après cette date, les identifiants de connexion hérités et l’authentification SSO héritée ne fonctionneront plus. Tous les utilisateurs et utilisatrices devront se connecter via `experience.adobe.com` à l’aide de leurs identifiants Adobe Experience Cloud. Si vous avez besoin d’aide avec votre Experience Cloud ID, contactez l’administration Adobe Analytics de votre entreprise ou l’[Assistance clientèle Adobe](https://helpx.adobe.com/fr/contact.html?lang=fr). |
| **API Adobe Analytics (version 1.4)** | 17 juillet 2024 | Le **12 août 2026**, les services d’API hérités d’Analytics suivants arriveront en fin de vie et seront fermés. Les intégrations actuelles créées à l’aide de ces services cesseront de fonctionner :<ul><li>API Adobe Analytics (version 1.4)</li><li>Authentification WSSE Adobe Analytics</li></ul><p>Les intégrations qui utilisent l’API Adobe Analytics (version 1.4) doivent migrer vers l’[API Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), tandis que les intégrations WSSE doivent migrer vers un protocole d’authentification basé sur OAuth dans [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Pour obtenir des réponses aux questions courantes et d’autres conseils, reportez-vous à la [FAQ sur la fin de vie des API Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md).</p> |


## AppMeasurement

Pour connaître les dernières mises à jour des versions d’AppMeasurement, reportez-vous aux [notes de mise à jour d’AppMeasurement](https://github.com/adobe/appmeasurement/releases).


## Ressources connexes

* [Notes de mise à jour précédentes pour 2025](/help/release-notes/2025.md)
* [Notes de mise à jour de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=fr)
* [Notes de mise à jour des services de médias en streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* Dernières mises à jour des [produits Adobe Experience Cloud](https://business.adobe.com/products/adobe-experience-cloud-products.html?lang=fr)
