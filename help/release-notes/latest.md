---
title: Dernières notes de mise à jour dʼAnalytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 1d98d711c17d3c7ca487b8f5bd4e918a9a399ea7
workflow-type: tm+mt
source-wordcount: '1456'
ht-degree: 53%

---

# Notes de mise à jour actuelles d’Adobe Analytics (Juin 2023)

**Dernière mise à jour** : 1 juin 2023

Les mises à jour dʼAdobe Analytics suivent une [modèle de diffusion continue](releases.md), ce qui permet un déploiement plus flexible et progressif des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Principaux éléments de la mise à jour {#highlights}

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Partage de liens pour les projets (aucune connexion requise)** | Vous pouvez désormais partager des liens en lecture seule vers les projets Analysis Workspace avec des personnes qui n’ont pas accès à Adobe Analytics. Cela inclut le partage avec des personnes hors de votre organisation, ou avec des personnes au sein de votre organisation qui ne sont pas configurées pour Adobe Analytics. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=fr#share-public-link)<p>Cette fonctionnalité est activée par défaut et peut être désactivée par l’administrateur ou administratrice système. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=fr)</p> | 3 mai 2023 | 7 juin 2023 |
| **Jeux de classifications - consolidation** | Combinez des classifications de différentes suites de rapports dans un jeu de données consolidé. Le jeu de données consolidé peut être utilisé dans des jeux de classifications ou comme jeu de données de recherche dans CJA. En savoir plus (bientôt disponible) |  | 7 juin 2023 |
| **Jeux de classifications - Créateur de règles** | Utilisez le créateur de règles de classification dans l’architecture actuelle du jeu de classifications. En savoir plus (bientôt disponible) |  | 7 juin 2023 |
| **Jeux de classifications - importation automatisée** | Vous pouvez désormais importer automatiquement des données de jeu de classifications à partir des destinations de stockage dans le cloud. En savoir plus (bientôt disponible) |  | 7 juin 2023 |
| **Nouvelle variable AppMeasurement** | La variable `doubleEncodeLinkParameters` prend en charge les cas de périphérie où les implémentations codent des caractères à plusieurs octets dans les variables de suivi des liens. La plupart des implémentations n’ont pas besoin de définir cette variable. En savoir plus (bientôt disponible) |  | 7 juin 2023 |
| **Destinations sécurisées pour l’exportation des flux de données** | Les flux de données peuvent désormais être envoyés vers les destinations de stockage dans le cloud suivantes :<ul><li>Amazon S3</li><li>RBAC Azure</li><li>SAS Azure</li><li>Google Cloud Platform</li></ul>Les destinations qui étaient auparavant disponibles (FTP, SFTP, S3 et Azure Blob) ne sont plus recommandées. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/create-feed.html?lang=fr) |  | 12 juin 2023 |
| **Création de rapports de robots dans Workspace** | La création de rapports sur les robots est désormais disponible dans Analysis Workspace. Cette fonctionnalité comporte plusieurs ajouts :<ul><li>Nouvelle dimension : [Nom du robot](/help/components/dimensions/bot-name.md)</li><li>Deux nouvelles mesures : [Pages vues de robots](/help/components/metrics/bot-page-views.md) et [Occurrences du robot](/help/components/metrics/bot-occurrences.md).</li><li>Un nouveau modèle de mesure calculée : [Taux de pages vues des robots](/help/components/c-calcmetrics/cm-reference/default-calcmetrics.md)</li><li>Un nouveau rapport Workspace : Rapports de robots</li></ul>La nouvelle dimension et les nouvelles mesures contiennent des données renvoyées depuis mars 2023. |  | Juin 7,2023 |

{style="table-layout:auto"}

## Autres fonctionnalités nouvelles ou mises à jour {#other}

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Suppression de lignes contenant des dimensions dynamiques d’un tableau à structure libre** | Dans un tableau à structure libre d’Analysis Workspace, vous pouvez désormais supprimer rapidement des lignes spécifiques contenant des dimensions dynamiques à l’aide de l’icône x. Dans ce cas, une règle de filtre &quot;Toujours exclure les éléments&quot; est automatiquement appliquée.<p>Auparavant, la seule manière de supprimer des lignes contenant des dimensions dynamiques consistait à créer manuellement une règle dans la boîte de dialogue Filtre. [En savoir plus](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)</p> | S.O. | 17 mai 2023 |
| **Nouveau bouton pour ajouter une visualisation dans un panneau** | Un nouveau bouton est désormais disponible au bas de chaque panneau dans Analysis Workspace, ce qui vous permet d’ajouter rapidement une visualisation. <p>Auparavant, les seules méthodes permettant d’ajouter une visualisation à un panneau étaient de faire glisser une visualisation depuis le rail de gauche, de dupliquer ou de copier une visualisation existante ou de créer un panneau vierge. [En savoir plus](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</p> | S.O. | 17 mai 2023 |
| **Liens profonds (application mobile)** | Permet aux utilisateurs et utilisatrices d’envoyer des liens vers des cartes de performance qui les dirigeront directement vers le projet de cartes de performance dans l’application. Cela facilite encore plus le partage de projets et améliore l’engagement d’une audience moins technique. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html#share-scorecards-using-a-shareable-link) | S.O. | 17 mai 2023 |
| **Filtres déroulants dynamiques** | Nous introduisons un nouveau type de filtre déroulant qui détermine les valeurs disponibles en fonction des données dans la plage de rapports du panneau et les valeurs dans d’autres filtres déroulants. Vous pouvez utiliser des filtres de liste déroulante dynamiques en faisant glisser une dimension dans la zone de dépôt du panneau tout en maintenant la touche [!UICONTROL Maj]. Les filtres déroulants statiques restent inchangés en faisant glisser un groupe d’éléments de dimension dans la zone de dépôt du panneau tout en maintenant la touche [!UICONTROL Maj]. [En savoir plus](/help/analyze/analysis-workspace/c-panels/panels.md) |  | 14 juin 2023 |
| **Mise à jour de la page d’apprentissage Analytics** | L’onglet Apprentissage de la page d’entrée Adobe Analytics contient désormais les améliorations suivantes :<ul><li>Amélioration de la conception qui affiche plus de contenu d’apprentissage sur une seule page avec une navigation améliorée.</li><li>Possibilité de personnaliser le contenu de l’apprentissage par niveau d’expérience (débutant, intermédiaire et avancé)</li></ul>[En savoir plus](/help/analyze/landing.md) |  | Juin 30,2023 |
| **Tri des composants dans Analysis Workspace** | Une nouvelle option de tri est désormais disponible lorsque vous affichez des composants dans le rail de gauche ou dans le dictionnaire de données dans Analysis Workspace. Vous pouvez trier les composants par Recommandé (ceux qui sont les plus couramment utilisés), Ordre alphabétique ou par Catégorie (type).<p>Auparavant, vous pouviez uniquement rechercher ou filtrer des composants. [En savoir plus](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)</p> | S.O. | À confirmer |

{style="table-layout:auto"}

## Correctifs dans Adobe Analytics

-311878 ; AN-313968 ; AN-314130 ; AN-315701 ; AN-315761 ; AN-316613 ; AN-317563 ; AN-318829 ; AN-319009 ; AN-319043 ; AN-319066 ; AN- ; AN-319166 ; AN-319245 ; AN-319271 ; AN-319381 ; AN-319391 ; AN-319482 ; AN-319621 ; AN-319637 ; AN-319676 ; AN-320176 ; AN-320221 ; AN-320225 ; AN-320286 ; AN-320312 ; AN-320316 ; AN-320449 ; AN-320477 ; AN-320492 ; AN-320538 ; AN-320556 ; AN-320569 ; AN-320679 ; AN-320684 ; AN-320786 ; AN-320802 ; AN-320811 ; AN-320812 ; AN-320815 ; AN-321032 ; AN-321033 ; AN-321070 ; AN-321096 ; AN-321105 ; AN-321122 ; AN-321337 ;

## Avis importants pour les administrateurs d’Adobe Analytics {#admin}

| Avis | Date d’ajout ou de mise à jour | Description |
| ----------- | ---------- | ---------- |
| **Expiration de 37 mois des identifiants d’achat et d’événement (sérialisation d’événements)** | Mai 25,2023 | Une prochaine version du moteur de traitement des accès Analytics, destinée à être publiée dans **fin juin 2023 ou début juillet 2023**, commence à appliquer une expiration de 37 mois pour les identifiants d’achat et les identifiants d’événement (sérialisation d’événements). Actuellement, les identifiants d’achat et d’événement n’expirent jamais dans Adobe Analytics. Une fois qu’un identifiant d’achat ou un identifiant d’événement est affiché/utilisé, tout accès futur, peu importe quand, verra cet achat ou cet événement marqué comme un doublon. Avec la nouvelle version du moteur de traitement :<ul><li>Les identifiants d’achat et d’événement expirent toujours après 37 mois.</li><li>Si 37 mois se sont écoulés depuis que l’ID d’achat ou l’ID d’événement a été affiché, il n’est plus considéré comme un achat ou un événement en double.</li><li> Si vous &quot;réutilisez&quot; les identifiants d’achat ou d’événement d’il y a plus de 37 mois, ils ne sont plus considérés comme des doublons.</li></ul> |
| **Migration vers les informations d’identification Adobe IO OAuth serveur à serveur** | 11 mai 2023 | L’API Adobe Analytics et les clients Livestream qui utilisent les informations d’identification JWT d’Adobe IO doivent migrer vers les informations d’identification OAuth serveur à serveur d’Adobe IO par **1er janvier 2025**. Pour plus d’informations et de chronologies, reportez-vous à l’avis de fin de vie dans le tableau ci-dessous. |
| **Nouvelles adresses IP utilisées par les flux de données Adobe Analytics et la sortie de Data Warehouse dans le centre de données de Londres** | 27 avril 2023 | Cela concerne les clients du centre de données de Londres qui ont des demandes de flux de données et/ou des rapports de Data Warehouse remis à un service FTP/SFTP. Les plages d’adresses IP suivantes doivent être ajoutées à la configuration de votre pare-feu pour permettre l’accès : <ul><li>130.248.244.32/29</li><li>130.248.244.40/29</li></ul> |

{style="table-layout:auto"}

## Avis de fin de vie {#eol}

| Produit ou fonctionnalité en fin de vie | Date d’ajout ou de mise à jour | Description |
| --- | --- | --- |
| **Migration vers les informations d’identification Adobe IO OAuth serveur à serveur** | 11 mai 2023 | L’API Adobe Analytics et les clients Livestream qui utilisent les informations d’identification JWT d’Adobe IO doivent migrer vers les informations d’identification OAuth serveur à serveur d’Adobe IO par **1er janvier 2025**. Adobe IO n’autorise pas la création de nouvelles informations d’identification JWT à compter du 1er mai 2024. Les clients utilisant JWT doivent créer des informations d’identification OAuth serveur à serveur ou migrer leurs informations d’identification JWT existantes vers des informations d’identification OAuth serveur à serveur. Les clients doivent également mettre à jour leurs applications clientes pour utiliser les nouvelles informations d’identification OAuth serveur à serveur. <ul><li>[Migration des informations d’identification du compte de service (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Utilisation des nouvelles informations d’identification OAuth serveur à serveur](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Questions fréquentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **Fin de vie de [!DNL Reports & Analytics]** | 7 mars 2023 | À compter du **31 décembre 2023**, Adobe prévoit dʼabandonner [!DNL Reports & Analytics] et ses rapports et fonctionnalités associés. [!DNL Reports & Analytics] sʼappuie sur des rapports, des visualisations et des technologies sous-jacentes qui ne répondent plus aux normes technologiques dʼAdobe. La plupart des fonctionnalités de [!DNL Reports & Analytics] sont disponibles dans [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=fr). Depuis la publication d’Analysis Workspace en 2015, les fonctionnalités de [!DNL Reports & Analytics] ont migré vers Analysis Workspace, de telle sorte quʼun seuil de parité en matière de workflow a été atteint. [Cet avis](https://spark.adobe.com/page/6WnF8JK6IRDhf/) décrit le processus de fin de vie.<p>Le 31 décembre 2023, nous allons mettre fin à de nombreuses fonctionnalités Reports &amp; Analytics associées, notamment : Rapports planifiés, Extractions de données et Rapports DL. Après le 31 décembre 2023, les rapports planifiés ne seront plus envoyés. En **avril 2023**, tous les rapports dont l’expiration était planifiée au-delà du 31 décembre 2023 seront automatiquement mis à jour et expireront le 31 décembre 2023. En outre, vous ne pouvez plus planifier les rapports ultérieurs au-delà du 31 décembre 2023. |
| **Abandon de la fonctionnalité [!UICONTROL Listes de publication]** | 29 septembre 2022 | Dans le cadre de la fin de vie de Reports &amp; Analytics, les [!UICONTROL listes de publication] sont programmées pour atteindre la fin de vie en **décembre 2023**. Vous ne pourrez pas créer de [!UICONTROL listes de publication] ou y accéder pour envoyer ou planifier des projets [!UICONTROL Analysis Workspace]. |
| **Fin de vie de Data Workbench** | 14 septembre 2022 | Adobe a l’intention d’abandonner Data Workbench à compter du **31 décembre 2023**. Consultez l’[annonce de fin de vie du Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=fr) pour plus d’informations. Contactez le gestionnaire de compte Adobe de votre entreprise pour toute question. |

{style="table-layout:auto"}

## AppMeasurement

Pour connaître les dernières mises à jour des versions d’AppMeasurement (version 2.23.0), reportez-vous aux [Notes de mise à jour d’AppMeasurement pour JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=fr).


## Ressources connexes

* [Notes de mise à jour précédentes pour 2022](/help/release-notes/2022.md)
* [Notes de mise à jour de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=fr)
* [Notes de mise à jour de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* Dernières mises à jour des [produits Adobe Experience Cloud](https://business.adobe.com/fr/products/adobe-experience-cloud-products.html)
