---
title: Dernières notes de mise à jour dʼAnalytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 7c6ef22322a67e671ac32d2b7be4a182bb3a2df7
workflow-type: tm+mt
source-wordcount: '1011'
ht-degree: 83%

---

# Notes de mise à jour actuelles d’Adobe Analytics (août 2022)

**Dernière mise à jour**: 12 août 2022

## Ressources connexes

* [Notes de mise à jour précédentes pour 2022](/help/release-notes/2022.md)
* [Notes de mise à jour de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=fr)
* [Notes de mise à jour de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* Dernières mises à jour des [produits Adobe Experience Cloud](https://business.adobe.com/fr/products/adobe-experience-cloud-products.html)

## Fonctionnalités nouvelles ou mises à jour dans Adobe Analytics

| Fonctionnalité | Description | [Date ciblée](releases.md) |
| ----------- | ---------- | ------- |
| Aucune nouvelle fonctionnalité ce mois-ci |  |  |

{style=&quot;table-layout:auto&quot;}

## Correctifs dans Adobe Analytics 

* Correction de plusieurs problèmes liés aux flux de données. (AN-297264, AN-297295, AN-297449)

**Correctifs pour les clients individuels** :

AN-280956; AN-285670; AN-288176; AN-289221; AN-289665; AN-289768; AN-294632; AN-294970; AN-295078; AN-295233; AN-295482; AN-295549; AN-295633; AN-295712; AN-295749; AN-295963; AN-295977; AN-296094; AN-296153; AN-296167; AN-296177; AN-296297; AN-296383; AN-296394; AN-296414; AN-296431; AN-296459; AN-296486; AN-296510; AN-296514; AN-296540; AN-296734; AN-296840; AN-296841; AN-296977; AN-296987; AN-297002; AN-297141; AN-297267; AN-297396;

## Avis importants pour les administrateurs d’Adobe Analytics

| Remarque | Date d’ajout  ou de mise à jour | Description |
| ----------- | ---------- | ---------- |
| **Mise à niveau des services SFTP** | 12 août 2022 | Nous avons précédemment annoncé qu’Adobe allait procéder à la mise à niveau de ses services SFTP (Secure File Transfer Protocol) en mai 2022, afin d’assurer une sécurité accrue pour le transfert de fichiers. Nous avons reporté cette mise à niveau à **7 septembre 2022**. Cette mise à niveau marque la fin de la prise en charge de certaines configurations de clients SFTP. Cela n’affecte que les données envoyées ou récupérées depuis Adobe Analytics via SFTP. Le protocole FTP n’est pas affecté. Afin d’éviter toute perturbation du service, assurez-vous que vos clients SFTP (code, outils, services) sont compatibles avec les modifications détaillées [ici](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=fr). |
| **Mettre à jour la nouvelle base de données des opérateurs NetAcuity** | 11 juillet 2022 | **À compter d’octobre 2022**, les informations relatives à l’opérateur stockées dans la variable `carrier` dans Adobe Analytics Data Warehouse et les flux de données Analytics changeront. Historiquement, le format de données de cette colonne était `<domain>:<ISP>`. Adobe a conservé une table de recherche interne pour les mapper. `<domain>:<ISP>` valeurs en noms d’opérateurs à des fins de création de rapports dans les outils de reporting d’Adobe Analytics (Analysis Workspace, Reports &amp; Analytics, API de création de rapports, Data Warehouse, LiveStream, etc.). Le fichier de recherche (`carrier.tsv`) est également fourni avec les flux de données afin que vous puissiez utiliser les mêmes mappages.<p>Cette mise à jour améliore nos mappages des opérateurs en utilisant une base de données des opérateurs plus précise fournie par NetAcuity. Le format des données de la colonne des opérateurs dans les flux de données va changer à l’avenir. Au lieu de `<domain>:<ISP>`, il contiendra un nom d’opérateur. Adobe continuera à utiliser la table de recherche afin de maintenir une continuité maximale avec les rapports antérieurs. Les outils de création de rapports pour lesquels les recherches sont appliquées par Adobe (Analysis Workspace, Reports &amp; Analytics, API de création de rapports, Data Warehouse, LiveStream, etc.) bénéficieront de mappages plus précis. Certains mappages, en particulier pour les domaines internationaux et les FAI, changeront plus que d’autres lorsque nous adopterons la nouvelle base de données. Le fichier de recherche de l’opérateur de flux de données (`carrier.tsv`) conserve les anciens mappages et ajoute les nouveaux mappages.<p>Actuellement, le connecteur source Analytics ne mappe pas le champ de l’opérateur, de sorte que les rapports de l’opérateur ne sont pour le moment pas disponibles dans AEP, CJA, etc. Par conséquent, l’utilisation de la nouvelle base de données des opérateurs n’aura aucune incidence dans AEP sur les données fournies par le connecteur source Analytics. |
| **Amélioration du mappage IP/géolocalisation** | 11 juillet 2022 | Digital Element, notre fournisseur pour les recherches IP, effectue une mise à niveau vers un nouveau jeu de données amélioré (NetAcuity Pulse) pour le mappage IP/géolocalisation. Adobe Analytics adoptera ce nouveau jeu de données durant le mois d’**octobre 2022**. La nouvelle base de données sera plus précise que les versions précédentes. Certains mappages IP/géolocalisation seront modifiés/améliorés lors de l’adoption de la nouvelle base de données.<p>Tous les outils Adobe Analytics (Analysis Workspace, Reports &amp; Analytics, API de création de rapports, Data Warehouse, LiveStream, flux de données, etc.) tireront automatiquement parti des nouveaux mappages améliorés. Le format des données dans les flux de données ne sera pas modifié. Les données CJA fournies par le biais du connecteur source Analytics tireront également automatiquement parti des nouveaux mappages. |
| **Suspension des rapports planifiés dans Reports &amp; Analytics** | 8 juin 2022 | Le 21 avril 2022, nous avons annoncé l’abandon de plusieurs fonctionnalités spécifiques aux rapports planifiés en prévision de la fin de vie de Reports &amp; Analytics annoncée précédemment. Ces fonctionnalités comprenaient la possibilité de planifier de nouveaux rapports ainsi que de nouvelles extractions de données.<p>En réponse aux demandes des clients qui souhaitaient une prolongation et pour faciliter la transition depuis Reports and Analytics, nous avons décidé de prolonger l’accès à ces fonctionnalités jusqu’au **31 janvier 2023**. Veuillez noter que les fenêtres d’expiration pour les rapports et les extractions de données continueront d’être limitées à neuf mois ; la diffusion des rapports et des extractions de données s’interrompra à la fin de cette période, sauf si le planning est réactivé.<p>Pour réitérer, ces fonctionnalités seront abandonnées le 31 janvier 2023. Avant cette date, vous devez migrer vos rapports planifiés vers l’un des autres mécanismes disponibles dans Adobe Analytics. Pour toute question ou assistance supplémentaire, contactez l’Assistance clientèle d’Adobe. [En savoir plus](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **Suspension des tâches planifiées dans Report Builder** | 8 juin 2022 | Le 21 avril 2022, nous avons apporté des modifications aux tâches planifiées dans Report Builder dans le cadre de nos efforts d’optimisation des performances et des diffusions. Ces modifications comprenaient la suppression de la possibilité de faire en sorte que les diffusions planifiées prennent « fin après x occurrences ». En réponse à plusieurs demandes de clients souhaitant disposer de plus de temps pour explorer et implémenter des alternatives, nous avons décidé de restaurer cette option de manière limitée jusqu’au **31 janvier 2023**.<p>Vous pouvez continuer à planifier des tâches horaires de Report Builder et faire en sorte qu’elles se terminent après un maximum de 99 occurrences. Veuillez noter que la restauration ne s’applique qu’aux tâches horaires ; l’option « fin après x occurrences » restera indisponible pour tous les autres intervalles de diffusion (quotidien, hebdomadaire, mensuel et annuel). Veuillez noter que cette option sera abandonnée le 31 janvier 2023. Pour toute question ou assistance, contactez l’Assistance clientèle d’Adobe. [En savoir plus](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| **Fin de vie de [!DNL Reports & Analytics]** | 4 janvier 2022 | À compter du **31 décembre 2023**, Adobe prévoit dʼabandonner [!DNL Reports & Analytics] et ses rapports et fonctionnalités associés. [!DNL Reports & Analytics] repose sur des rapports, des visualisations et une technologie sous-jacente qui ne répondent plus aux normes technologiques d’Adobe. La plupart des fonctionnalités de [!DNL Reports & Analytics] sont disponibles dans [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=fr). Depuis la publication d’Analysis Workspace en 2015, les fonctionnalités de [!DNL Reports & Analytics] ont migré vers Analysis Workspace, de telle sorte quʼun seuil de parité en matière de workflow a été atteint. [Cet avis](https://spark.adobe.com/page/6WnF8JK6IRDhf/) décrit le processus de fin de vie. |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

Pour connaître les dernières mises à jour des versions d’AppMeasurement (version 2.22.4), reportez-vous aux [Notes de mise à jour d’AppMeasurement pour JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=fr).

