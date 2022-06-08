---
title: Dernières notes de mise à jour dʼAnalytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 9a16f3942505028624e5c07568342a9acac898d7
workflow-type: tm+mt
source-wordcount: '821'
ht-degree: 63%

---

# Notes de mise à jour actuelles d’Adobe Analytics (mai 2022)

**Dernière mise à jour**: 8 juin 2022

## Ressources connexes

* [Notes de mise à jour précédentes pour 2022](/help/release-notes/2022.md)
* [Notes de mise à jour de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=fr)
* [Notes de mise à jour de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* Dernières mises à jour des [produits Adobe Experience Cloud](https://business.adobe.com/fr/products/adobe-experience-cloud-products.html)

## Nouvelles fonctionnalités d’Adobe Analytics

| Fonctionnalité | Description | [Date ciblée](releases.md) |
| ----------- | ---------- | ------- |
| Remplir les dimensions et les mesures de cycle de vie via Experience Edge | Les données de cycle de vie mobile envoyées via Experience Edge apparaissent désormais dans les rapports Analytics. Consultez la documentation pour plus d’informations sur les données de cycle de vie collectées via Experience Edge et sur les différences par rapport aux rapports de cycle de vie existants. [En savoir plus - bientôt disponible] | 27 mai 2022 |

{style=&quot;table-layout:auto&quot;}

### Correctifs dans Adobe Analytics

(Correctifs pour plusieurs clients)

S.O.

### Correctifs supplémentaires dans Adobe Analytics

(Correctifs pour les clients individuels)

AN-274429 ; AN-279640 ; AN-280918 ; AN-280945 ; AN-282884 ; AN-283565 ; AN-284785 ; AN-284814 ; AN-284854 ; AN-284989 ; AN-285244 ; AN-285253 ; AN-285432 ; AN-285528 ; AN-285535 ; AN-285710 ; AN-286255 ; AN-286340 ; AN-286434 ; AN-286454 ; AN-286630 ; AN-286716 ; AN-286854 ; AN-286911

### Avis importants pour les administrateurs d’Adobe Analytics

| Remarque | Date d’ajout ou de mise à jour | Description |
| ----------- | ---------- | ---------- |
| Suspension des rapports planifiés dans Reports &amp; Analytics | 8 juin 2022 | Le 21 avril 2022, nous avons annoncé l’abandon de plusieurs fonctionnalités spécifiques aux rapports planifiés en vue de la [fin de vie de Reports &amp; Analytics](https://express.adobe.com/page/6WnF8JK6IRDhf/). Ces fonctionnalités comprenaient la possibilité de planifier de nouveaux rapports ainsi que de nouveaux extractions de données.<p>En réponse aux demandes des clients qui recherchent une extension et pour faciliter la transition à partir de Reports and Analytics, nous avons décidé d’étendre l’accès à ces fonctionnalités jusqu’à ce que **31 janvier 2023**. Veuillez noter que les délais d’expiration des rapports et des extractions de données continueront à être limités à neuf mois ; la remise des rapports et des extractions de données sera suspendue à la fin de cette période, sauf si le planning est réactivé. <p>En résumé, ces fonctionnalités seront abandonnées le 31 janvier 2023, avant que vous ne deviez migrer vos rapports planifiés vers l’un des autres mécanismes disponibles dans Adobe Analytics. Pour toute question ou assistance supplémentaire, contactez l’assistance clientèle Adobe. |
| Suspension des tâches planifiées en Report Builder | 8 juin 2022 | Le 21 avril 2022, nous avons apporté des modifications aux tâches planifiées dans le Report Builder dans le cadre de nos efforts d’optimisation des performances et des diffusions. Ces modifications comprenaient la suppression de la possibilité que des diffusions planifiées &quot;se terminent après x occurrences&quot;. En réponse à plusieurs demandes de clients qui recherchent plus de temps pour explorer et mettre en oeuvre des alternatives, nous avons décidé de restaurer cette option de manière limitée jusqu’à ce que **31 janvier 2023**.<p>Vous pourrez continuer à planifier les tâches de Report Builder horaire et les terminer au maximum après 99 occurrences. Notez que la restauration s’applique uniquement aux tâches horaires ; la &quot;fin après x occurrences&quot; reste indisponible pour tous les autres intervalles de diffusion (quotidiens, hebdomadaires, mensuels et annuels). Cette option sera abandonnée le 31 janvier 2023. Pour plus de questions ou d’assistance, contactez l’assistance clientèle Adobe. |
| **Mise à niveau des services SFTP** | 9 mai 2022 | Nous avons précédemment annoncé qu’Adobe allait procéder à la mise à niveau de ses services SFTP (Secure File Transfer Protocol) en mai 2022, afin d’assurer une sécurité accrue pour le transfert de fichiers. Nous avons reporté cette mise à niveau à **été 2022**. Cette mise à niveau marque la fin de la prise en charge de certaines configurations de clients SFTP. Cela n’affecte que les données envoyées ou récupérées depuis Adobe Analytics via SFTP. Le protocole FTP n’est pas affecté. Afin d’éviter toute perturbation du service, assurez-vous que vos clients SFTP (code, outils, services) sont compatibles avec les modifications détaillées [ici](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=fr). |
| **Mise à jour des méthodes de chiffrement du navigateur prises en charge pour certains clients** | 28 mars 2022 | Adobe propose deux niveaux de sécurité de chiffrement pour répondre aux différents besoins des clients en matière de sécurité de la collecte de données de première main. Le **23 juin 2022**, nous supprimerons la prise en charge de certains algorithmes de chiffrement HTTPS, appelés chiffrements, pour les clients dont le niveau de sécurité est défini sur « Élevé ». Cela signifie que certains systèmes d’exploitation plus anciens ne pourront plus envoyer de données à Analytics, car ils ne prennent pas en charge les méthodes de chiffrement modernes. Les clients utilisant les paramètres de sécurité de chiffrement « standard » par défaut ne seront pas concernés. Tous les clients qui utilisent actuellement le paramètre « Élevé » ont déjà été contactés directement. Une liste détaillée des chiffrements concernés par cette modification est disponible ici. |
| **Mises à jour des zones géographiques ISO 2022** | 11 mars 2021 | Adobe effectuera les mises à jour des zones géographiques ISO 2022 le **10 juin 2022**. Attendez-vous à voir des mises à jour mineures des informations géographiques après cette publication. |
| **Fin de vie de [!DNL Reports & Analytics]** | 4 janvier 2022 | À compter du **31 décembre 2023**, Adobe prévoit dʼabandonner [!DNL Reports & Analytics] et ses rapports et fonctionnalités associés. [!DNL Reports & Analytics] repose sur des rapports, des visualisations et une technologie sous-jacente qui ne répondent plus aux normes technologiques d’Adobe. La plupart des fonctionnalités de [!DNL Reports & Analytics] sont disponibles dans [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=fr). Depuis la publication d’Analysis Workspace en 2015, les fonctionnalités de [!DNL Reports & Analytics] ont migré vers Analysis Workspace, de telle sorte quʼun seuil de parité en matière de workflow a été atteint. [Cet avis](https://spark.adobe.com/page/6WnF8JK6IRDhf/) décrit le processus de fin de vie. |

{style=&quot;table-layout:auto&quot;}

### AppMeasurement

Pour connaître les dernières mises à jour des versions d’AppMeasurement (version 2.22.4), reportez-vous aux [Notes de mise à jour d’AppMeasurement pour JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=fr).

