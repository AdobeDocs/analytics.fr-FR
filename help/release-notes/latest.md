---
title: Dernières notes de mise à jour dʼAnalytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: c29515da8c74ad3332aa9797db9de505af7fe3aa
workflow-type: tm+mt
source-wordcount: '1070'
ht-degree: 57%

---

# Notes de mise à jour actuelle d’Adobe Analytics (avril 2022)

**Dernière mise à jour**: 28 avril 2022

## Ressources connexes

* [Notes de mise à jour précédentes pour 2022](/help/release-notes/2022.md)
* [Notes de mise à jour de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Notes de mise à jour de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* Les dernières mises à jour de version pour [Produits Adobe Experience Cloud](https://business.adobe.com/fr/products/adobe-experience-cloud-products.html)

## Nouvelles fonctionnalités d’Adobe Analytics

| Fonctionnalité | Description | [Date ciblée](releases.md) |
| ----------- | ---------- | ------- |
| Mises à jour de la page de destination dʼAdobe Analytics | Mises à jour de la page de destination conjointe Analysis Workspace / Reports &amp; Analytics qui améliorent la convivialité et la facilité de navigation. [En savoir plus](/help/analyze/landing.md) | 20 avril 2022 |
| Panneau Espace de travail [!UICONTROL Élément suivant] ou [!UICONTROL Élément précédent] | Le panneau [!UICONTROL Élément suivant ou précédent] vous permet d’explorer les éléments qui suivent ou précèdent un élément de dimension de votre choix. Par exemple, utilisez-le si vous souhaitez voir les pages suivantes ou précédentes d’une page produit spécifique, d’un canal marketing ou même d’un type d’appareil. Ce panneau va au-delà des rapports précédents/suivants hérités, car il vous permet d’examiner n’importe quelle dimension et ne nécessite aucune nouvelle implémentation pour obtenir des insights. [En savoir plus](/help/analyze/analysis-workspace/c-panels/next-previous.md) | 20 avril 2022 |
| Panneau de l’espace de travail [!UICONTROL Synthèse de la page] | Le panneau [!UICONTROL Synthèse de la page] fournit une analyse approfondie d’une page de votre choix. Il fournit les mêmes détails que le rapport hérité [!UICONTROL Synthèse de la page] Reports &amp; Analytics, et bien plus encore. [En savoir plus](/help/analyze/analysis-workspace/c-panels/page-summary.md) | 20 avril 2022 |
| Suppression de l’exigence de `x-proxy-global-company-id` en-tête des appels API 2.0 | Les API d’Adobe Analytics 2.0 ne nécessitent plus le `x-proxy-global-company-id` , car ces informations font partie de l’URL du point de terminaison . Vous pouvez toujours inclure cet en-tête, mais vous n’obtenez plus d’erreur s’il manque. | 20 avril 2022 |

{style=&quot;table-layout:auto&quot;}

## Correctifs dans Adobe Analytics

* Correction d’un problème dans les flux de données, où les dates de début et de fin changeaient automatiquement après l’enregistrement du flux de données lors de sa création à partir de l’interface utilisateur du flux de données. Les dates s’actualisaient d’un jour. (AN-281262)
* Correction d’un problème qui empêchait la reconduction des projets planifiés via un lien e-mail. (AN-283622)
* Correction d’un problème en raison duquel les versions récentes d’Apple Safari et de Microsoft Edge n’étaient pas correctement identifiées dans la table de recherche de type navigateur d’Adobe. Similaire à quand [les versions du navigateur sont mises à jour.](/help/components/dimensions/browser.md), les mises à jour apportées aux tables de recherche de type navigateur ne corrigent que les données à partir de maintenant. Les tables de recherche pour la version du navigateur ont été mises à jour le 20 avril et celles pour le type de navigateur ont été mises à jour le 28 avril. (AN-284872) AN-285753; AN-286257)

### Correctifs supplémentaires dans Adobe Analytics

AN-274486; AN-279258; AN-279995; AN-280918; AN-281423; AN-282084; AN-282435; AN-283508; AN-283517; AN-283706; AN-283762; AN-283921; AN-284195; AN-284663; AN-284573; AN-284721; AN-284790; AN-284867; AN-284870; AN-284872; AN-284884; AN-284914; AN-284930; AN-284933; AN-284967; AN-284970; AN-285187; AN-285328; AN-285337; AN-285375; AN-285447; AN-285724; AN-285753; AN-285761

## Avis importants pour les administrateurs d’Adobe Analytics

| Remarque | Date d’ajout ou de mise à jour | Description |
| ----------- | ---------- | ---------- |
| **Droits d’Analytics sur l’ensemble des appareils (CDA)** | 13 avril 2022 | Efficace **1er mai 2022**, toute nouvelle implémentation de [CDA](/help/components/cda/overview.md) sont limités à trois identifiants de suite de rapports (RSID) au maximum par client. |
| **Modification de la façon dont Adobe Analytics traite les données A4T collectées via Experience Edge** | 31 mars 2022 | Le 7 mars 2022, Analytics a modifié la manière dont il gère certains appels provenant d’Experience Edge qui incluent du contenu Target destiné à la création de rapports Analytics for Target (A4T). À compter du 7 mars, tous les accès avec du contenu de rapport A4T sont modifiés afin qu’ils ne soient pas traités comme des événements de page vue ou de lien. Démarrage **31 mars 2022**, la logique est plus sélective, de sorte que les événements Page vue et Clic standard ne soient pas modifiés. À l’avenir, les seuls événements qui sont modifiés sont les appels de personnalisation uniques qui ne comportent que du contenu A4T. |
| **Mise à jour des méthodes de chiffrement du navigateur prises en charge pour certains clients** | 28 mars 2022 | Adobe propose deux niveaux de sécurité de chiffrement pour répondre aux différents besoins des clients en matière de sécurité de la collecte de données de première main. Activé **23 juin 2022** La prise en charge de certains algorithmes de chiffrement HTTPS, appelés chiffrements, est supprimée pour les clients dont le niveau de sécurité est défini sur &quot;Élevé&quot;. Cette action signifie que certains systèmes d’exploitation plus anciens ne peuvent plus envoyer de données à Analytics, car ils ne prennent pas en charge les méthodes de chiffrement modernes. Les clients qui utilisent les paramètres de sécurité du chiffrement standard par défaut ne sont pas affectés. Tous les clients qui utilisent actuellement le paramètre « Élevé » ont déjà été contactés directement. Vous trouverez ici une liste détaillée des chiffrements concernés par ce changement. |
| **Suspension des anciens rapports planifiés** | 12 avril 2022 | À compter du **20 avril 2022**, Adobe a l’intention de suspendre tous les rapports planifiés dont la date de création est supérieure à deux ans (créés avant le 31 janvier 2020). Aucun rapport ou donnée n’est supprimé. Seuls les rapports identifiés comme antérieurs à deux ans sont suspendus et aucun rapport planifié supplémentaire n’est envoyé. En savoir plus |
| **Mises à jour des zones géographiques ISO 2022** | 11 mars 2021 | Adobe prévoit d’effectuer des mises à jour de région ISO 2022 sur **10 juin 2022**. Attendez-vous à voir des mises à jour mineures des informations géographiques après cette publication. |
| **Suspension des anciennes tâches planifiées de Report Builder** | 12 avril 2022 | À compter du **20 avril 2022**, Adobe prévoit de suspendre toutes les tâches planifiées de Report Builder qui ont été créées il y a plus de deux ans. Toutes les tâches créées avant le 31 janvier 2020 sont concernées. Aucune tâche, aucun classeur ou aucune donnée n’est supprimée. Toutefois, les tâches identifiées comme ayant plus de deux ans sont suspendues et aucune autre tâche planifiée n’est envoyée. En savoir plus |
| **Expiration de l’extension de fin de vie de liste autorisée pour les intégrations héritées OAuth/JWT d’Analytics** | 14 janvier 2022 | Activé **25 mai 2022**, la variable [API Analytics 1.3, API SOAP 1.4 et API OAuth/JWT héritées d’Analytics](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) L’extension de liste autorisée expire. Cette extension visait à offrir aux clients utilisant des identifiants OAuth/JWT [!DNL Adobe Analytics] un délai supplémentaire pour migrer leurs intégrations clientes vers les [identifiants Adobe IMS](https://developer.adobe.com/console). Cette expiration affecte (sans toutefois s’y limiter) les clients d’[!DNL Adobe Analytics Livestream] et d’[!DNL Adobe Campaign] qui n’ont pas terminé leurs migrations IMS requises. Clients qui utilisent actuellement des [!DNL Analytics] Les informations d’identification OAuth/JWT via l’extension de liste autorisée et qui ne terminent pas leur migration vers les informations d’identification IMS avant le 25 mai 2022 perdent l’accès aux services Adobe. Les clients Livestream peuvent se référer à ces [instructions](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) lors de la migration de leurs applications clientes vers les identifiants IMS. Les clients [!DNL Campaign] peuvent contacter leur équipe de compte Adobe pour effectuer la mise à niveau vers la dernière version de [!DNL Campaign]. |
| **Fin de vie de[!DNL Reports & Analytics]** | 4 janvier 2022 | À compter du **31 décembre 2023**, Adobe prévoit dʼabandonner [!DNL Reports & Analytics] et ses rapports et fonctionnalités associés. [!DNL Reports & Analytics] repose sur des rapports, des visualisations et une technologie sous-jacente qui ne répondent plus aux normes technologiques d’Adobe. La plupart des fonctionnalités de [!DNL Reports & Analytics] sont disponibles dans [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=fr). Depuis la publication d’Analysis Workspace en 2015, les fonctionnalités de [!DNL Reports & Analytics] ont migré vers Analysis Workspace, de telle sorte quʼun seuil de parité en matière de workflow a été atteint. [Cet avis](https://spark.adobe.com/page/6WnF8JK6IRDhf/) décrit le processus de fin de vie. |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement {#appm}

Pour connaître les dernières mises à jour des versions d’AppMeasurement (version 2.22.4), reportez-vous aux [Notes de mise à jour d’AppMeasurement pour JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=fr).

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics] notes de mise à jour](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=en)
