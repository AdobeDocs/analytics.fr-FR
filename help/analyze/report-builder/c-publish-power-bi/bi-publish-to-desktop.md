---
description: Explique comment extraire des ressources publiées du Créateur de rapports dans Power BI Desktop
seo-description: Explique comment extraire des ressources publiées du Créateur de rapports dans Power BI Desktop
seo-title: Extraction des éléments publiés dans Power BI Desktop
title: Extraction des éléments publiés dans Power BI Desktop
uuid: ef47d5c7-31e0-44fc-a792-bc9d12bb089e
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Extraction des éléments publiés dans Power BI Desktop

Explique comment extraire des ressources publiées du Créateur de rapports dans Power BI Desktop

## Conditions préalables {#section_BDFDAE1E300B429FB6EBCB21AD1383A0}

* Vous devez avoir installé la version la plus récente de Power BI Desktop (version d’avril 2017)
* Ce processus suppose que vous avez déjà publié des tableaux ou des requêtes au format du Créateur de rapports sur le service Power BI.

## Processus {#section_CB03E6E1B066457EA0F6FC08FFF5EFDD}

Dans la mise à jour d’avril 2017 de Power BI Desktop, Microsoft a introduit la possibilité de se connecter à des jeux de données dans le service Power BI. Cette fonctionnalité vous permet de créer de nouveaux rapports à partir de jeux de données existants que vous avez déjà publiés sur le cloud. Vous pouvez tirer parti de cette fonctionnalité pour améliorer la collaboration et réduire le chevauchement des tâches au sein de votre équipe.

1. In Power BI Desktop, go to **[!UICONTROL File]** &gt; **[!UICONTROL Options and settings]** &gt; **[!UICONTROL Options]** &gt; **[!UICONTROL Preview features.]**
1. Activez l’option **[!UICONTROL Connexion active du service Power BI]** et cliquez sur **[!UICONTROL OK]**. ![](assets/bi-preview-features.png)

1. Redémarrez Power BI Desktop.
1. **[!UICONTROL Après avoir redémarré le bureau, accédez à]** Accueil **[!UICONTROL &gt;]** Obtenir des données **[!UICONTROL &gt;]** Plus... .
1. Recherchez et sélectionnez **[!UICONTROL Service Power BI]**.
1. Under **[!UICONTROL Microsoft Power BI service]** &gt; **[!UICONTROL My Workspace]**, select the dataset that you had previously published from Report Builder.

Pour plus d’informations, voir ce [billet de blog de Microsoft](https://powerbi.microsoft.com/en-us/blog/connecting-to-datasets-in-the-power-bi-service-from-desktop/).
