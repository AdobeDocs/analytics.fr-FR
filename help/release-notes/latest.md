---
title: Dernières notes de mise à jour d’Analytics
description: Afficher les notes de mise à jour actuelles d’Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 792101403cf52008140f59121a2402c031221bdf
workflow-type: tm+mt
source-wordcount: '733'
ht-degree: 55%

---

# Notes de mise à jour actuelles d’Adobe Analytics (février 2022)

**Dernière mise à jour**: 24 février 2022

Découvrez les dernières mises à jour de versions des [produits Adobe Experience Cloud](https://business.adobe.com/fr/products/adobe-experience-cloud-products.html). Obtenez les derniers cours, tutoriels et documentation d’aide autonome sur Experience League.

## Nouvelles fonctionnalités d’Adobe Analytics {#aa-features}

| Fonctionnalité | Description | [Date ciblée](releases.md) |
| ----------- | ---------- | ------- |
| Mode d’aperçu du projet de Fiche d’évaluation mobile | Lancez un aperçu de l’apparence de votre fiche d’évaluation mobile dans l’application de tableaux de bord Analytics, directement à partir du créateur de Fiche d’évaluation. Le mode d’aperçu permet aux utilisateurs d’interagir avec les filtres et les graphiques de la même manière que dans l’application, ce qui leur permet de prévisualiser l’expérience avant d’enregistrer et de partager la fiche d’évaluation. Les utilisateurs peuvent également utiliser le sélecteur d’appareil en mode d’aperçu pour voir à quoi ressemblera leur fiche d’évaluation sur différents appareils. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html?lang=en#preview) | 16 février 2022 |
| Point de terminaison des projets API | Ajoutez, modifiez ou supprimez des projets Analysis Workspace à l’aide de l’API . [En savoir plus](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/projects/) | 1er février 2022 |

{style=&quot;table-layout:auto&quot;}

## Correctifs dans Adobe Analytics

* Correction de plusieurs problèmes liés à [!UICONTROL Utilisation des appels au serveur]. (AN-279134, AN-279878, AN-280802, AN-279097, AN-191284, AN-269720)
* Correction d’un problème en raison duquel Data Warehouse exportait des fichiers .csv vides. (AN-280291)
* Correction d’un problème en raison duquel les noms d’audience n’étaient pas renseignés pour les segments récents. (AN-279715)
* Correction d’un problème lié à la lenteur des rapports. (AN-280055)
* Correction de problèmes en raison desquels les classifications ne classaient pas tous les éléments de dimension. (AN-280031)

### Correctifs supplémentaires dans Adobe Analytics

AN-268093, AN-273820, AN-274435, AN-274904, AN-275356, AN-275947, AN-276160, AN-276258, AN-276705, AN-, AN-277051, AN-277957, AN-278693, AN-278882, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-AN-, AN-AN-AN-, AN-AN-AN-, AN-AN-, AN-AN-AN-, AN-AN-AN-AN-AN-, AN-AN-AN-, AN-AN-AN-AN-AN-, AN-AN-, AN-AN-AN-AN-AN-, AN-AN-AN-AN-, AN-AN-AN-, AN-AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN--AN-AN-

## Avis importants destinés aux administrateurs d’[!DNL Analytics]

**Mise à jour le 24 janvier 2022**

| Remarque | Date d’ajout ou de mise à jour | Description |
| ----------- | ---------- | ---------- |
| Suspension des tâches de Report Builder planifiées plus anciennes | 24 février 2022 | **Effectives le 15 avril 2022**, Adobe a l’intention de suspendre toutes les tâches de Report Builder planifiées qui ont été créées il y a plus de deux ans. Plus précisément, cette pause s’applique à toutes les tâches créées avant le 31 janvier 2020. Aucune tâche, aucun classeur ni aucune donnée ne sera supprimé. Toutefois, les tâches identifiées comme ayant plus de deux ans seront suspendues et aucune autre tâche planifiée ne sera envoyée. [En savoir plus](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| Expiration de l’extension de fin de vie de liste autorisée pour les intégrations héritées OAuth/JWT d’Analytics | 14 janvier 2022 | Le **25 mai 2022**, lʼextension de liste autorisée de [fin de vie de lʼAPI Analytics 1.3, de lʼAPI SOAP 1.4 et des intégrations héritées OAuth/JWT d’Analytics](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) arrive à expiration. Cette extension visait à offrir aux clients utilisant des identifiants OAuth/JWT [!DNL Adobe Analytics] un délai supplémentaire pour migrer leurs intégrations clientes vers les [identifiants Adobe IMS](https://developer.adobe.com/console). Cette expiration affecte (sans toutefois s’y limiter) les clients d’[!DNL Adobe Analytics Livestream] et d’[!DNL Adobe Campaign] qui n’ont pas terminé leurs migrations IMS requises. Les clients qui utilisent actuellement les identifiants OAuth/JWT herités d’[!DNL Analytics] via l’extension de liste autorisée et qui ne terminent pas leur migration vers les identifiants IMS d’ici le 25 mai 2022 perdront l’accès aux services Adobe. Les clients Livestream peuvent se référer à ces [instructions](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) lors de la migration de leurs applications clientes vers les identifiants IMS. Les clients [!DNL Campaign] peuvent contacter leur équipe de compte Adobe pour effectuer la mise à niveau vers la dernière version de [!DNL Campaign]. |
| Fin de vie de [!DNL Reports & Analytics] | 4 janvier 2022 | À compter du **31 décembre 2023**, Adobe a l’intention de mettre fin à [!DNL Reports & Analytics] et aux rapports et fonctionnalités associés. [!DNL Reports & Analytics] repose sur des rapports, des visualisations et une technologie sous-jacente qui ne répondent plus aux normes technologiques d’Adobe. La plupart des fonctionnalités de [!DNL Reports & Analytics] sont disponibles dans [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=fr). Depuis la publication d’Analysis Workspace en 2015, les fonctionnalités de [!DNL Reports & Analytics] ont migré vers Analysis Workspace, de telle sorte quʼun seuil de parité en matière de workflow a été atteint. [Cet avis](https://spark.adobe.com/page/6WnF8JK6IRDhf/) décrit le processus de fin de vie. |
| Mise à niveau des services SFTP (Secure File Transfer Protocol) | 13 janvier 2022 | Le **2 mai 2022**, [!DNL Adobe Analytics] effectuera la mise à niveau de ses services SFTP (Secure File Transfer Protocol) afin d’offrir des améliorations de sécurité pour les transferts de fichiers. Suite à la mise à niveau, certaines configurations de clients SFTP ne seront plus prises en charge. Nous ajouterons également plusieurs options de connexion, qui seront disponibles dʼici le **1er mars 2022**. Cela a un impact uniquement sur les données envoyées à ou récupérées à partir d’Adobe Analytics par SFTP. Le protocole FTP n’est pas affecté. Pour éviter des interruptions de service, veillez à ce que vos clients SFTP (code, outils, services) soient conformes aux modifications détaillées. [here](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=fr). |

## AppMeasurement {#appm}

Pour connaître les dernières mises à jour des versions d’AppMeasurement (version 2.22.4), reportez-vous aux [Notes de mise à jour d’AppMeasurement pour JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=fr).

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics]  Notes de mise à jour](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=en)
