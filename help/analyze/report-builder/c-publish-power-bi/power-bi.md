---
description: valeur nulle
title: Publication sur Power BI - Aperçu
uuid: ad688817-6e3c-45da-983d-48c123465309
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Publication sur Power BI - Aperçu

Microsoft Power BI est une suite de tableaux de bord d’analyse commerciale permettant d’analyser les données et de partager les informations. L’intégration d’Adobe Analytics à Power BI vous permet de visualiser les données d’analyse du Report Builder sur Microsoft Power BI et de les partager facilement avec l’ensemble de votre entreprise.

Auparavant, en tant qu’analyste, vous deviez planifier la diffusion des classeurs du Report Builder par courrier électronique (ou ftp). Vous pouvez désormais permettre à vos utilisateurs et intervenants métier d’accéder (depuis leur compte Power BI) à des données exactes et à jour dans un environnement Web qui est accessible quels que soient les plateformes et les périphériques utilisés.

L’association de la fonctionnalité de génération de rapports du Report Builder aux fonctionnalités de visualisation de Power BI rend les informations plus accessibles pour tous les membres de l’organisation. Grâce à Power BI, vous pouvez également intégrer Adobe Analytics à d’autres sources de données (par exemple, point de vente, gestion de la relation client) de façon à découvrir des statistiques sur les clients, des associations et des opportunités uniques.

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

1. Indiquez votre adresse électronique et envoyez immédiatement, ou définissez la fréquence de planification (par heure, quotidiennement, etc.).
1. Click **[!UICONTROL OK]** to publish.
1. Vous devrez alors vous connecter à votre compte Microsoft. Indiquez vos informations d’identification.
1. Le classeur du Report Builder est planifié et publié sur Power BI.

   À chaque instance planifiée, et après que le processus de planification du Report Builder a actualisé le classeur avec les données d’analyse mises à jour, le classeur sera publié sur Microsoft Power BI.

**Afficher les données du classeur du Report Builder dans Power BI**

1. In Power BI, double click the workbook under the [!UICONTROL Workbooks] menu.

   ![](assets/workbooks-power-bi.png)

1. Vous pouvez désormais visualiser les données de tableau de bord du classeur.  ![](assets/view-data-pbi.png)

1. Vous pouvez ensuite épingler une zone de ce classeur de façon à l’inclure dans l’un de vos tableaux de bord Power BI.

## Publier tous les tableaux formatés du classeur en tant que tableaux de jeu de données Power BI {#section_7C54A54E75184DD6BAEF4ACCE241239A}

>[!NOTE] Si le classeur contient une macro, l’option « Publier tous les tableaux formatés du classeur en tant que tableaux de jeu de données Power BI » sera désactivée.

Au lieu d’importer l’ensemble du classeur, vous pouvez n’importer que le contenu de l’ensemble des tableaux formatés de ce classeur.

**Cas d’utilisation** : Vous avez un classeur Excel qui extrait des données à partir de plusieurs requêtes du Report Builder et crée un tableau récapitulatif avec de nombreuses formules. Vous pouvez n’importer que le tableau récapitulatif dans Power BI et créer une visualisation pour ce tableau.

**Publier un tableau formaté dans le Report Builder**

1. Dans le Report Builder, générez un tableau de données comprenant une ligne d’en-tête, suivie d’une ligne de données.
1. Sélectionnez le tableau et sélectionnez-le **[!UICONTROL Format as Table]** dans le [!UICONTROL Home] menu. The table gets named by default (Table 1, Table 2, etc.), but you can change the name on the [!UICONTROL Design]menu.

1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]** > **[!UICONTROL New]**.

1. Dans l&#39;Assistant Planification de base, cliquez sur **[!UICONTROL Advanced Scheduling Options]**.
1. Dans le [!UICONTROL Scheduling Wizard - Advanced]panneau **[!UICONTROL Publishing Options]** , cochez la case en regard de **[!UICONTROL Publish all Formatted Tables as Power BI dataset tables]**.

   ![](assets/advanced-schedule-wizard2.png)

1. (Facultatif) Vous pouvez personnaliser le nom de la ressource publiée dans Power BI. Cela peut être utile si vous utilisez le contrôle de version dans le nom du classeur (par exemple, monclasseur_v1.1.xlsx) et que vous ne souhaitez pas que le numéro de version figure dans le nom de la ressource Power BI publiée. Un autre avantage est que la ressource publiée ne changera pas si le numéro de version change. (Affichez les [spécifications](/help/analyze/report-builder/c-publish-power-bi/specifications-limits.md) ici.)

**Visualiser les données de tableau dans Power BI**

1. In Power BI, go to the **[!UICONTROL Workspaces]** > **[!UICONTROL Datasets]** menu.

   ![](assets/datasets-menu.png)

1. Select the dataset that you published and click the [!UICONTROL Create report] icon next to it. Notez que les tableaux s’affichent en tant que Champs.

   ![](assets/formatted-tables.png)

1. Sélectionnez un tableau et ses colonnes associées.

   ![](assets/view-table-dataset.png)

1. From the [!UICONTROL Visualizations] menu, you can select how to visualize a table in Power BI. Par exemple, vous pouvez choisir de présenter vos données sous forme d’un graphique linéaire :

   ![](assets/bi-line-graph.png)

1. À partir de là, vous pouvez créer des visualisations à partir de ce tableau de jeu de données.

## Publier toutes les requêtes du Report Builder sous forme de tableaux de jeu de données Power BI {#section_0C26057C7DBB4068A643FDD688F6E463}

Vous pouvez transformer toutes vos requêtes en tableaux de jeu de données et générer des visualisations à partir de ces tableaux.

>[!IMPORTANT]
>
>Si le classeur contient plus de 100 requêtes, seules les 100 premières requêtes seront publiées sur Power BI. Par ailleurs, pour chaque requête publiée sur Power BI, seules les 10 000 premières lignes de données seront publiées. Par conséquent, bien que ces requêtes soient distribuées correctement à travers la planification, la portée de la publication sur Power BI est limitée.

1. Dans le Report Builder, ouvrez ou créez un classeur avec des requêtes du Report Builder.
1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]** > **[!UICONTROL New]**.

1. Dans l&#39;Assistant Planification de base, cliquez sur **[!UICONTROL Advanced Scheduling Options]**.
1. Dans le [!UICONTROL Scheduling Wizard - Advanced]panneau **[!UICONTROL Publishing Options]** , cochez la case en regard de **[!UICONTROL Publish all Report Builder Requests as Power BI Dataset Tables]**![](assets/advanced-schedule-wizard2.png)

1. Cliquez sur **[!UICONTROL OK]**.

**Visualiser les données de requête dans Power BI**

Chaque requête du Report Builder planifiée sera publiée en tant que tableau dans le jeu de données. Each request table is named after the primary dimension in the request and it has a [!UICONTROL Report Suite] and a [!UICONTROL Segments] column.

1. In Power BI, go to the **[!UICONTROL Workspaces]** > **[!UICONTROL Datasets]** menu.

1. Sélectionnez la requête que vous avez publiée et cliquez sur l’icône [!UICONTROL Create report] située juste à côté.

   Notice that the requests appear as tables in the [!UICONTROL Fields] menu.

   ![](assets/published-requests.png)

   >[!NOTE]
   >
   >Quelle que soit la façon dont vous avez configuré la présentation de votre requête du Report Builder dans le classeur (disposition croisée dynamique, disposition personnalisée, certaines colonnes invisibles), le Report Builder publie toujours votre requête selon le même format bidimensionnel à une seule ligne d’en-tête : Date, Dimensions, Mesures, Suites de rapports, Segments.

1. Also notice that there is an additional table called **[!UICONTROL Legend]**. Si vous sortez une requête du contexte du Report Builder, il peut être difficile de se rappeler ce à quoi correspond chaque requête. Le tableau Légende a pour fonction, par exemple, d’afficher le nom de chaque requête sous Identifiant du tableau. Vous pouvez également ajouter les autres colonnes de Légende pour obtenir un aperçu global de la requête.

   ![](assets/legend-table.png)

