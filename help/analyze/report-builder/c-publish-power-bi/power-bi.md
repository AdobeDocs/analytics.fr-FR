---
description: valeur nulle
title: Publication sur Power BI - Aperçu
uuid: ad688817-6e3c-45da-983d-48c123465309
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Publication sur Power BI - Aperçu

Microsoft Power BI est une suite de d’analyses d’entreprise permettant d’analyser des données et de partager des informations. L’intégration d’Adobe Analytics à Power BI vous permet de visualiser les données d’analyse du Report Builder sur Microsoft Power BI et de les partager facilement avec l’ensemble de votre entreprise.

Auparavant, en tant qu’analyste, vous deviez planifier la diffusion des classeurs du Report Builder par courrier électronique (ou ftp). Vous pouvez maintenant donner à vos utilisateurs professionnels l&#39;accès (depuis leurs comptes Power BI) à des données précises et à jour dans un de  Web accessible sur toutes les plates-formes et tous les périphériques.

L’association de la fonctionnalité de génération de rapports du Report Builder aux fonctionnalités de visualisation de Power BI rend les informations plus accessibles pour tous les membres de l’organisation. Avec Power BI, vous pouvez également intégrer Adobe Analytics à d’autres sources de données (point de vente, gestion de la relation client, par exemple) afin de découvrir des informations client uniques, des associations et des opportunités.

![](assets/aaplusbi.png)

L’intégration avec le Report Builder Adobe vous permet de

* [Publier les classeurs du Report Builder planifiés sur Power BI](/help/analyze/report-builder/whats-new-arb.md#rb-5-5-section)
* [Publier tous les tableaux formatés du classeur en tant que tableaux de jeu de données Power BI](/help/analyze/report-builder/whats-new-arb.md#rb-5-5-section)
* [Publier toutes les requêtes du Report Builder sous forme de tableaux de jeu de données Power BI](/help/analyze/report-builder/whats-new-arb.md#rb-5-5-section)

## Configuration requise {#section_0B71092D853446F38FA36447DAC0D32B}

* La version 5.5 du Report Builder d’Adobe est [installée](/help/analyze/report-builder/setup/t-install-arb.md)
* Compte Microsoft actif qui vous permet de vous connecter à Power BI

## Publier le classeur sur Power BI {#section_21CA66229EC240D49594A9A7D3FBA687}

Les classeurs planifiés sont des feuilles de calcul Excel renseignées avec des données d’Adobe Analytics et envoyées à intervalles réguliers planifiés.

**Publier un classeur dans le Report Builder**

1. Dans le Report Builder, générez et sauvegardez un classeur.
1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]** > **[!UICONTROL New]**.

1. Dans l&#39;Assistant Planification de base, cochez la case en regard de **[!UICONTROL Publish Workbook to Microsoft Power BI]**.

   ![](assets/simple-schedule-wizard.png)

1. Indiquez votre adresse électronique et envoyez-la immédiatement ou indiquez la fréquence de planification (horaire, quotidien, etc.).
1. Cliquez sur **[!UICONTROL OK]** pour publier.
1. Vous serez désormais invité à vous connecter à votre compte Microsoft. Fournissez vos informations d’identification.
1. Le classeur du Report Builder est planifié et publié sur Power BI.

   À chaque instance planifiée, et après que le processus de planification du Report Builder a actualisé le classeur avec les données d’analyse mises à jour, le classeur sera publié sur Microsoft Power BI.

**Afficher les données du classeur du Report Builder dans Power BI**

1. Dans Power BI,  cliquez sur le classeur sous le [!UICONTROL Workbooks] menu.

   ![](assets/workbooks-power-bi.png)

1. Vous pouvez désormais visualiser les données de tableau de bord du classeur.  ![](assets/view-data-pbi.png)

1. Vous pouvez ensuite épingler une zone de ce classeur de façon à l’inclure dans l’un de vos tableaux de bord Power BI.

## Publier tous les tableaux formatés du classeur en tant que tableaux de jeu de données Power BI {#section_7C54A54E75184DD6BAEF4ACCE241239A}

>[!NOTE] Si le classeur contient une macro, l’option « Publier tous les tableaux formatés du classeur en tant que tableaux de jeu de données Power BI » sera désactivée.

Au lieu d’importer l’intégralité du classeur, vous ne pouvez importer que le contenu de tous les tableaux formatés du classeur.

**Cas d’utilisation** : Vous avez un classeur Excel qui extrait des données à partir de plusieurs requêtes du Report Builder et crée un tableau récapitulatif avec de nombreuses formules. Vous pouvez uniquement importer le tableau récapitulatif dans Power BI et créer une visualisation à cet effet.

**Publier un tableau formaté dans le Report Builder**

1. Dans le Report Builder, générez un tableau de données comprenant une ligne d’en-tête, suivie d’une ligne de données.
1. Sélectionnez le tableau et sélectionnez-le **[!UICONTROL Format as Table]** dans le [!UICONTROL Home] menu. The table gets named by default (Table 1, Table 2, etc.), but you can change the name on the [!UICONTROL Design]menu.

1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]** > **[!UICONTROL New]**.

1. Dans l&#39;Assistant Planification de base, cliquez sur **[!UICONTROL Advanced Scheduling Options]**.
1. Dans le [!UICONTROL Scheduling Wizard - Advanced]panneau **[!UICONTROL Publishing Options]** , cochez la case en regard de **[!UICONTROL Publish all Formatted Tables as Power BI dataset tables]**.

   ![](assets/advanced-schedule-wizard2.png)

1. (Facultatif) Vous pouvez personnaliser le nom du fichier publié dans Power BI. Cela peut s’avérer utile si vous utilisez le contrôle de version dans le nom du classeur (par exemple, myclasseur_v1.1.xlsx) et que vous ne souhaitez pas que le numéro de version s’affiche dans le nom du fichier Power BI publié. Il présente l’avantage supplémentaire que la ressource publiée ne changera pas si le numéro de version change. ( [Spécifications](/help/analyze/report-builder/c-publish-power-bi/specifications-limits.md) de  ici.)

**Visualiser les données de tableau dans Power BI**

1. Dans Power BI, accédez au menu **[!UICONTROL Workspaces]** > **[!UICONTROL Datasets]** .

   ![](assets/datasets-menu.png)

1. Sélectionnez le jeu de données que vous avez publié et cliquez sur l’ [!UICONTROL Create report] icône en regard de celui-ci. Les tableaux s’affichent sous forme de champs.

   ![](assets/formatted-tables.png)

1. Sélectionnez un tableau et ses colonnes associées.

   ![](assets/view-table-dataset.png)

1. Dans le [!UICONTROL Visualizations] menu, vous pouvez choisir comment visualiser un tableau dans Power BI. Par exemple, vous pouvez choisir de présenter vos données sous forme de graphique linéaire :

   ![](assets/bi-line-graph.png)

1. A partir de là, vous pouvez créer des visualisations à partir de ce tableau de jeux de données.

## Publier toutes les requêtes du Report Builder sous forme de tableaux de jeu de données Power BI {#section_0C26057C7DBB4068A643FDD688F6E463}

Vous pouvez transformer toutes vos requêtes en tableaux de jeu de données et générer des visualisations à partir de ces tableaux.

>[!IMPORTANT]
>
>Si le classeur contient plus de 100 requêtes, seules les 100 premières requêtes seront publiées sur Power BI. De plus, pour chaque requête publiée sur Power BI, seules les 10 000 premières lignes de données seront publiées. Ainsi, bien que ces demandes soient exécutées avec succès par le biais de la planification, la portée de la publication sur Power BI est limitée.

1. Dans le Report Builder, ouvrez ou créez un classeur avec des requêtes du Report Builder.
1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]** > **[!UICONTROL New]**.

1. Dans l&#39;Assistant Planification de base, cliquez sur **[!UICONTROL Advanced Scheduling Options]**.
1. Dans le [!UICONTROL Scheduling Wizard - Advanced]panneau **[!UICONTROL Publishing Options]** , cochez la case en regard de **[!UICONTROL Publish all Report Builder Requests as Power BI Dataset Tables]**![](assets/advanced-schedule-wizard2.png)

1. Cliquez sur **[!UICONTROL OK]**.

**Visualiser les données de requête dans Power BI**

Chaque requête du Report Builder planifiée sera publiée en tant que tableau dans le jeu de données. Chaque table de requête porte le nom de la dimension principale de la requête et comporte une [!UICONTROL Report Suite] colonne et une [!UICONTROL Segments] .

1. Dans Power BI, accédez au menu **[!UICONTROL Workspaces]** > **[!UICONTROL Datasets]** .

1. Sélectionnez la requête que vous avez publiée, puis cliquez sur l’ [!UICONTROL Create report] icône en regard de celle-ci.

   Notez que les requêtes apparaissent sous forme de tableaux dans le [!UICONTROL Fields] menu.

   ![](assets/published-requests.png)

   >[!NOTE]
   >
   >Quelle que soit la façon dont vous avez configuré la présentation de votre requête du Report Builder dans le classeur (disposition croisée dynamique, disposition personnalisée, certaines colonnes invisibles), le Report Builder publie toujours votre requête selon le même format bidimensionnel à une seule ligne d’en-tête : Date, Dimensions, Mesures, Suites de rapports, Segments.

1. Notez également qu’il existe une table supplémentaire appelée **[!UICONTROL Legend]**. Si vous sortez une requête du contexte du Report Builder, il peut être difficile de se rappeler ce à quoi correspond chaque requête. Le tableau Légende a, par exemple, pour but de vous montrer le nom de chaque requête sous ID de tableau. Vous pouvez également ajouter les autres colonnes Légende pour obtenir un  complet de la requête.

   ![](assets/legend-table.png)

