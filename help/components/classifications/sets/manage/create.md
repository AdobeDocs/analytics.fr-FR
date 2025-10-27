---
title: Créer des ensembles de classifications
description: Découvrez comment accéder aux champs et descriptions disponibles lors de la création d’un ensemble de classifications.
exl-id: 6d692d90-8cc7-4306-a780-58d03db45be8
feature: Classifications
source-git-commit: 2ced7cd61c4119347be2ef0fba9b8d60ee6c4df2
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 2%

---

# Créer et modifier des ensembles de classifications

Vous [créez](#create-a-classification-set) et [modifiez](#edit-a-classification-set) des ensembles de classifications à partir du gestionnaire des ensembles de classifications.

## Créer un jeu de classifications

Pour créer un ensemble de classifications, procédez comme suit :

1. Sélectionnez **[!UICONTROL Composants]** dans la barre de menus supérieure d’Adobe Analytics, puis sélectionnez **[!UICONTROL Ensembles de classifications]**.
1. Dans **[!UICONTROL Ensembles de classifications]**, sélectionnez l’onglet **[!UICONTROL Ensembles de classifications]**.
1. Sélectionnez ![AjouterCercle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Nouveau]**.
1. Dans la boîte de dialogue **[!UICONTROL Ajouter un nouvel ensemble de classifications]** :

   ![Ensembles De Classifications - Ajoutez Un Nouvel Ensemble De Classifications](assets/classifications-sets-new.png)

   1. Saisissez un **[!UICONTROL Nom]**. Par exemple : `Classification Set Example`.
   1. Saisissez une **[!UICONTROL Description (facultatif)]**. Par exemple : `Example classification set`.
   1. Saisissez une ou plusieurs adresses e-mail (séparées par des virgules) dans **[!UICONTROL Notifier les problèmes]**. Des notifications par e-mail sont envoyées à ces utilisateurs pour les informer de problèmes éventuels.
   1. Sélectionnez le **[!UICONTROL Type]** de l’ensemble de classifications. Les types possibles sont :
      * **[!UICONTROL Principal]**. Un ensemble de classifications principal s’applique aux dimensions collectées dans Adobe Analytics. Les classifications de Principal sont un moyen de regrouper (classifier) les valeurs de dimension granulaires dans des niveaux de données plus significatifs. Par exemple, vous pouvez regrouper des mots-clés de recherche interne en catégories de recherche interne, afin de comprendre les thèmes dans vos données de recherche. Vous pouvez également classer les SKU de produit par couleur ou par catégorie.
         * Saisissez un ou plusieurs **[!UICONTROL abonnements]**.  Vous pouvez définir plusieurs combinaisons **[!UICONTROL Suite de rapports]** et **[!UICONTROL Dimension]** pour un ensemble de classifications.

         * Sélectionnez ![CrossSize400](/help/assets/icons/CrossSize400.svg) pour supprimer une combinaison **[!UICONTROL Suite de rapports]** et **[!UICONTROL Clé Dimension]**.

        Si vous ajoutez une combinaison **[!UICONTROL Suite de rapports]** et **[!UICONTROL Dimension clé]** qui existe déjà dans un autre ensemble de classifications, une alerte rouge s’affiche sous la combinaison. Vous pouvez sélectionner **[!UICONTROL Ajouter à l’existant]** pour ouvrir l’autre ensemble de classifications et [ajouter des classifications au schéma](schema.md) pour cet autre ensemble de classifications, ou modifier la dimension.
      * **[!UICONTROL Recherche]**. Généralement appelée ‘classifications enfants’ ou ‘sous-classifications’, une table de recherche est une classification d’une classification principale. Une recherche correspond à des métadonnées sur une valeur de classification, plutôt que sur la dimension d’origine. Par exemple, une dimension *Produit* peut avoir une classification principale de *Code couleur*. Une table de recherche de *nom de la couleur* peut ensuite être jointe au *code de couleur* pour expliquer chaque code de couleur.
1. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer l’ensemble de classifications. Sélectionnez **[!UICONTROL Annuler]** pour annuler la définition.
1. Pour définir le schéma de l’ensemble de classifications, sélectionnez l’ensemble de classifications que vous venez de créer dans le gestionnaire **[!UICONTROL Ensembles de classifications]** afin de [&#x200B; modifier l’ensemble de classifications](#edit-a-classification-set).


## Modifier un ensemble de classifications

Pour modifier un ensemble de classifications, procédez comme suit :

1. Sélectionnez **[!UICONTROL Composants]** dans la barre de menus supérieure d’Adobe Analytics, puis sélectionnez **[!UICONTROL Ensembles de classifications]**.
1. Dans **[!UICONTROL Ensembles de classifications]**, sélectionnez l’onglet **[!UICONTROL Ensembles de classifications]**.
1. Sélectionnez le titre de votre ensemble de classifications.
1. Dans la boîte de dialogue **[!UICONTROL Ensemble de classifications : _titre de l’ensemble de classifications_]**, vous pouvez définir les [paramètres](settings.md) et le [schéma](schema.md) de l’ensemble de classifications.
1. Une fois que vous avez terminé, sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer vos modifications. Sélectionnez **[!UICONTROL Annuler]** pour annuler.


<!--


### Schema

In the Schema tab 





You can use the Classification set manager to create a classification set.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Sets]** > **[!UICONTROL Add]**

When creating a classification set, the following fields are available.

* **[!UICONTROL Name]**: A text field used to identify the classification set. This field cannot be edited upon creation, but can be renamed later.
* **[!UICONTROL Column Name]**: The name of the first classification dimension that you want to create. This field is the dimension name used in Analysis Workspace, and the column name when exporting classification data. You can add more column names after the classification set is created.
* **[!UICONTROL Type]**: Radio buttons that indicate the type of classification.
  * **[!UICONTROL Primary]**: Apply to dimensions collected in Analytics. They are a way to group (classify) granular dimension values into more meaningful levels of data. For example, you might want to group internal search keywords into internal search categories, to better understand themes in your search data.
  * **[!UICONTROL Lookup]**: Commonly referred to as child or subclassifications, a lookup table is a classification of a primary classification. It is metadata about a classification value, rather than the original dimension. For example, the Product variable might have a primary classification of 'Color code'. A lookup table of 'Color name' could then be attached to 'Color code' to further explain what each code means.
* **[!UICONTROL Subscriptions]** The report suites and dimensions that this classification set applies to. You can add multiple report suite and dimension combinations to a classification set.

![Create a Classification set](../../assets/classification-set-create.png)

If a classification set exists for a given report suite + variable, the classification is added to the schema instead. A given report suite + variable combination cannot belong to multiple classification sets.

-->