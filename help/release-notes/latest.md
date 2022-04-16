---
title: Dernières notes de mise à jour dʼAnalytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 614dff141e4201d09dc7e585e9f8744e4b37faf1
workflow-type: tm+mt
source-wordcount: '992'
ht-degree: 40%

---

# Notes de mise à jour actuelles d’Adobe Analytics (avril 2022)

**Dernière mise à jour**: 13 avril 2022

* Pour les notes de mise à jour de mars 2022, accédez à [here](/help/release-notes/2022.md).

* Pour consulter les notes de mise à jour du Customer Journey Analytics, accédez à [here](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=fr).

* Pour les notes de mise à jour de Media Analytics, accédez à [here](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=en).

* Découvrez les dernières mises à jour de versions des [produits Adobe Experience Cloud](https://business.adobe.com/fr/products/adobe-experience-cloud-products.html). Obtenez les derniers cours, tutoriels et documentation d’aide autonome sur Experience League.


| Fonctionnalité | Description | [Date ciblée](releases.md) |
| ----------- | ---------- | ------- |
| Mises à jour des landing pages Adobe Analytics | Mises à jour de la page d’entrée conjointe Workspace/Reports &amp; Analytics qui améliore la convivialité et la facilité de navigation. [En savoir plus](/help/analyze/landing.md) | 20 avril 2022 |
| [!UICONTROL Élément suivant] ou [!UICONTROL Élément précédent] Panneau Espace de travail | Le [!UICONTROL Élément suivant ou précédent] vous permet d’explorer les éléments qui suivent ou précèdent un élément de dimension de votre choix. Par exemple, utilisez-le si vous souhaitez afficher les pages suivantes ou précédentes d’une page de produit spécifique, d’un canal marketing ou même d’un type de périphérique. Ce panneau va au-delà des rapports précédents/suivants hérités, car il vous permet d’examiner n’importe quelle dimension et ne nécessite aucune nouvelle implémentation pour obtenir des informations. | 20 avril 2022 |
| [!UICONTROL Résumé de la page] Panneau Espace de travail | Le [!UICONTROL Résumé de la page] fournit une analyse approfondie d’une page de votre choix. Il fournit les mêmes détails que l’ancien Reports &amp; Analytics. [!UICONTROL Résumé de la page] rapport, plus beaucoup plus. | 20 avril 2022 |

{style=&quot;table-layout:auto&quot;}

## Correctifs dans Adobe Analytics

* Correction d’un problème dans les flux de données en raison duquel les dates de début et de fin étaient automatiquement modifiées après l’enregistrement du flux de données lors de la création à partir de l’interface utilisateur des flux de données. Les dates étaient mises à jour par elles-mêmes d&#39;un jour. (AN-281262)

* Correction d’un problème qui empêchait le renouvellement des projets planifiés par courrier électronique. (AN-283622)

### Correctifs supplémentaires dans Adobe Analytics

AN-274486; AN-279258; AN-279995; AN-280918; AN-281423; AN-282084; AN-282435; AN-283508; AN-283517; AN-283706; AN-283762; AN-283921; AN-284195; AN-284663; AN-284573; AN-284721; AN-284790; AN-284867; AN-284870; AN-284872; AN-284884; AN-284914; AN-284930; AN-284933; AN-284967; AN-284970; AN-285187; AN-285328; AN-285337; AN-285375; AN-285447; AN-285724; AN-285753; AN-285761;

## Avis importants à l’intention des administrateurs d’Adobe Analytics

| Remarque | Date d’ajout ou de mise à jour | Description |
| ----------- | ---------- | ---------- |
| Droits Analyses entre appareils (CDA) | 13 avril 2022 | Efficace **1er mai 2022**, toute nouvelle implémentation de [CDA](/help/components/cda/overview.md) ne peut pas contenir plus de trois identifiants de suite de rapports (RSID) par client. |
| Modification de la manière dont Adobe Analytics gère les données A4T collectées via Experience Edge | 31 mars 2022 | Le 7 mars 2022, nous avons modifié la manière dont nous gérons certains appels provenant d’Experience Edge qui incluent du contenu Target destiné aux rapports Analytics for Target (A4T). À compter du 7 mars, tous les accès avec du contenu de rapport A4T ont été modifiés afin qu’ils n’aient pas été traités comme des événements de page vue ou de lien. Démarrage **31 mars 2022**, nous avons modifié notre logique pour qu’elle soit plus sélective, de sorte que les événements Page vue et Clic standard ne soient pas modifiés. À l’avenir, les seuls événements qui seront modifiés seront les appels de personnalisation uniquement qui auront uniquement du contenu A4T. |
| Mise à jour des méthodes de chiffrement de navigateur prises en charge pour certains clients | 28 mars 2022 | Adobe offre deux niveaux de sécurité de chiffrement pour répondre aux besoins divers des clients en matière de sécurité dans la collecte de données propriétaires. Activé **23 juin 2022** nous supprimerons la prise en charge de certains algorithmes de chiffrement HTTPS, appelés chiffrements, pour les clients dont le niveau de sécurité est défini sur &quot;Élevé&quot;. Cela signifie que certains systèmes d’exploitation plus anciens ne pourront plus envoyer de données à Analytics, car ils ne prennent pas en charge les méthodes de chiffrement modernes. Les clients qui utilisent les paramètres de sécurité du chiffrement standard par défaut ne seront pas affectés. Tous les clients utilisant actuellement le paramètre &quot;Élevé&quot; ont déjà été contactés directement. Vous trouverez ici une liste détaillée des chiffrements concernés par cette modification. |
| Suspension des rapports planifiés plus anciens | 12 avril 2022 | Efficace **21 avril 2022**, Adobe a l’intention de suspendre tous les rapports planifiés dont la date de création est supérieure à deux ans (créés avant le 31 janvier 2020). Aucun rapport ou donnée ne sera supprimé. Seuls les rapports identifiés comme antérieurs à deux ans seront suspendus et aucun autre rapport planifié ne sera envoyé. En savoir plus |
| Mises à jour des zones géographiques ISO 2022 | 11 mars 2021 | Adobe effectuera des mises à jour de région ISO 2022 sur **10 juin 2022**. Des mises à jour mineures des informations géographiques sont attendues à cette version. |
| Suspension des anciennes tâches planifiées de Report Builder | 12 avril 2022 | Efficace **21 avril 2022**, Adobe a l’intention de suspendre toutes les tâches de Report Builder planifiées qui ont été créées il y a plus de deux ans. Toutes les tâches créées avant le 31 janvier 2020 sont concernées. Aucune tâche, aucun classeur ni aucune donnée ne sera supprimé. Toutefois, les tâches identifiées comme datant de plus de deux ans seront suspendues et aucune autre tâche planifiée ne sera envoyée. En savoir plus |
| Expiration de l’extension de fin de vie de liste autorisée pour les intégrations héritées OAuth/JWT d’Analytics | 14 janvier 2022 | Le **25 mai 2022**, lʼextension de liste autorisée de [fin de vie de lʼAPI Analytics 1.3, de lʼAPI SOAP 1.4 et des intégrations héritées OAuth/JWT d’Analytics](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) arrive à expiration. Cette extension visait à offrir aux clients utilisant des identifiants OAuth/JWT [!DNL Adobe Analytics] un délai supplémentaire pour migrer leurs intégrations clientes vers les [identifiants Adobe IMS](https://developer.adobe.com/console). Cette expiration affecte (sans toutefois s’y limiter) les clients d’[!DNL Adobe Analytics Livestream] et d’[!DNL Adobe Campaign] qui n’ont pas terminé leurs migrations IMS requises. Les clients qui utilisent actuellement les identifiants OAuth/JWT herités d’[!DNL Analytics] via l’extension de liste autorisée et qui ne terminent pas leur migration vers les identifiants IMS d’ici le 25 mai 2022 perdront l’accès aux services Adobe. Les clients Livestream peuvent se référer à ces [instructions](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) lors de la migration de leurs applications clientes vers les identifiants IMS. Les clients [!DNL Campaign] peuvent contacter leur équipe de compte Adobe pour effectuer la mise à niveau vers la dernière version de [!DNL Campaign]. |
| Fin de vie de [!DNL Reports & Analytics] | 4 janvier 2022 | À compter du **31 décembre 2023**, Adobe prévoit dʼabandonner [!DNL Reports & Analytics] et ses rapports et fonctionnalités associés. [!DNL Reports & Analytics] repose sur des rapports, des visualisations et une technologie sous-jacente qui ne répondent plus aux normes technologiques d’Adobe. La plupart des fonctionnalités de [!DNL Reports & Analytics] sont disponibles dans [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=fr). Depuis la publication d’Analysis Workspace en 2015, les fonctionnalités de [!DNL Reports & Analytics] ont migré vers Analysis Workspace, de telle sorte quʼun seuil de parité en matière de workflow a été atteint. [Cet avis](https://spark.adobe.com/page/6WnF8JK6IRDhf/) décrit le processus de fin de vie. |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement {#appm}

Pour connaître les dernières mises à jour des versions d’AppMeasurement (version 2.22.4), reportez-vous aux [Notes de mise à jour d’AppMeasurement pour JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=fr).

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics] notes de mise à jour](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=en)
