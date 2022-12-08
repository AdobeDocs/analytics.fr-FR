---
title: Dernières notes de mise à jour dʼAnalytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: d5d4d1c9274bba8c3a40ee8fe86da311c1d1220b
workflow-type: tm+mt
source-wordcount: '1459'
ht-degree: 96%

---

# Notes de mise à jour actuelles d’Adobe Analytics (octobre/novembre 2022)

**Dernière mise à jour**: 18 novembre 2022

Les mises à jour dʼAdobe Analytics suivent un [modèle de diffusion continue](releases.md), ce qui permet un déploiement plus flexible et progressif des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités nouvelles ou mises à jour dans Adobe Analytics

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| Visualisation du **[!UICONTROL résumé des mesures clés]** | La visualisation du [!UICONTROL résumé des mesures clés] vous permet de visualiser le niveau de tendance d’une mesure importante au cours d’une période unique. Elle vous permet également de comparer les performances des mesures sur deux périodes. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/key-metric.html) | 5 octobre 2022 | 19 octobre 2023 |
| **Variables à plusieurs valeurs non sensibles à la casse** | Pour les variables à plusieurs valeurs non sensibles à la casse, les valeurs stockées dans `mvvar1 - mvvar3` et `post_mvvar1 - post_mvvar3` dans les flux de données ne seront plus automatiquement mises en minuscules. Au lieu de cela, les flux de données (et les données transmises par le biais du connecteur source Analytics à Adobe Experience Platform et CJA) refléteront le cas d’origine qui a été transmis à partir de la page. | S.O. | 24 octobre 2022 |

{style=&quot;table-layout:auto&quot;}

## Correctifs dans Adobe Analytics

* Correction d’un problème en raison duquel les versions récentes de macOS étaient incorrectement nommées « Macintosh ». Avec ce correctif, la dimension du système d’exploitation commencera à utiliser la numérotation de version de « macOS » à partir de macOS 11. (AN-301834)
* Correction d’un problème lié à la période des « dates fixes » dans Report Builder. (AN-303684)
* Correction de problèmes en raison desquels l’interface utilisateur des flux de données ne se chargeait pas. (AN-303803, AN-303784)

### Autres correctifs

AN-295574 ; AN-296354 ; AN-297143 ; AN-299501 ; AN-301755 ; AN-302054 ; AN-302304 ; AN-302631 ; AN-302811 ; AN-303090 ; AN-303372 ; AN- ; AN-303428 ; AN-303429 ; AN-303432 ; AN-303434 ; AN-303437 ; AN-303438 ; AN-303519 ; AN-303610 ; AN-303656 ; AN-303659 ; AN-303663 ; AN-303664 ; AN-303818 ; AN-303823 ; AN-303837 ; AN-304036 ; AN-304195 ; AN-304321 ; AN-304325 ; AN-304339 ; AN-304356 ; AN-304435 ; AN-304457 ; AN-304509 ; AN-304519 ; AN-304534

## Avis importants pour les administrateurs d’Adobe Analytics

| Remarque | Date d’ajout ou de mise à jour | Description |
| ----------- | ---------- | ---------- |
| **Mise à jour des directives pour les notifications de pic de trafic** | 18 novembre 2022 | Les anciennes instructions étaient strictement basées sur les volumes d’accès. Le [nouvelles directives](https://experienceleague.adobe.com/docs/analytics/admin/traffic-management/traffic-lead-time.html?lang=en) sont basées sur une combinaison de la taille de la suite de rapports et de l’augmentation du pourcentage. |
| **Mise à jour des recherches d’appareils en raison des indications du client Google** | 14 octobre 2022 | L’utilisation d’indications du client dans la recherche du périphérique, initialement prévue pour le 26 octobre 2022, a été reportée à **janvier 2023**. <p> <p>Depuis octobre 2022, il est possible de collecter les indications du client avec le SDK Web ou les bibliothèques AppMeasurement pour JavaScript. Mais les indications du client ne seront pas intégrées à la recherche du périphérique avant janvier 2023. À partir de cette date, Adobe commencera à utiliser les indications du client en plus de la chaîne Agent-utilisateur lors de la dérivation de certaines informations sur les périphériques pour les accès provenant des navigateurs Chromium, tels que Google Chrome et Microsoft Edge. Cette mesure fait suite au projet de Google qui consiste à réduire progressivement les informations présentées à partir de la chaîne Agent-utilisateur à la place des données transmises par les indications du client. <p> <p>Dans le cadre de cette modification, Adobe utilisera Device Atlas pour toutes les recherches de périphériques liées à la chaîne Agent-utilisateur. [En savoir plus](/help/technotes/client-hints.md) |
| **Page de destination par défaut** | 29 septembre 2022 | La [nouvelle page de destination](/help/analyze/landing.md) qui a été introduite en début d’année deviendra l’expérience par défaut pour tous les utilisateurs en **janvier 2023**. La page actuelle deviendra obsolète et tout le monde devra utiliser la nouvelle expérience. |
| Conditions d’exécution automatique de la **[!UICONTROL détection des anomalies]** | 29 septembre 2022 | Aujourd’hui, la [!UICONTROL détection des anomalies] s’exécute automatiquement sur toutes les colonnes des tableaux à structure libre de série temporelle. Afin de garantir que les données sont disponibles pour l’analyse et que les projets se chargent plus rapidement, Adobe modifie la manière dont la détection des anomalies s’exécute automatiquement. À compter du **26 octobre 2022**, la [!UICONTROL détection des anomalies] s’exécutera automatiquement uniquement sur la première colonne de mesures d’un tableau. Si nécessaire, vous pouvez configurer les paramètres des colonnes pour exécuter la détection des anomalies sur d’autres colonnes. |
| **Mettre à jour la nouvelle base de données des opérateurs NetAcuity** | 26 septembre 2022 | Cette mise à jour, initialement prévue pour le 5 octobre 2022, a été reportée à **Janvier 2023**. Les informations relatives à l’opérateur stockées dans le champ `carrier` dans Adobe Analytics Data Warehouse et les flux de données d’Analytics changeront. Historiquement, le format de données de cette colonne était `<domain>:<ISP>`. Adobe a conservé une table de recherche interne pour mapper ces valeurs `<domain>:<ISP>` sur les noms d’opérateurs à des fins de création de rapports dans les outils de création de rapports d’Adobe Analytics (Analysis Workspace, Reports &amp; Analytics, API de création de rapports, Data Warehouse, LiveStream, etc.). Le fichier de recherche (`carrier.tsv`) est également fourni avec les flux de données afin que les clients des flux de données puissent utiliser les mêmes mappages.<p>Cette mise à jour améliore nos mappages des opérateurs en utilisant une base de données des opérateurs plus précise fournie par NetAcuity. Le format des données de la colonne des opérateurs dans les flux de données va changer à partir de maintenant. Au lieu de `<domain>:<ISP>`, il contiendra un nom d’opérateur. Adobe continuera à utiliser la table de recherche afin de maintenir une continuité maximale avec les rapports antérieurs. Les outils de création de rapports pour lesquels les recherches sont appliquées par Adobe (Analysis Workspace, Reports &amp; Analytics, API de création de rapports, Data Warehouse, LiveStream, etc.) bénéficieront de mappages plus précis. Certains mappages, en particulier pour les domaines internationaux et les FAI, changeront plus que d’autres lorsqu’Adobe adoptera la nouvelle base de données. Le fichier de recherche de l’opérateur des flux de données (`carrier.tsv`) conserve les anciens mappages et ajoute les nouveaux mappages.<p>Actuellement, le connecteur source Analytics ne mappe pas le champ de l’opérateur, de sorte que les rapports de l’opérateur ne sont pour le moment pas disponibles dans Experience Platform, CJA, etc. Par conséquent, l’utilisation de la nouvelle base de données des opérateurs n’aura aucune incidence dans Experience Platform sur les données fournies par le connecteur source Analytics. |
| **Amélioration du mappage IP/géolocalisation** | 26 septembre 2022 | Digital Element, notre fournisseur pour les recherches IP, effectue une mise à niveau vers un nouveau jeu de données amélioré (NetAcuity Pulse) pour le mappage IP/géolocalisation. Prévu à l’origine pour octobre 2022, Adobe Analytics adoptera ce nouveau jeu de données en **Janvier 2023**. La nouvelle base de données sera plus précise que les versions précédentes. Certains mappages IP/géolocalisation seront modifiés/améliorés lors de l’adoption de la nouvelle base de données.<p>Tous les outils Adobe Analytics (Analysis Workspace, Reports &amp; Analytics, API de création de rapports, Data Warehouse, LiveStream, flux de données, etc.) tireront automatiquement parti des nouveaux mappages améliorés. Le format des données dans les flux de données ne sera pas modifié. Les données CJA fournies par le biais du connecteur source Analytics tireront également automatiquement parti des nouveaux mappages. |
| **Suspension des rapports planifiés dans Reports &amp; Analytics** | 8 juin 2022 | Le 21 avril 2022, Adobe a annoncé l’abandon de plusieurs fonctionnalités spécifiques aux rapports planifiés en prévision de la fin de vie de Reports &amp; Analytics annoncée précédemment. Ces fonctionnalités comprenaient la possibilité de planifier de nouveaux rapports ainsi que de nouvelles extractions de données.<p>En réponse aux demandes des clients qui souhaitaient une prolongation et pour faciliter la transition depuis Reports &amp; Analytics, Adobe a décidé de prolonger l’accès à ces fonctionnalités jusqu’au **31 janvier 2023**. Veuillez noter que les fenêtres d’expiration pour les rapports et les extractions de données continueront d’être limitées à neuf mois ; la diffusion des rapports et des extractions de données s’interrompra à la fin de cette période, sauf si le planning est réactivé.<p>Pour réitérer, ces fonctionnalités seront abandonnées le 31 janvier 2023. Avant cette date, vous devez migrer vos rapports planifiés vers l’un des autres mécanismes disponibles dans Adobe Analytics. Pour toute question ou assistance supplémentaire, contactez l’Assistance clientèle d’Adobe. [En savoir plus](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **Suspension des tâches planifiées dans Report Builder** | 8 juin 2022 | Le 21 avril 2022, Adobe a apporté des modifications aux tâches planifiées dans Report Builder dans le cadre de nos efforts d’optimisation des performances et des diffusions. Ces modifications ne permettaient plus que les diffusions planifiées se terminent « après x occurrences ». En réponse à plusieurs demandes de clients souhaitant disposer de plus de temps pour explorer et implémenter des alternatives, Adobe a décidé de restaurer cette option de manière limitée jusqu’au **31 janvier 2023**.<p>Vous pouvez continuer à planifier des tâches horaires de Report Builder et faire en sorte qu’elles se terminent après un maximum de 99 occurrences. Veuillez noter que la restauration ne s’applique qu’aux tâches horaires ; l’option « se terminent après x occurrences » restera indisponible pour tous les autres intervalles de diffusion (quotidien, hebdomadaire, mensuel et annuel). Veuillez noter que cette option sera abandonnée le 31 janvier 2023. Pour toute question ou assistance, contactez l’Assistance clientèle d’Adobe. [En savoir plus](/help/analyze/report-builder/r-arb-scheduled-reports.md) |

{style=&quot;table-layout:auto&quot;}

## Avis de fin de vie

| Produit ou fonctionnalité en fin de vie | Date d’ajout ou de mise à jour | Description |
| --- | --- | --- |
| **Abandon de la fonctionnalité [!UICONTROL Listes de publication]** | 29 septembre 2022 | Dans le cadre de la fin de vie de Reports &amp; Analytics, les listes de publication sont programmées pour atteindre la fin de vie en **décembre 2023**. Vous ne pourrez pas créer de listes de publication ou y accéder pour envoyer ou planifier des projets Analysis Workspace. |
| **Fin de vie de Data Workbench** | 14 septembre 2022 | Adobe a l’intention d’abandonner Data Workbench à compter du **31 décembre 2023**. Consultez l’[annonce de fin de vie du Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=fr) pour plus d’informations. Contactez le gestionnaire de compte Adobe de votre entreprise pour toute question. |
| **Fin de vie de [!DNL Reports & Analytics]** | 4 janvier 2022 | À compter du **31 décembre 2023**, Adobe prévoit dʼabandonner [!DNL Reports & Analytics] et ses rapports et fonctionnalités associés. [!DNL Reports & Analytics] sʼappuie sur des rapports, des visualisations et des technologies sous-jacentes qui ne répondent plus aux normes technologiques dʼAdobe. La plupart des fonctionnalités de [!DNL Reports & Analytics] sont disponibles dans [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Depuis la publication d’Analysis Workspace en 2015, les fonctionnalités de [!DNL Reports & Analytics] ont migré vers Analysis Workspace, de telle sorte quʼun seuil de parité en matière de workflow a été atteint. [Cet avis](https://spark.adobe.com/page/6WnF8JK6IRDhf/) décrit le processus de fin de vie. |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

Pour connaître les dernières mises à jour des versions d’AppMeasurement (version 2.23.0), reportez-vous aux [Notes de mise à jour d’AppMeasurement pour JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=fr).

## Ressources connexes

* [Notes de mise à jour précédentes pour 2022](/help/release-notes/2022.md)
* [Notes de mise à jour de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=fr)
* [Notes de mise à jour de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* Dernières mises à jour des [produits Adobe Experience Cloud](https://business.adobe.com/fr/products/adobe-experience-cloud-products.html)
