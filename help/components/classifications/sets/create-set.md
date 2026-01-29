---
title: Créer des ensembles de classifications
description: Découvrez comment accéder aux champs et descriptions disponibles lors de la création d’un ensemble de classifications.
exl-id: 6d692d90-8cc7-4306-a780-58d03db45be8
feature: Classifications
source-git-commit: 993bef6137bbcda98cb6f09f9e8644db44e7d8cb
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 3%

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

        Si vous ajoutez une combinaison **[!UICONTROL Suite de rapports]** et **[!UICONTROL Dimension clé]** qui existe déjà dans un autre ensemble de classifications, un message de couleur rouge s’affiche.
Vous pouvez :
         * Sélectionnez **[!UICONTROL Ajouter à l’existant]** pour ouvrir l’autre ensemble de classifications et [ajouter des classifications au schéma](manage/schema.md) pour cet autre ensemble de classifications.
         * Remplacez **[!UICONTROL Suite de rapports]** et **[!UICONTROL Dimension clé]** par une combinaison qui n’est pas déjà abonnée à un autre ensemble de classifications.
      * **[!UICONTROL Recherche]**. Généralement appelée ‘classifications enfants’ ou ‘sous-classifications’, une table de recherche est une classification d’une classification principale. Une recherche correspond à des métadonnées sur une valeur de classification, plutôt que sur la dimension d’origine. Par exemple, une dimension *Produit* peut avoir une classification principale de *Code couleur*. Une table de recherche de *nom de la couleur* peut ensuite être jointe au *code de couleur* pour expliquer chaque code de couleur.
1. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer l’ensemble de classifications. Sélectionnez **[!UICONTROL Annuler]** pour annuler la définition.
1. Pour définir le schéma de l’ensemble de classifications, sélectionnez l’ensemble de classifications que vous venez de créer dans le gestionnaire **[!UICONTROL Ensembles de classifications]** afin de [ modifier l’ensemble de classifications](#edit-a-classification-set).


## Modifier un ensemble de classifications

Pour modifier un ensemble de classifications, procédez comme suit :

1. Sélectionnez **[!UICONTROL Composants]** dans la barre de menus supérieure d’Adobe Analytics, puis sélectionnez **[!UICONTROL Ensembles de classifications]**.
1. Dans **[!UICONTROL Ensembles de classifications]**, sélectionnez l’onglet **[!UICONTROL Ensembles de classifications]**.
1. Sélectionnez le nom de votre ensemble de classifications.
1. Dans la boîte de dialogue **[!UICONTROL Ensemble de classifications : _nom de l’ensemble de classifications_]**, vous pouvez définir les [paramètres](manage/settings.md) et le [schéma](manage/schema.md) de l’ensemble de classifications.
1. Une fois que vous avez terminé, sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer vos modifications. Sélectionnez **[!UICONTROL Annuler]** pour annuler.
