---
title: Dernières notes de mise à jour dʼAnalytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 4168dc9579950cad02725242aa97e07721c66978
workflow-type: tm+mt
source-wordcount: '1239'
ht-degree: 60%

---

# Notes de mise à jour actuelles d’Adobe Analytics (Mai 2023)

**Dernière mise à jour** : 8 mai 2023

Les mises à jour dʼAdobe Analytics suivent une [modèle de diffusion continue](releases.md), ce qui permet un déploiement plus flexible et progressif des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités nouvelles ou mises à jour dans Adobe Analytics {#features}

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Renvoi pour les environnements de test hors production** | Lors de la création d’un flux de données Analytics Source Connector dans un environnement de test hors production, le renvoi dans les environnements de test hors production sera limité à 3 mois. Il restera à 13 mois pour les environnements de test de production. | S.O. | 26 avril 2023 |
| **Partage de liens pour les projets (aucune connexion requise)** | Vous pouvez désormais partager des liens en lecture seule vers les projets Analysis Workspace avec des personnes qui n’ont pas accès à Adobe Analytics. Cela inclut le partage avec des personnes en dehors de votre organisation ou au sein de votre organisation qui ne sont pas configurées pour Adobe Analytics. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=en#share-public-link)<p>Cette fonctionnalité est activée par défaut et peut être désactivée par l’administrateur système. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=en#company-preferences)</p> | 3 mai 2023 | Juin 2023 |
| **Écran d’accueil mis à jour pour l’application de tableaux de bord Analytics (application mobile)** | Le nouvel écran d’accueil mis à jour vous permet d’afficher toutes vos fiches d’évaluation dans une seule liste de fiches d’évaluation consolidée.  Si vous avez accès à plusieurs organisations sous une seule connexion, toutes les Fiches d’évaluation de vos organisations seront disponibles dans une seule liste. | S.O. | 10 mai 2023 |
| **Tri des composants dans Analysis Workspace** | Une nouvelle option de tri est désormais disponible lorsque vous affichez des composants dans le rail de gauche ou dans le dictionnaire de données dans Analysis Workspace. Vous pouvez trier les composants par Recommandé (ceux qui sont les plus couramment utilisés), Alphabétique ou Catégoriel (type).<p>Auparavant, vous pouviez uniquement rechercher ou filtrer des composants. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html?lang=en)</p> | S.O. | 10 mai 2023 |
| **Suppression de lignes contenant des dimensions dynamiques d’un tableau à structure libre** | Dans un tableau à structure libre d’Analysis Workspace, vous pouvez désormais supprimer rapidement des lignes spécifiques contenant des dimensions dynamiques à l’aide de l’icône x. Dans ce cas, une règle de filtrage &quot;N’est pas égale&quot; est automatiquement appliquée.<p>Auparavant, la seule manière de supprimer des lignes contenant des dimensions dynamiques consistait à créer manuellement une règle dans la boîte de dialogue Filtre. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.html?lang=en)</p> | S.O. | 10 mai 2023 |
| **Nouveau bouton pour ajouter une visualisation dans un panneau** | Un nouveau bouton est désormais disponible au bas de chaque panneau dans Analysis Workspace, ce qui vous permet d’ajouter rapidement une visualisation. <p>Auparavant, les seules méthodes permettant d’ajouter une visualisation à un panneau étaient de faire glisser une visualisation depuis le rail de gauche, de dupliquer ou de copier une visualisation existante ou de créer un panneau vierge. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=en#add-visualizations-to-a-panel)</p> | S.O. | 17 mai 2023 |
| **Lien profond (application mobile)** | Permet aux utilisateurs d’envoyer des liens vers des Fiches d’évaluation qui les mèneront directement au projet de Fiche d’évaluation dans l’application. Cela facilite encore le partage de projets et améliore l’engagement d’une audience moins technique. | À confirmer | À confirmer |

{style="table-layout:auto"}

## Correctifs dans Adobe Analytics

AN-312098; AN-318309; AN-316675; AN-318173; AN-310359; AN-317613; AN-318836; AN-315744; AN-311772; AN-318719; AN-314074; AN-316651<!--"Verified" status-->; AN-318602; AN-315961; AN-317534; AN-318607; AN-316498; AN-316648; AN-318244; AN-317747; AN-318432; AN-318231; AN-317590; AN-318415; AN-318154; AN-316647; N-314417; AN-317614; AN-317725; AN-318114; AN-317876; AN-318052; AN-317966; AN-316477; AN-318036; AN-317931; AN-318045; AN-316246; AN-317281; AN-317879; AN-308077; AN-317708; AN-316115; AN-315963

## Avis importants pour les administrateurs d’Adobe Analytics {#admin}

| Avis | Date d’ajout ou de mise à jour | Description |
| ----------- | ---------- | ---------- |
| **Remarque : Nouvelles adresses IP utilisées par les flux de données Adobe Analytics et la sortie de Data Warehouse dans le centre de données de Londres** | 27 avril 2023 | Pour les clients du centre de données de Londres qui ont des demandes de flux de données et/ou des rapports de Data Warehouse diffusés vers un service FTP/SFTP, les plages d’adresses IP suivantes doivent être ajoutées à la configuration de votre pare-feu afin d’autoriser l’accès : <ul><li>130.248.244.32/29</li><li>130.248.244.40/29</li></ul> |
| **Les processus de recherche d’appareils utilisent désormais un service tiers lors de la recherche** | 3 mars 2023 | Le 2 mars 2023, dans le cadre du déploiement du support pour les indications du client, nous avons mis à jour nos processus de recherche d’appareils, qui sont désormais confiés à un service tiers. Ce dernier était déjà utilisé lors de la recherche d’appareils mobiles uniquement. Dans le cadre de ce déploiement, certains systèmes d’exploitation de bureau ont été libellés de manière incorrecte avec le texte « mobile » (par exemple, « Mobile OS X 10.15.7 » au lieu de « OS X 10.15.7 »).<p>La version d’avril d’Adobe y apportera un correctif. Les rapports Analytics et CJA seront mis à jour rétroactivement, car leurs rapports recherchent le nom du système d’exploitation en fonction d’un identifiant enregistré dans les données d’événement. Une fois que la valeur de recherche correspondant à un identifiant est mise à jour, tous les rapports seront corrigés, y compris les données historiques. Pour les clientes et clients des [!UICONTROL Flux de données], la modification est rétroactive si vous utilisez un processus de recherche similaire au moment de la création de rapports. Cependant, si vous stockez la valeur du système d’exploitation dans vos données d’événement, les rapports ne seront mis à jour qu’ultérieurement. Pour plus de détails, consultez la section [Système d’exploitation](/help/components/dimensions/operating-systems.md). |

{style="table-layout:auto"}

## Avis de fin de vie {#eol}

| Produit ou fonctionnalité en fin de vie | Date d’ajout ou de mise à jour | Description |
| --- | --- | --- |
| **Abandon du service de tracking des téléphones mobiles japonais** | 21 mars 2023 | À l’attention de nos clientes et clients japonais uniquement : à la **fin du mois de mai 2023**, le service japonais de tracking des téléphones mobiles (mod_ktrack) sera rendu obsolète. Nous vous prions de nous excuser pour ce désagrément et vous invitons à désinstaller ou désactiver les modules installés sur votre serveur Apache. Consultez les pages 27 et 28 de [ce document](/help/release-notes/mod_ktrackforSiteCatalyst_ver1.40.pdf) à titre de référence. |
| **Fin de vie de [!DNL Reports & Analytics]** | 7 mars 2023 | À compter du **31 décembre 2023**, Adobe prévoit dʼabandonner [!DNL Reports & Analytics] et ses rapports et fonctionnalités associés. [!DNL Reports & Analytics] sʼappuie sur des rapports, des visualisations et des technologies sous-jacentes qui ne répondent plus aux normes technologiques dʼAdobe. La plupart des fonctionnalités de [!DNL Reports & Analytics] sont disponibles dans [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=fr). Depuis la publication d’Analysis Workspace en 2015, les fonctionnalités de [!DNL Reports & Analytics] ont migré vers Analysis Workspace, de telle sorte quʼun seuil de parité en matière de workflow a été atteint. [Cet avis](https://spark.adobe.com/page/6WnF8JK6IRDhf/) décrit le processus de fin de vie.<p>Le 31 décembre 2023, nous allons mettre fin à de nombreuses fonctionnalités Reports &amp; Analytics associées, notamment : Rapports planifiés, Extractions de données et Rapports DL. Après le 31 décembre 2023, les rapports planifiés ne seront plus envoyés. En **avril 2023**, tous les rapports dont l’expiration était planifiée au-delà du 31 décembre 2023 seront automatiquement mis à jour et expireront le 31 décembre 2023. En outre, vous ne pouvez plus planifier les rapports ultérieurs au-delà du 31 décembre 2023. |
| **Fin de vie de la mesure [!UICONTROL Personnes]** | 9 mars 2023 | Avec l’abandon de la fonctionnalité [[!DNL Device Co-op]](https://experienceleague.adobe.com/docs/discontinued/using/device-co-op.html?lang=fr), la mesure Personnes liée à la coopération entre appareils n’est désormais plus pertinente. Le 8 mai 2023, nous supprimerons la mesure [!UICONTROL Personnes]. À ce stade, nous redirigerons ses données vers la mesure [!UICONTROL Visiteur unique] afin d’empêcher la ventilation des projets, des segments et des mesures calculées.<p>**Remarque** : la mesure [[!UICONTROL Personnes] liée aux analyses entre appareils](/help/components/metrics/people.md) n’est pas affectée par cette annonce. |
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
