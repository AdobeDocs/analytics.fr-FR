---
title: Dernières notes de mise à jour dʼAnalytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 1e8aa373bcb2714c6b2c7605e1ea7c7c462b89e7
workflow-type: tm+mt
source-wordcount: '1166'
ht-degree: 45%

---

# Notes de mise à jour actuelles d’Adobe Analytics (mars 2022)

**Dernière mise à jour : 12 avril 2022**

* Pour les notes de mise à jour de février 2022, accédez à [here](/help/release-notes/2022.md).
* Pour consulter les notes de mise à jour du Customer Journey Analytics, accédez à [here](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=fr)
* Pour les notes de mise à jour de Media Analytics, accédez à [here](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=en)
* Découvrez les dernières mises à jour de versions des [produits Adobe Experience Cloud](https://business.adobe.com/fr/products/adobe-experience-cloud-products.html). Obtenez les derniers cours, tutoriels et documentation d’aide autonome sur Experience League.

## Nouvelles fonctionnalités d’Adobe Analytics {#aa-features}

| Fonctionnalité | Description | [Date ciblée](releases.md) |
| ----------- | ---------- | ------- |
| Annotations dans Workspace | Les annotations dans Workspace vous permettent de communiquer efficacement des nuances de données contextuelles et des informations à votre organisation. [En savoir plus](/help/analyze/analysis-workspace/components/annotations/overview.md) | Le déploiement progressif commence le 23 mars 2022. Disponibilité générale : 11 avril 2022 |
| Mises à jour des landing pages Adobe Analytics | Mises à jour de la page d’entrée conjointe Workspace/Reports &amp; Analytics qui améliore la convivialité et la facilité de navigation. [En savoir plus](/help/analyze/landing.md) | 20 avril 2022 |
| [!UICONTROL Élément suivant] ou [!UICONTROL Élément précédent] Panneau Espace de travail | Le [!UICONTROL Élément suivant ou précédent] vous permet d’explorer les éléments qui suivent ou précèdent un élément de dimension de votre choix. Par exemple, utilisez-le si vous souhaitez afficher les pages suivantes ou précédentes d’une page de produit spécifique, d’un canal marketing ou même d’un type de périphérique. Ce panneau va au-delà des rapports précédents/suivants hérités, car il vous permet d’examiner n’importe quelle dimension et ne nécessite aucune nouvelle implémentation pour obtenir des informations. | 20 avril 2022 |
| [!UICONTROL Résumé de la page] Panneau Espace de travail | Le [!UICONTROL Résumé de la page] fournit une analyse approfondie d’une page de votre choix. Il fournit les mêmes détails que l’ancien Reports &amp; Analytics. [!UICONTROL Résumé de la page] rapport, plus beaucoup plus. | 20 avril 2022 |

{style=&quot;table-layout:auto&quot;}

## Correctifs dans Adobe Analytics

* Correction d’un problème qui entraînait une erreur lors de la tentative d’accès à Activity Map. (AN-267177)
* Correction d’un problème en raison duquel les transferts de ressources utilisateur échouaient. (AN-279813)
* Correction de problèmes liés au panneau Espace de travail A4T. (AN-281594 ; AN-282418)
* Correction d’un problème en raison duquel certains utilisateurs ne pouvaient pas accéder à Adobe Analytics. (AN-282776)
* Correction de problèmes en raison desquels certaines suites de rapports nouvellement créées ne collectaient pas de données. (AN-283114, AN-283311)
* Correction de problèmes liés aux messages électroniques de flux de données incorrectement envoyés. (AN-280255 ; AN-282051)

### Correctifs supplémentaires dans Adobe Analytics

AN-256929; AN-270937; AN-272158; AN-275130; AN-277830; AN-278635; AN-279066; AN-279683; AN-279899; AN-280504; AN-280617; AN-280663; AN-281423; AN-281523; AN-281608; AN-281671; AN-281963; AN-282027; AN-282218; AN-282593; AN-282605; AN-282632; AN-282654; AN-282694; AN-282744; AN-282756; AN-282804; AN-282838; AN-282862; AN-282903; AN-282937; AN-282892; AN-283315; AN-283338; AN-283388; AN-283417; AN-283474; AN-283511; AN-283691, AN-283895; AN-283943; AN-283957; AN-284030; AN-284100; AN-284142; AN-284162

## Avis importants à l’intention des administrateurs d’Adobe Analytics

| Remarque | Date d’ajout ou de mise à jour | Description |
| ----------- | ---------- | ---------- |
| Modification de la manière dont Analytics gère les données A4T collectées via Experience Edge | 31 mars 2022 | Activé **7 mars 2022**, nous avons modifié la manière dont nous gérons certains appels provenant d’Experience Edge qui incluent du contenu Target destiné aux rapports Analytics for Target (A4T). À compter du 7 mars, tous les accès avec du contenu de rapport A4T ont été modifiés afin qu’ils n’aient pas été traités comme des événements de page vue ou de lien. **À compter du 31 mars 2022**, nous avons modifié notre logique pour qu’elle soit plus sélective, de sorte que les événements Page vue et Clic standard ne soient pas modifiés. À l’avenir, les seuls événements qui seront modifiés seront les appels de personnalisation uniquement qui auront uniquement du contenu A4T. |
| Mise à jour des méthodes de chiffrement de navigateur prises en charge pour certains clients | 28 mars 2022 | Adobe offre deux niveaux de sécurité de chiffrement pour répondre aux besoins divers des clients en matière de sécurité dans la collecte de données propriétaires. Activé **23 juin 2022** nous supprimerons la prise en charge de certains algorithmes de chiffrement HTTPS, appelés chiffrements, pour les clients dont le niveau de sécurité est défini sur &quot;Élevé&quot;. Cela signifie que certains systèmes d’exploitation plus anciens ne pourront plus envoyer de données à Analytics, car ils ne prennent pas en charge les méthodes de chiffrement modernes. Les clients qui utilisent les paramètres de sécurité du chiffrement standard par défaut ne seront pas affectés. Tous les clients utilisant actuellement le paramètre &quot;Élevé&quot; ont déjà été contactés directement. Vous trouverez une liste détaillée des chiffrements affectés par cette modification. [here](/help/technotes/rdc/encryption-algos.md). |
| Suspension des rapports planifiés plus anciens | 12 avril 2022 | Efficace **21 avril 2022**, Adobe a l’intention de suspendre tous les rapports planifiés dont la date de création est supérieure à deux ans (créés avant le 31 janvier 2020). Aucun rapport ou donnée ne sera supprimé. Seuls les rapports identifiés comme antérieurs à deux ans seront suspendus et aucun autre rapport planifié ne sera envoyé. Pour tout rapport dont la date de création est inférieure à deux ans sans date d’expiration (ou dont la date d’expiration est supérieure à deux ans), une date d’expiration de 9 mois par défaut est appliquée. [En savoir plus](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| Mises à jour des zones géographiques ISO 2022 | 11 mars 2021 | Adobe effectuera des mises à jour de région ISO 2022 sur **10 juin 2022**. Des mises à jour mineures des informations géographiques sont attendues à cette version. |
| Suspension des anciennes tâches planifiées de Report Builder | 12 avril 2022 | À compter du **21 avril 2022**, Adobe prévoit de suspendre toutes les tâches planifiées de Report Builder créées il y a plus de deux ans. Toutes les tâches créées avant le 31 janvier 2020 sont concernées. Aucune tâche, aucun classeur ni aucune donnée ne sera supprimé. Toutefois, les tâches identifiées comme datant de plus de deux ans seront suspendues et aucune autre tâche planifiée ne sera envoyée. [En savoir plus](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| Expiration de l’extension de fin de vie de liste autorisée pour les intégrations héritées OAuth/JWT d’Analytics | 14 janvier 2022 | Le **25 mai 2022**, lʼextension de liste autorisée de [fin de vie de lʼAPI Analytics 1.3, de lʼAPI SOAP 1.4 et des intégrations héritées OAuth/JWT d’Analytics](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) arrive à expiration. Cette extension visait à offrir aux clients utilisant des identifiants OAuth/JWT [!DNL Adobe Analytics] un délai supplémentaire pour migrer leurs intégrations clientes vers les [identifiants Adobe IMS](https://developer.adobe.com/console). Cette expiration affecte (sans toutefois s’y limiter) les clients d’[!DNL Adobe Analytics Livestream] et d’[!DNL Adobe Campaign] qui n’ont pas terminé leurs migrations IMS requises. Les clients qui utilisent actuellement les identifiants OAuth/JWT herités d’[!DNL Analytics] via l’extension de liste autorisée et qui ne terminent pas leur migration vers les identifiants IMS d’ici le 25 mai 2022 perdront l’accès aux services Adobe. Les clients Livestream peuvent se référer à ces [instructions](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) lors de la migration de leurs applications clientes vers les identifiants IMS. Les clients [!DNL Campaign] peuvent contacter leur équipe de compte Adobe pour effectuer la mise à niveau vers la dernière version de [!DNL Campaign]. |
| Mise à niveau des services SFTP (Secure File Transfer Protocol) | 3 mars 2022 | Le **15 mai 2022**, [!DNL Adobe Analytics] effectuera la mise à niveau de ses services SFTP (Secure File Transfer Protocol) afin d’offrir des améliorations de sécurité pour les transferts de fichiers. Suite à la mise à niveau, certaines configurations de clients SFTP ne seront plus prises en charge. Nous ajouterons également plusieurs options de connexion, qui seront disponibles dʼici le **1er mars 2022**. Cela n’affecte que les données envoyées ou récupérées depuis Adobe Analytics via SFTP. Le protocole FTP n’est pas affecté. Afin d’éviter toute perturbation du service, assurez-vous que vos clients SFTP (code, outils, services) sont compatibles avec les modifications détaillées [ici](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=fr). |
| Fin de vie de [!DNL Reports & Analytics] | 4 janvier 2022 | À compter du **31 décembre 2023**, Adobe prévoit dʼabandonner [!DNL Reports & Analytics] et ses rapports et fonctionnalités associés. [!DNL Reports & Analytics] repose sur des rapports, des visualisations et une technologie sous-jacente qui ne répondent plus aux normes technologiques d’Adobe. La plupart des fonctionnalités de [!DNL Reports & Analytics] sont disponibles dans [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=fr). Depuis la publication d’Analysis Workspace en 2015, les fonctionnalités de [!DNL Reports & Analytics] ont migré vers Analysis Workspace, de telle sorte quʼun seuil de parité en matière de workflow a été atteint. [Cet avis](https://spark.adobe.com/page/6WnF8JK6IRDhf/) décrit le processus de fin de vie. |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement {#appm}

Pour connaître les dernières mises à jour des versions d’AppMeasurement (version 2.22.4), reportez-vous aux [Notes de mise à jour d’AppMeasurement pour JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=fr).

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics] notes de mise à jour](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=en)
