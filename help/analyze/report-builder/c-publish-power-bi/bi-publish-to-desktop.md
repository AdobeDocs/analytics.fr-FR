---
description: Explique comment extraire des ressources publiées du Créateur de rapports dans Power BI Desktop
seo-description: Explique comment extraire des ressources publiées du Créateur de rapports dans Power BI Desktop
seo-title: Extraire les fichiers publiés dans Power BI Desktop
title: Extraire les fichiers publiés dans Power BI Desktop
uuid: ef 47 d 5 c 7-31 e 0-44 fc-a 792-bc 9 d 12 bb 089 e
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Extraire les fichiers publiés dans Power BI Desktop

Explique comment extraire des ressources publiées du Créateur de rapports dans Power BI Desktop

## Conditions préalables {#section_BDFDAE1E300B429FB6EBCB21AD1383A0}

* Vous devez avoir installé la version la plus récente de Power BI Desktop (version d’avril 2017)
* Ce processus suppose que vous avez déjà publié des tableaux ou des requêtes au format du Créateur de rapports sur le service Power BI.

## Processus {#section_CB03E6E1B066457EA0F6FC08FFF5EFDD}

Dans la mise à jour d’avril 2017 de Power BI Desktop, Microsoft a introduit la possibilité de se connecter à des jeux de données dans le service Power BI. Cette fonctionnalité vous permet de créer de nouveaux rapports à partir de jeux de données existants que vous avez déjà publiés sur le cloud. Vous pouvez tirer parti de cette fonctionnalité pour améliorer la collaboration et réduire le chevauchement des tâches au sein de votre équipe.

1. In Power BI Desktop, go to **[!UICONTROL File]** &gt; **[!UICONTROL Options and settings]** &gt; **[!UICONTROL Options]** &gt; **[!UICONTROL Preview features.]**
1. Activez l’option **[!UICONTROL Connexion active du service Power BI]** et cliquez sur **[!UICONTROL OK]**. ![](assets/bi-preview-features.png)

1. Redémarrez Power BI Desktop.
1. Once you have restarted the desktop, go to **[!UICONTROL Home]** &gt; **[!UICONTROL Get Data]** &gt; **[!UICONTROL More...]**.
1. Recherchez et sélectionnez **[!UICONTROL Service Power BI]**.
1. Under **[!UICONTROL Microsoft Power BI service]** &gt; **[!UICONTROL My Workspace]**, select the dataset that you had previously published from Report Builder.

Pour plus d’informations, voir ce [billet de blog de Microsoft](https://powerbi.microsoft.com/en-us/blog/connecting-to-datasets-in-the-power-bi-service-from-desktop/).
