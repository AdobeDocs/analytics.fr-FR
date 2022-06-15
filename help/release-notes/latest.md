---
title: Dernières notes de mise à jour dʼAnalytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 29f152bf1724c566da69598f35929ee3b502b7f9
workflow-type: tm+mt
source-wordcount: '1077'
ht-degree: 46%

---

# Notes de mise à jour actuelles d’Adobe Analytics (juin 2022)

>[!NOTE]
>
>Cette page contient des informations préliminaires. Elles peuvent être modifiées à tout moment.

**Dernière mise à jour**: 15 juin 2022

## Ressources connexes

* [Notes de mise à jour précédentes pour 2022](/help/release-notes/2022.md)
* [Notes de mise à jour de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=fr)
* [Notes de mise à jour de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* Dernières mises à jour des [produits Adobe Experience Cloud](https://business.adobe.com/fr/products/adobe-experience-cloud-products.html)

## Nouvelles fonctionnalités d’Adobe Analytics

| Fonctionnalité | Description | [Date ciblée](releases.md) |
| ----------- | ---------- | ------- |
| **Nouvelle interface utilisateur de visualisation de flux** | Fournit des fonctionnalités supplémentaires à notre visualisation Flux pour la rendre plus puissante et plus performante. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/flow/create-flow.html?lang=en) | 15 juin 2022 |
| **Partage des annotations dans les Fiches d’évaluation mobiles** | Vous pouvez afficher les annotations créées dans Workspace dans les Fiches d’évaluation mobiles. Cela vous permet de partager des nuances de données contextuelles et des informations sur votre organisation et vos campagnes directement dans les projets de Fiche d’évaluation mobile, visibles dans l’application mobile des tableaux de bord Analytics. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/annotations/mobile-annotations.html?lang=en) | 15 juin 2022 |
| **Prise en charge de la version de syntaxe de produit des variables de marchandisage avec la collection Edge** | Vous pouvez désormais définir des variables de marchandisage à l’aide de l’équivalent de la syntaxe du produit en définissant les champs XDM appropriés. En savoir plus sur la syntaxe des produits pour les variables de marchandisage [here](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/merchandising-evars.html?lang=fr). Voir les mappages pour la syntaxe du produit [here](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=en#aep-edge). | 15 juin 2022 |
| **Remplir les dimensions et les mesures de cycle de vie via Experience Edge** | Les données de cycle de vie mobile envoyées via Experience Edge apparaissent désormais dans les rapports Analytics. Consultez la documentation pour plus d’informations sur les champs XDM associés aux rapports de cycle de vie mobile existants. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) | 27 mai 2022 |
| **Règles de traitement de Mobile Service disponibles dans les règles de traitement Analytics** | La date de fin de vie d’Adobe Mobile Services est le 31 décembre 2022. Les règles de traitement existantes créées ou générées par Adobe Mobile Services migrent automatiquement vers les règles de traitement Adobe Analytics, où vous pouvez les modifier et les gérer. Ils peuvent être gérés, mais ne peuvent plus être modifiés dans Mobile Services tant que le produit n’a pas expiré. Pour toute question ou assistance supplémentaire, contactez l’assistance clientèle Adobe. [En savoir plus](https://experienceleague.adobe.com/docs/mobile-services/using/eol.html?lang=en) | 15 juin 2022 |
| **Nouvelle expérience des classifications - Phase 1** | Cette version progressive d’une nouvelle expérience utilisateur de jeu de classifications améliore considérablement la visibilité des données de classification détenues par le client. [Disponibilité générale](/help/release-notes/releases.md) est estimé au début de 2023. | Les tests limités démarrent le 15 juin 2022 |

{style=&quot;table-layout:auto&quot;}

### Correctifs dans Adobe Analytics

AN-251686 ; AN-283542 ; AN-286572 ; AN-286945 ; AN-286784 ; AN-286944 ; AN-287012 ; AN-287319 ; AN-287333 ; AN-287348 ; AN-287429 ; AN-288238 ; AN-288281 ; AN-288660 ; AN-288769 ; AN-288798 ; AN-288871 ; AN-288872 ; AN-288941 ; AN-288951 ; AN-288952 ; AN-288956 ; AN-289062 ; AN-289340 ; AN-289346 ; AN-289488 ; AN-289562 ; AN-289580 ; AN-289861 ; AN-289892;

### Avis importants pour les administrateurs d’Adobe Analytics

| Remarque | Date d’ajout ou de mise à jour | Description |
| ----------- | ---------- | ---------- |
| **Suspension des rapports planifiés dans Reports &amp; Analytics** | 8 juin 2022 | Le 21 avril 2022, nous avons annoncé l’abandon de plusieurs fonctionnalités spécifiques aux rapports planifiés en vue de la fin de vie précédemment annoncée de Reports &amp; Analytics. Ces fonctionnalités comprenaient la possibilité de planifier de nouveaux rapports ainsi que de nouveaux extractions de données.<p>En réponse aux demandes des clients qui recherchent une extension et pour faciliter la transition à partir de Reports and Analytics, nous avons décidé d’étendre l’accès à ces fonctionnalités jusqu’à ce que **31 janvier 2023**. Veuillez noter que les délais d’expiration des rapports et des extractions de données continueront à être limités à neuf mois ; la remise des rapports et des extractions de données sera suspendue à la fin de cette période, sauf si le planning est réactivé.<p>En résumé, ces fonctionnalités seront abandonnées le 31 janvier 2023. Avant cette date, vous devez migrer les rapports planifiés vers l’un des autres mécanismes disponibles dans Adobe Analytics. Pour toute question ou assistance supplémentaire, contactez l’assistance clientèle Adobe. [En savoir plus](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **Suspension des tâches planifiées en Report Builder** | 8 juin 2022 | Le 21 avril 2022, nous avons apporté des modifications aux tâches planifiées dans le Report Builder dans le cadre de nos efforts d’optimisation des performances et des diffusions. Ces modifications comprenaient la suppression de la possibilité que des diffusions planifiées &quot;se terminent après x occurrences&quot;. En réponse à plusieurs demandes de clients qui recherchent plus de temps pour explorer et mettre en oeuvre des alternatives, nous avons décidé de restaurer cette option de manière limitée jusqu’à ce que **31 janvier 2023**.<p>Vous pouvez continuer à planifier les tâches par Report Builder horaire et les terminer après un maximum de 99 occurrences. Notez que la restauration s’applique uniquement aux tâches horaires ; la &quot;fin après x occurrences&quot; reste indisponible pour tous les autres intervalles de diffusion (quotidiens, hebdomadaires, mensuels et annuels). Cette option sera abandonnée le 31 janvier 2023. Pour plus de questions ou d’assistance, contactez l’assistance clientèle Adobe. [En savoir plus](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| **Mise à niveau des services SFTP** | 9 mai 2022 | Nous avons précédemment annoncé qu’Adobe allait procéder à la mise à niveau de ses services SFTP (Secure File Transfer Protocol) en mai 2022, afin d’assurer une sécurité accrue pour le transfert de fichiers. Nous avons reporté cette mise à niveau à **été 2022**. Cette mise à niveau marque la fin de la prise en charge de certaines configurations de clients SFTP. Cela n’affecte que les données envoyées ou récupérées depuis Adobe Analytics via SFTP. Le protocole FTP n’est pas affecté. Afin d’éviter toute perturbation du service, assurez-vous que vos clients SFTP (code, outils, services) sont compatibles avec les modifications détaillées [ici](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=fr). |
| **Mise à jour des méthodes de chiffrement du navigateur prises en charge pour certains clients** | 28 mars 2022 | Adobe propose deux niveaux de sécurité de chiffrement pour répondre aux différents besoins des clients en matière de sécurité de la collecte de données de première main. Le **23 juin 2022**, nous supprimerons la prise en charge de certains algorithmes de chiffrement HTTPS, appelés chiffrements, pour les clients dont le niveau de sécurité est défini sur « Élevé ». Cela signifie que certains systèmes d’exploitation plus anciens ne pourront plus envoyer de données à Analytics, car ils ne prennent pas en charge les méthodes de chiffrement modernes. Les clients utilisant les paramètres de sécurité de chiffrement « standard » par défaut ne seront pas concernés. Tous les clients qui utilisent actuellement le paramètre « Élevé » ont déjà été contactés directement. Liste détaillée des chiffrements concernés par cette opération |
| **Mises à jour des zones géographiques ISO 2022** | 11 mars 2021 | Adobe effectué des mises à jour de la région ISO 2022 sur **10 juin 2022**. Attendez-vous à voir des mises à jour mineures des informations géographiques après cette publication. |
| **Fin de vie de [!DNL Reports & Analytics]** | 4 janvier 2022 | À compter du **31 décembre 2023**, Adobe prévoit dʼabandonner [!DNL Reports & Analytics] et ses rapports et fonctionnalités associés. [!DNL Reports & Analytics] repose sur des rapports, des visualisations et une technologie sous-jacente qui ne répondent plus aux normes technologiques d’Adobe. La plupart des fonctionnalités de [!DNL Reports & Analytics] sont disponibles dans [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=fr). Depuis la publication d’Analysis Workspace en 2015, les fonctionnalités de [!DNL Reports & Analytics] ont migré vers Analysis Workspace, de telle sorte quʼun seuil de parité en matière de workflow a été atteint. [Cet avis](https://spark.adobe.com/page/6WnF8JK6IRDhf/) décrit le processus de fin de vie. |

{style=&quot;table-layout:auto&quot;}

### AppMeasurement

Pour connaître les dernières mises à jour des versions d’AppMeasurement (version 2.22.4), reportez-vous aux [Notes de mise à jour d’AppMeasurement pour JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=fr).

