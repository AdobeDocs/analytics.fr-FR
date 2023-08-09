---
description: Utilisation de Report Builder avec Microsoft Power BI.
title: Publication sur Power BI - Aperçu
feature: Report Builder
role: User, Admin
exl-id: 3464c153-2db5-41af-9e83-da081ec64ad3
source-git-commit: fb39f906d6c08713e4dc8211c917b2942502868e
workflow-type: tm+mt
source-wordcount: '1171'
ht-degree: 79%

---

# Publication sur Power BI - Aperçu

Microsoft Power BI est une suite de tableaux de bord d’analyse commerciale permettant d’analyser les données et de partager les informations. L’intégration d’Adobe Analytics à Power BI vous permet de visualiser les données d’analyse de Report Builder dans Microsoft Power BI et de les partager facilement avec l’ensemble de votre entreprise.

En tant qu’analyste, vous deviez auparavant planifier la distribution de classeurs de Report Builder à l’aide de l’adresse électronique ou du ftp. Vous pouvez désormais donner aux parties prenantes de l’entreprise l’accès, depuis leurs comptes de Power BI, à des données précises et à jour dans un environnement Web accessible sur toutes les plateformes et tous les appareils.

L’association de la fonctionnalité de génération de rapports du Report Builder aux fonctionnalités de visualisation de Power BI rend les informations plus accessibles pour tous les membres de l’organisation. Avec Power BI, vous pouvez également intégrer Adobe Analytics à d’autres sources de données, par exemple, des sources de point de vente ou de gestion de la relation client, pour découvrir des informations sur les clients, des associations et des opportunités uniques.

![Diagramme de l’icône de Power BI Microsoft plus l’icône Adobe Analytics.](assets/aaplusbi.png)

## Configuration requise {#section_0B71092D853446F38FA36447DAC0D32B}

* La version 5.5 du Report Builder d’Adobe est [installée](/help/analyze/report-builder/setup/t-install-arb.md)
* Compte Microsoft actif qui vous permet de vous connecter à Power BI

## Publier le classeur sur Power BI {#section_21CA66229EC240D49594A9A7D3FBA687}

Les classeurs planifiés sont des feuilles de calcul Excel renseignées avec des données d’Adobe Analytics qui sont distribuées régulièrement.

**Publier un classeur dans Report Builder**

1. Dans le Report Builder, générez et sauvegardez un classeur.
1. Dans la barre d’outils du Report Builder, cliquez sur **[!UICONTROL Planifier]** > **[!UICONTROL Nouveau]**.

1. Dans l’Assistant de planification - Options de base, cochez la case située en regard de **[!UICONTROL Publier le classeur sur Microsoft Power BI]**.

   ![Capture d’écran de l’Assistant de planification des Reports Builder présentant l’option permettant de cocher l’option Publier le classeur sur la Power BI Microsoft .](assets/simple-schedule-wizard.png)

1. Indiquez votre adresse e-mail et envoyez immédiatement, ou définissez la fréquence de planification (par heure, quotidiennement, etc.).
1. Cliquez sur **[!UICONTROL OK]** pour publier.
1. Vous devrez alors vous connecter à votre compte Microsoft. Indiquez vos informations d’identification.
1. Le classeur du Report Builder est planifié et publié sur Power BI.

   À chaque instance planifiée, et après que le processus de planification du Report Builder a actualisé le classeur avec les données d’analyse mises à jour, le classeur sera publié sur Microsoft Power BI.

**Afficher les données du classeur du Report Builder dans Power BI**

1. Dans Power BI, double-cliquez sur le classeur en dessous du menu [!UICONTROL Classeurs].

   ![Capture d’écran de la vue Classeurs de Power BI.](assets/workbooks-power-bi.png)

1. Vous pouvez désormais visualiser les données de tableau de bord du classeur.    ![Données du tableau de bord du classeur.](assets/view-data-pbi.png)

1. Vous pouvez ensuite épingler une zone de ce classeur de façon à l’inclure dans l’un de vos tableaux de bord Power BI.

## Publier tous les tableaux formatés du classeur en tant que tableaux de jeu de données Power BI {#section_7C54A54E75184DD6BAEF4ACCE241239A}

>[!NOTE]
>
>Si le classeur contient une macro, l’option « Publier tous les tableaux formatés du classeur en tant que tableaux de jeu de données Power BI » sera désactivée.

Au lieu d’importer l’ensemble du classeur, vous pouvez n’importer que le contenu de l’ensemble des tableaux formatés de ce classeur.

**Cas d’utilisation** : Vous avez un classeur Excel qui extrait des données à partir de plusieurs requêtes du Report Builder et crée un tableau récapitulatif avec de nombreuses formules. Vous pouvez n’importer que le tableau récapitulatif dans Power BI et créer une visualisation pour ce tableau.

**Publier un tableau formaté dans le Report Builder**

1. Dans le Report Builder, générez un tableau de données comprenant une ligne d’en-tête, suivie d’une ligne de données.
1. Sélectionnez le tableau, puis l’option **[!UICONTROL Formater en tant que tableau]** dans le menu [!UICONTROL Accueil]. Un nom de tableau par défaut est attribué (Tableau 1, Tableau 2, etc.), mais vous pouvez le modifier dans le menu [!UICONTROL Conception].

1. Dans la barre d’outils du Report Builder, cliquez sur **[!UICONTROL Planifier]** > **[!UICONTROL Nouveau]**.

1. Dans l’Assistant de planification - Options de base, cliquez sur **[!UICONTROL Options de planification avancées]**.
1. Dans l’[!UICONTROL Assistant de planification - Options avancées], dans l’onglet **[!UICONTROL Options de publication]**, cochez la case située en regard de **[!UICONTROL Publier tous les tableaux formatés en tant que tableaux de jeu de données Power BI]**.

   ![Capture d’écran montrant l’ Assistant de planification - Options de publication avancées avec Publier tous les tableaux formatés en tant que tableaux de jeu de données de Power BI.](assets/advanced-schedule-wizard2.png)

1. (Facultatif) Vous pouvez personnaliser le nom de la ressource publiée dans Power BI. Cela peut être utile si vous utilisez le contrôle de version dans le nom du classeur (par exemple, monclasseur_v1.1.xlsx) et que vous ne souhaitez pas que le numéro de version figure dans le nom de la ressource Power BI publiée. Un autre avantage est que la ressource publiée ne changera pas si le numéro de version change. (Affichez les [spécifications](/help/analyze/report-builder/c-publish-power-bi/specifications-limits.md) ici.)

**Visualiser les données de tableau dans Power BI**

1. Dans Power BI, accédez au menu **[!UICONTROL Espaces de travail]** > **[!UICONTROL Jeux de données]**.

   ![Capture d’écran montrant le menu Jeux de données de Power BI en surbrillance sur Créer des rapports.](assets/datasets-menu.png)

1. Sélectionnez le jeu de données que vous avez publié et cliquez sur l’icône [!UICONTROL Créer un rapport] située juste à côté. Notez que les tableaux s’affichent en tant que Champs.

   ![Capture d’écran présentant le jeu de données publié sélectionné répertoriant les tableaux comme Champs.](assets/formatted-tables.png)

1. Sélectionnez un tableau et ses colonnes associées.

   ![Capture d’écran montrant un tableau sélectionné avec les colonnes associées](assets/view-table-dataset.png)

1. Dans le menu [!UICONTROL Visualisations], vous pouvez sélectionner la manière de visualiser un tableau dans Power BI. Par exemple, vous pouvez choisir de présenter vos données sous forme d’un graphique linéaire :

   ![Capture d’écran du menu Visualisations et graphique en courbes de données.](assets/bi-line-graph.png)

1. À partir de là, vous pouvez créer des visualisations à partir de ce tableau de jeu de données.

## Publier toutes les requêtes du Report Builder sous forme de tableaux de jeu de données Power BI {#section_0C26057C7DBB4068A643FDD688F6E463}

Vous pouvez transformer toutes vos requêtes en tableaux de jeu de données et générer des visualisations à partir de ces tableaux.

>[!IMPORTANT]
>
>Si le classeur contient plus de 100 requêtes, seules les 100 premières requêtes seront publiées sur Power BI. Par ailleurs, pour chaque requête publiée sur Power BI, seules les 10 000 premières lignes de données seront publiées. Par conséquent, bien que ces requêtes soient distribuées correctement à travers la planification, la portée de la publication sur Power BI est limitée.

1. Dans le Report Builder, ouvrez ou créez un classeur avec des requêtes du Report Builder.
1. Dans la barre d’outils du Report Builder, cliquez sur **[!UICONTROL Planifier]** > **[!UICONTROL Nouveau]**.

1. Dans l’Assistant de planification - Options de base, cliquez sur **[!UICONTROL Options de planification avancées]**.
1. Dans l’[!UICONTROL Assistant de planification - Options avancées], dans l’onglet **[!UICONTROL Options de publication]**, cochez la case située en regard de **[!UICONTROL Publier toutes les requêtes du Créateur de rapports en tant que tableaux de jeu de données Power BI]** ![Capture d’écran montrant l’Assistant de planification mettant en surbrillance l’option Publier toutes les requêtes de Report Builder en tant que tableaux de jeu de données de Power BI .](assets/advanced-schedule-wizard2.png)

1. Cliquez sur **[!UICONTROL OK]**.

**Visualiser les données de requête dans Power BI**

Chaque requête du Report Builder planifiée sera publiée en tant que tableau dans le jeu de données. Chaque tableau de requête est nommé en fonction de la dimension principale de la requête et comprend une colonne [!UICONTROL Suites de rapports] et une colonne [!UICONTROL Segments].

1. Dans Power BI, accédez au menu **[!UICONTROL Espaces de travail]** > **[!UICONTROL Jeux de données]**.

1. Sélectionnez la requête que vous avez publiée et cliquez sur l’icône [!UICONTROL Créer un rapportt] située juste à côté.

   Notez que les requêtes s’affichent en tant que tableaux dans le menu [!UICONTROL Champs].

   ![Capture d’écran montrant une requête sélectionnée publiée au format d’une ligne d’en-tête unique à deux chiffres.](assets/published-requests.png)

   >[!NOTE]
   >
   >Quelle que soit la façon dont vous avez configuré la présentation de votre requête du Report Builder dans le classeur (disposition croisée dynamique, disposition personnalisée, certaines colonnes invisibles), le Report Builder publie toujours votre requête selon le même format bidimensionnel à une seule ligne d’en-tête : Date, Dimensions, Mesures, Suites de rapports, Segments.

1. Notez également l’existence d’un tableau supplémentaire intitulé **[!UICONTROL Légende]**. Si vous sortez une requête du contexte du Report Builder, il peut être difficile de se rappeler ce à quoi correspond chaque requête. Le tableau Légende a pour fonction, par exemple, d’afficher le nom de chaque requête sous Identifiant du tableau. Vous pouvez également ajouter les autres colonnes de Légende pour obtenir un aperçu global de la requête.

   ![Capture d’écran montrant le tableau Légende indiquant le nom de chaque requête sous Identifiant du tableau.](assets/legend-table.png)
