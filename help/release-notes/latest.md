---
title: Dernières notes de mise à jour dʼAnalytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: c14fc5f07d74ed3ab85e68e567f37712e4a92883
workflow-type: tm+mt
source-wordcount: '1104'
ht-degree: 96%

---

# Notes de mise à jour actuelles d’Adobe Analytics (juin 2022)

**Dernière mise à jour**: 13 juillet 2022

## Ressources connexes

* [Notes de mise à jour précédentes pour 2022](/help/release-notes/2022.md)
* [Notes de mise à jour de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=fr)
* [Notes de mise à jour de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* Dernières mises à jour des [produits Adobe Experience Cloud](https://business.adobe.com/fr/products/adobe-experience-cloud-products.html)

## Nouvelles fonctionnalités d’Adobe Analytics

| Fonctionnalité | Description | [Date ciblée](releases.md) |
| ----------- | ---------- | ------- |
| **Nouvelle interface utilisateur pour la visualisation de flux** | Fournit des fonctionnalités supplémentaires à notre visualisation de flux pour la rendre plus puissante et plus performante. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/flow/create-flow.html?lang=fr) | Le déploiement commence le 15 juin 2022 ; Google Analytics d’ici le 27 ou le 28 juin 2022. |
| **Partager des annotations dans les cartes de performance mobiles** | Vous pouvez afficher les annotations créées dans Workspace dans les cartes de performance mobiles. Cela vous permet de partager des nuances de données contextuelles et des insights sur votre organisation et vos campagnes directement dans les projets de cartes de performance mobiles, consultables dans l’application mobile des tableaux de bord Analytics. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/annotations/mobile-annotations.html?lang=fr) | 15 juin 2022 |
| **Prise en charge de la version de syntaxe de produit des variables de marchandisage avec Edge Collection** | Vous pouvez désormais définir des variables de marchandisage à l’aide de l’équivalent de la syntaxe de produit en définissant les champs XDM correspondants. Consultez la rubrique [variable produits](../implement/vars/page-vars/products.md) pour en savoir plus sur la syntaxe du SDK Web avec la variable `products`, et le [mappage des variables Analytics dans Adobe Experience Edge](../implement/aep-edge/variable-mapping.md) pour obtenir la liste complète des variables disponibles. | 15 juin 2022 |
| **Remplir les dimensions et les mesures de cycle de vie via Experience Edge** | Les données de cycle de vie mobile envoyées via Experience Edge apparaissent désormais dans les rapports Analytics. Consultez la documentation pour savoir quels champs XDM correspondent aux rapports de cycle de vie mobile existants. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=fr) | 27 mai 2022 |
| **Règles de traitement Mobile Services disponibles dans les règles de traitement Analytics** | La date de fin de vie d’Adobe Mobile Services est fixée au 31 décembre 2022. Les règles de traitement existantes créées ou générées par Adobe Mobile Services migreront automatiquement vers les règles de traitement Adobe Analytics, où vous pourrez les modifier et les gérer. Elles peuvent être consultées, mais ne peuvent plus être modifiées dans Mobile Services jusqu’à la fin de vie du produit. Pour toute question ou assistance supplémentaire, contactez l’Assistance clientèle d’Adobe. [En savoir plus](https://experienceleague.adobe.com/docs/mobile-services/using/eol.html?lang=fr) | 15 juin 2022 |
| **Ensembles de classifications - Phase 1** | Ce lancement progressif d’une nouvelle expérience client en matière de classifications améliore considérablement la visibilité des données de classification appartenant aux clients. Consultez la section [Ensembles de classifications](../components/classifications/sets/overview.md) pour plus d’informations. | Les tests limités débutent le 15 juin 2022 ; la disponibilité générale est prévue pour début 2023. |

{style=&quot;table-layout:auto&quot;}

### Correctifs dans Adobe Analytics 

AN-251686 ; AN-283542 ; AN-286572 ; AN-286945 ; AN-286784 ; AN-286944 ; AN-287012 ; AN-287319 ; AN-287333 ; AN-287348 ; AN-287429 ; AN-288238 ; AN-288281 ; AN-288660 ; AN-288769 ; AN-288798 ; AN-288871 ; AN-288872 ; AN-288941 ; AN-288951 ; AN-288952 ; AN-288956 ; AN-289062 ; AN-289340 ; AN-289346 ; AN-289488 ; AN-289562 ; AN-289580 ; AN-289861 ; AN-289892 ;

### Avis importants pour les administrateurs d’Adobe Analytics

| Remarque | Date d’ajout  ou de mise à jour | Description |
| ----------- | ---------- | ---------- |
| **Nouveau domaine pour les emails générés par le système** | 13 juillet 2022 | Activé **18 mai 2022**, Adobe a modifié le domaine de l’expéditeur pour les emails provenant des projets Workspace, des alertes et des alertes de dépassement, de `noreply@omniture.com` to `noreply@adobe.com`. Ajoutez ce nouvel email à votre liste autorisée si votre entreprise n’autorise que des expéditeurs spécifiques. |
| **Suspension des rapports planifiés dans Reports &amp; Analytics** | 8 juin 2022 | Le 21 avril 2022, nous avons annoncé l’abandon de plusieurs fonctionnalités spécifiques aux rapports planifiés en prévision de la fin de vie de Reports &amp; Analytics annoncée précédemment. Ces fonctionnalités comprenaient la possibilité de planifier de nouveaux rapports ainsi que de nouvelles extractions de données.<p>En réponse aux demandes des clients qui souhaitaient une prolongation et pour faciliter la transition depuis Reports and Analytics, nous avons décidé de prolonger l’accès à ces fonctionnalités jusqu’au **31 janvier 2023**. Veuillez noter que les fenêtres d’expiration pour les rapports et les extractions de données continueront d’être limitées à neuf mois ; la diffusion des rapports et des extractions de données s’interrompra à la fin de cette période, sauf si le planning est réactivé.<p>Pour réitérer, ces fonctionnalités seront abandonnées le 31 janvier 2023. Avant cette date, vous devez migrer vos rapports planifiés vers l’un des autres mécanismes disponibles dans Adobe Analytics. Pour toute question ou assistance supplémentaire, contactez l’Assistance clientèle d’Adobe. [En savoir plus](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **Suspension des tâches planifiées dans Report Builder** | 8 juin 2022 | Le 21 avril 2022, nous avons apporté des modifications aux tâches planifiées dans Report Builder dans le cadre de nos efforts d’optimisation des performances et des diffusions. Ces modifications comprenaient la suppression de la possibilité de faire en sorte que les diffusions planifiées prennent « fin après x occurrences ». En réponse à plusieurs demandes de clients souhaitant disposer de plus de temps pour explorer et implémenter des alternatives, nous avons décidé de restaurer cette option de manière limitée jusqu’au **31 janvier 2023**.<p>Vous pouvez continuer à planifier des tâches horaires de Report Builder et faire en sorte qu’elles se terminent après un maximum de 99 occurrences. Veuillez noter que la restauration ne s’applique qu’aux tâches horaires ; l’option « fin après x occurrences » restera indisponible pour tous les autres intervalles de diffusion (quotidien, hebdomadaire, mensuel et annuel). Veuillez noter que cette option sera abandonnée le 31 janvier 2023. Pour toute question ou assistance, contactez l’Assistance clientèle d’Adobe. [En savoir plus](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| **Mise à niveau des services SFTP** | 9 mai 2022 | Nous avons précédemment annoncé qu’Adobe allait procéder à la mise à niveau de ses services SFTP (Secure File Transfer Protocol) en mai 2022, afin d’assurer une sécurité accrue pour le transfert de fichiers. Cette mise à niveau a été reportée à **l’été 2022**. Cette mise à niveau marque la fin de la prise en charge de certaines configurations de clients SFTP. Cela n’affecte que les données envoyées ou récupérées depuis Adobe Analytics via SFTP. Le protocole FTP n’est pas affecté. Afin d’éviter toute perturbation du service, assurez-vous que vos clients SFTP (code, outils, services) sont compatibles avec les modifications détaillées [ici](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=fr). |
| **Mise à jour des méthodes de chiffrement du navigateur prises en charge pour certains clients** | 28 mars 2022 | Adobe propose deux niveaux de sécurité de chiffrement pour répondre aux différents besoins des clients en matière de sécurité de la collecte de données de première main. Le **23 juin 2022**, nous supprimerons la prise en charge de certains algorithmes de chiffrement HTTPS, appelés chiffrements, pour les clients dont le niveau de sécurité est défini sur « Élevé ». Cela signifie que certains systèmes d’exploitation plus anciens ne pourront plus envoyer de données à Analytics, car ils ne prennent pas en charge les méthodes de chiffrement modernes. Les clients utilisant les paramètres de sécurité de chiffrement « standard » par défaut ne seront pas concernés. Tous les clients qui utilisent actuellement le paramètre « Élevé » ont déjà été contactés directement. Une liste détaillée des chiffrements concernés par ce changement |
| **Mises à jour des zones géographiques ISO 2022** | 11 mars 2021 | Adobe a effectué les mises à jour des zones géographiques ISO 2022 le **10 juin 2022**. Attendez-vous à voir des mises à jour mineures des informations géographiques après cette publication. |
| **Fin de vie de [!DNL Reports & Analytics]** | 4 janvier 2022 | À compter du **31 décembre 2023**, Adobe prévoit dʼabandonner [!DNL Reports & Analytics] et ses rapports et fonctionnalités associés. [!DNL Reports & Analytics] repose sur des rapports, des visualisations et une technologie sous-jacente qui ne répondent plus aux normes technologiques d’Adobe. La plupart des fonctionnalités de [!DNL Reports & Analytics] sont disponibles dans [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=fr). Depuis la publication d’Analysis Workspace en 2015, les fonctionnalités de [!DNL Reports & Analytics] ont migré vers Analysis Workspace, de telle sorte quʼun seuil de parité en matière de workflow a été atteint. [Cet avis](https://spark.adobe.com/page/6WnF8JK6IRDhf/) décrit le processus de fin de vie. |

{style=&quot;table-layout:auto&quot;}

### AppMeasurement

Pour connaître les dernières mises à jour des versions d’AppMeasurement (version 2.22.4), reportez-vous aux [Notes de mise à jour d’AppMeasurement pour JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=fr).

