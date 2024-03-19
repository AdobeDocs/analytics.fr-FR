---
description: Explique comment extraire des ressources publiées du Report Builder dans Power BI Desktop
title: Extraction des éléments publiés dans Power BI Desktop
feature: Report Builder
role: User, Admin
exl-id: ce6020df-caf4-4cd2-8086-4357309e5bbb
source-git-commit: fb39f906d6c08713e4dc8211c917b2942502868e
workflow-type: ht
source-wordcount: '206'
ht-degree: 100%

---

# Extraction des éléments publiés dans Power BI Desktop

Explique comment extraire des ressources publiées du Report Builder dans Power BI Desktop

## Conditions préalables {#section_BDFDAE1E300B429FB6EBCB21AD1383A0}

* Vous devez avoir installé la version la plus récente de Power BI Desktop (version d’avril 2017)
* Ce processus suppose que vous avez déjà publié des tableaux ou des requêtes au format du Report Builder sur le service Power BI.

## Processus {#section_CB03E6E1B066457EA0F6FC08FFF5EFDD}

Dans la mise à jour d’avril 2017 de Power BI Desktop, Microsoft a introduit la possibilité de se connecter à des jeux de données dans le service Power BI. Cette fonctionnalité vous permet de créer de nouveaux rapports à partir de jeux de données existants que vous avez déjà publiés sur le cloud. Vous pouvez tirer parti de cette fonctionnalité pour améliorer la collaboration et réduire le chevauchement des tâches au sein de votre équipe.

1. Dans Power BI Desktop, sélectionnez **[!UICONTROL Fichier]** > **[!UICONTROL Options et paramètres]** > **[!UICONTROL Options]** > **[!UICONTROL Fonctionnalités en préversion.]**
1. Activez l’option **[!UICONTROL Connexion active du service Power BI]** et cliquez sur **[!UICONTROL OK]**. ![Cliquez sur Connexion active du service Power BI, puis sur OK. ](assets/bi-preview-features.png)

1. Redémarrez Power BI Desktop.
1. Une fois que le desktop est redémarré, sélectionnez **[!UICONTROL Accueil]** > **[!UICONTROL Obtenir des données]** > **[!UICONTROL Plus...]**.
1. Recherchez et sélectionnez **[!UICONTROL Service Power BI]**.
1. En dessous de l’option **[!UICONTROL Service Microsoft Power BI]** > **[!UICONTROL Mon espace de travail]**, sélectionnez le jeu de données que vous avez précédemment publié à partir du Report Builder.

Pour plus d’informations, voir cet [article de blog de Microsoft](https://powerbi.microsoft.com/en-us/blog/connecting-to-datasets-in-the-power-bi-service-from-desktop/).
