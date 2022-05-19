---
title: Dernières notes de mise à jour dʼAnalytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: b9bf373d7d62d7b6df405629cdf304246b80649f
workflow-type: tm+mt
source-wordcount: '905'
ht-degree: 82%

---

# Notes de mise à jour actuelles d’Adobe Analytics (mai 2022)

**Dernière mise à jour**: 17 mai 2022

## Ressources connexes

* [Notes de mise à jour précédentes pour 2022](/help/release-notes/2022.md)
* [Notes de mise à jour de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=fr)
* [Notes de mise à jour de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* Dernières mises à jour des [produits Adobe Experience Cloud](https://business.adobe.com/fr/products/adobe-experience-cloud-products.html)

## Nouvelles fonctionnalités d’Adobe Analytics

| Fonctionnalité | Description | [Date ciblée](releases.md) |
| ----------- | ---------- | ------- |
| Renseignement des dimensions et des mesures de cycle de vie via Experience Edge | Les données de cycle de vie mobile envoyées via Experience Edge apparaîtront désormais dans les rapports Analytics. Consultez la documentation pour plus d’informations sur les données du cycle de vie collectées via Experience Edge et sur la manière dont elles correspondent aux rapports du cycle de vie existants. [En savoir plus - bientôt] | 27 mai 2022 |

{style=&quot;table-layout:auto&quot;}

### Correctifs dans Adobe Analytics

(Correctifs pour plusieurs clients)

S.O.

### Correctifs supplémentaires dans Adobe Analytics

(Correctifs pour les clients individuels)

AN-274429; AN-279640; AN-280918; AN-280945; AN-282884; AN-283565; AN-284785; AN-284814; AN-284854; AN-284989; AN-285244; AN-285253; AN-285432; AN-285528; AN-285535; AN-285710; AN-286255; AN-286340; AN-286434; AN-286454; AN-286630; AN-286716; AN-286854; AN-286911

### Avis importants pour les administrateurs d’Adobe Analytics

| Remarque | Date d’ajout ou de mise à jour | Description |
| ----------- | ---------- | ---------- |
| **Mise à niveau SFTP** | 9 mai 2022 | Auparavant, nous avions annoncé que l’Adobe allait mettre à niveau ses services SFTP (Secure File Transfer Protocol) en mai 2022 afin de fournir une sécurité améliorée pour le transfert de fichiers. Nous avons reporté cet upgrade à l&#39;été 2022. Lorsque cette modification aura lieu, certaines configurations de client SFTP ne seront plus prises en charge. Cela n’affecte que les données envoyées ou récupérées depuis Adobe Analytics via SFTP. Le protocole FTP n’est pas affecté. Afin d’éviter toute perturbation du service, assurez-vous que vos clients SFTP (code, outils, services) sont compatibles avec les modifications détaillées [ici](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=fr). |
| **Droits relatifs à Analytics sur l’ensemble des appareils (CDA)** | 13 avril 2022 | Efficace **1er mai 2022**, toute nouvelle mise en oeuvre de [CDA](/help/components/cda/overview.md) sont limités à trois identifiants de suite de rapports (RSID) au maximum par client. |
| **Modification de la façon dont Adobe Analytics traite les données A4T collectées via Experience Edge** | 31 mars 2022 | Le 7 mars 2022, Analytics a modifié la façon de gérer certains appels provenant d’Experience Edge et comprenant du contenu Target destiné aux rapports Analytics for Target (A4T). À partir du 7 mars, tous les accès avec du contenu destiné aux rapports A4T ont été modifiés afin de ne pas être traités comme des événements de type Page vue ou Lien. Depuis le **31 mars 2022**, la logique est plus sélective, de sorte que les événements Page vue et Clic standards ne soient pas modifiés. À l’avenir, les seuls événements qui seront modifiés seront uniquement les appels de personnalisation contenant exclusivement du contenu A4T. |
| **Mise à jour des méthodes de chiffrement du navigateur prises en charge pour certains clients** | 28 mars 2022 | Adobe propose deux niveaux de sécurité de chiffrement pour répondre aux différents besoins des clients en matière de sécurité de la collecte de données de première main. Le **23 juin 2022**, nous supprimerons la prise en charge de certains algorithmes de chiffrement HTTPS, appelés chiffrements, pour les clients dont le niveau de sécurité est défini sur « Élevé ». Cela signifie que certains systèmes d’exploitation plus anciens ne pourront plus envoyer de données à Analytics, car ils ne prennent pas en charge les méthodes de chiffrement modernes. Les clients utilisant les paramètres de sécurité de chiffrement « standard » par défaut ne seront pas concernés. Tous les clients qui utilisent actuellement le paramètre « Élevé » ont déjà été contactés directement. Une liste détaillée des chiffrements concernés par cette modification est disponible ici. |
| **Suspension des anciens rapports planifiés** | 12 avril 2022 | À compter du **20 avril 2022**, Adobe a l’intention de suspendre tous les rapports planifiés dont la date de création est supérieure à deux ans (créés avant le 31 janvier 2020). Aucun rapport ou donnée n’est supprimé. Seuls les rapports identifiés comme ayant plus de deux ans seront suspendus et aucun autre rapport planifié ne sera envoyé. En savoir plus |
| **Mises à jour des zones géographiques ISO 2022** | 11 mars 2021 | Adobe effectuera les mises à jour des zones géographiques ISO 2022 le **10 juin 2022**. Attendez-vous à voir des mises à jour mineures des informations géographiques après cette publication. |
| **Suspension des anciennes tâches planifiées de Report Builder** | 12 avril 2022 | À compter du **20 avril 2022**, Adobe prévoit de suspendre toutes les tâches planifiées de Report Builder qui ont été créées il y a plus de deux ans. Toutes les tâches créées avant le 31 janvier 2020 sont concernées. Aucune tâche, aucun classeur ou aucune donnée n’est supprimé. Toutefois, les tâches identifiées comme datant de plus de deux ans seront suspendues et aucune autre tâche planifiée ne sera envoyée. En savoir plus |
| **Expiration de l’extension de fin de vie de liste autorisée pour les intégrations héritées OAuth/JWT d’Analytics** | 14 janvier 2022 | Le **25 mai 2022**, la liste d’extensions autorisées de fin de vie de [l’API 1.3 d’Analytics, l’API 1.4 de SOAP et Legacy Analytics OAuth/JWT](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) arrivera à expiration. Cette extension visait à offrir aux clients utilisant des identifiants OAuth/JWT [!DNL Adobe Analytics] un délai supplémentaire pour migrer leurs intégrations clientes vers les [identifiants Adobe IMS](https://developer.adobe.com/console). Cette expiration affecte (sans toutefois s’y limiter) les clients d’[!DNL Adobe Analytics Livestream] et d’[!DNL Adobe Campaign] qui n’ont pas terminé leurs migrations IMS requises. Les clients qui utilisent actuellement les identifiants OAuth/JWT herités de [!DNL Analytics] via la liste d’extensions autorisée et qui ne terminent pas leur migration vers les identifiants IMS d’ici le 25 mai 2022 perdront l’accès aux services Adobe. Les clients Livestream peuvent se référer à ces [instructions](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) lors de la migration de leurs applications clientes vers les identifiants IMS. Les clients [!DNL Campaign] peuvent contacter leur équipe de compte Adobe pour effectuer la mise à niveau vers la dernière version de [!DNL Campaign]. |
| **Fin de vie de [!DNL Reports & Analytics]** | 4 janvier 2022 | À compter du **31 décembre 2023**, Adobe prévoit dʼabandonner [!DNL Reports & Analytics] et ses rapports et fonctionnalités associés. [!DNL Reports & Analytics] repose sur des rapports, des visualisations et une technologie sous-jacente qui ne répondent plus aux normes technologiques d’Adobe. La plupart des fonctionnalités de [!DNL Reports & Analytics] sont disponibles dans [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=fr). Depuis la publication d’Analysis Workspace en 2015, les fonctionnalités de [!DNL Reports & Analytics] ont migré vers Analysis Workspace, de telle sorte quʼun seuil de parité en matière de workflow a été atteint. [Cet avis](https://spark.adobe.com/page/6WnF8JK6IRDhf/) décrit le processus de fin de vie. |

{style=&quot;table-layout:auto&quot;}

### AppMeasurement

Pour connaître les dernières mises à jour des versions d’AppMeasurement (version 2.22.4), reportez-vous aux [Notes de mise à jour d’AppMeasurement pour JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=fr).

