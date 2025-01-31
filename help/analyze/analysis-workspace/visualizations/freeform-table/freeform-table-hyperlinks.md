---
title: Création de liens hypertexte dans un tableau à structure libre dans Analysis Workspace
description: Découvrez comment créer des liens hypertexte pour les éléments de dimension dans un tableau à structure libre dans Analysis Workspace
feature: Freeform Tables
role: User, Admin
exl-id: df846a73-e3e3-4376-844e-48153a20e5d6
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '1739'
ht-degree: 1%

---

# Créer des hyperliens pour les dimensions dans un tableau à structure libre

Vous pouvez créer des liens hypertexte pour les éléments de dimension afin de pouvoir les cliquer dans un tableau à structure libre d’Analysis Workspace.

Cette fonctionnalité est particulièrement utile lors de la création de liens hypertexte pour les types d’éléments de dimension suivants :

* Éléments de Dimension dont les valeurs URL correspondent à des liens que vous souhaitez créer (par exemple, une dimension URL de page )

* Éléments de Dimension qui contiennent des répartitions ayant des valeurs d’URL vers lesquelles vous souhaitez créer un lien (par exemple, une dimension Nom de page qui comporte une répartition d’une dimension URL de page)

* Éléments de Dimension ou répartitions dont les valeurs font partie d’une URL vers laquelle vous souhaitez créer un lien (par exemple, une dimension Nom de page qui fait partie d’une URL)


>[!BEGINSHADEBOX]

Consultez ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Hyperlinks pour la dimension](https://video.tv.adobe.com/v/3430411?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]





## Créer des liens hypertexte pour un ou plusieurs éléments de dimension

Tenez compte des points suivants lors de la création de liens hypertexte pour les éléments de dimension :

* Les liens hypertexte créés sont stockés dans le tableau à structure libre du projet Analysis Workspace. Les liens hypertexte ne sont pas conservés lorsque vous utilisez la même dimension ou les mêmes éléments de dimension dans un autre tableau ou dans un autre projet.

* Si vous modifiez la vue de données du tableau à structure libre, tous les liens hypertexte créés pour les dimensions ou les éléments de dimension dans le tableau restent disponibles, à condition que la dimension existe dans la vue de données.

* La validité des URL n’est pas vérifiée lors de la création du lien hypertexte.

  Si vous créez un lien hypertexte avec une URL non valide ou un lien hypertexte qui fait référence à un élément de dimension sans valeur d’URL (en référençant directement l’élément de dimension ou en utilisant les variables `$value` ou `$breakdown`), un message d’erreur s’affiche pour les utilisateurs qui cliquent sur le lien hypertexte indiquant que l’URL n’est pas valide.

* Les liens hypertexte créés pour un seul élément de dimension remplacent les liens hypertexte créés sur la dimension.

* Les liens hypertexte ne sont pas fonctionnels dans les [fichiers de PDF téléchargés](/help/analyze/analysis-workspace/curate-share/download-send.md).

Pour créer des liens hypertexte pour un ou plusieurs éléments de dimension :

1. Dans un tableau à structure libre d’Analysis Workspace, effectuez l’une des opérations suivantes :

   * **Créer un lien hypertexte pour un seul élément de dimension :** cliquez avec le bouton droit sur l’élément de dimension dans le tableau pour lequel vous souhaitez créer le lien hypertexte, puis sélectionnez [!UICONTROL **Créer un lien hypertexte**].

     ![Créer un lien hypertexte pour un seul élément de dimension](assets/hyperlink-single-add.png)

     La boîte de dialogue [!UICONTROL **Créer un lien hypertexte**] s’affiche. Le nom de l’élément de dimension pour lequel vous créez un lien hypertexte s’affiche dans la boîte de dialogue.

     ![Créer un lien hypertexte pour une boîte de dialogue à un seul élément](assets/hyperlink-dialog-single.png)

   * **Créer des liens hypertexte pour tous les éléments de dimension d’une colonne de dimension :** cliquez avec le bouton droit sur le nom de la dimension dans l’en-tête de colonne de dimension, puis sélectionnez [!UICONTROL **Créer des liens hypertexte pour tous les éléments de dimension**].

     ![Créer un lien hypertexte pour une dimension](assets/hyperlink-multiple-add.png)

     La boîte de dialogue [!UICONTROL **Créer des liens hypertexte pour tous les éléments de dimension**] s’affiche. Le nom de la dimension pour laquelle vous créez des liens hypertexte s’affiche dans la boîte de dialogue.

     ![Boîte de dialogue Créer des liens hypertexte](assets/hyperlink-dialog-multiple.png)

1. Choisissez l’une des options suivantes :

   * [!UICONTROL **Utiliser la valeur de l’élément de dimension comme URL**] : sélectionnez cette option pour les éléments de dimension comportant des valeurs d’URL, tels qu’une dimension URL de page .

     Par exemple, si vous utilisez une dimension URL de la page où la valeur de chaque élément de dimension est une URL, la sélection de cette option crée un lien hypertexte vers l’URL.

   * [!UICONTROL **Créer une URL personnalisée**] : spécifiez une URL personnalisée statique ou dynamique. Sélectionnez cette option pour créer des liens hypertexte pour les éléments de dimension qui ne possèdent pas de valeurs d’URL.

     Par exemple, si vous utilisez une dimension Nom de page où la valeur de chaque élément de dimension correspond au nom d’une page (et non à une URL complète), en sélectionnant cette option, vous pouvez spécifier un lien hypertexte à utiliser comme lien pour l’élément de dimension.

     Si vous souhaitez créer des URL dynamiques pour plusieurs éléments de dimension, vous pouvez utiliser les variables `$value` et `$breakdown` dans votre URL personnalisée. Pour plus d’informations, consultez le tableau ci-dessous.

     Pour créer une URL personnalisée, spécifiez les informations suivantes :

     | Champ | Description |
     |---------|----------|
     | [!UICONTROL **URL personnalisée**] | Spécifiez une URL personnalisée que vous souhaitez utiliser pour le lien hypertexte. Les URL doivent être saisies en tant qu’URL complètes. Par exemple : https://www.example.com<p>L’URL personnalisée que vous créez peut être statique ou dynamique :</p> <ul><li>**URL statiques :** si vous créez un lien hypertexte pour un élément de dimension individuel, une URL statique peut être suffisante. <p>Prenons l’exemple suivant : par exemple, si vous disposez d’un élément de dimension Nom de page , vous pouvez créer une URL statique qui lie les utilisateurs à la page web spécifique que vous souhaitez associer au nom de la page.</p><p>Supposons que vous souhaitiez créer des liens hypertexte pour une liste d’éléments de dimension, chacun d’eux étant lié à sa définition respective dans la documentation d’une page wiki interne.</p><p>Pour ce faire, créez une URL statique pour chaque élément de dimension. Par exemple :</p><p>https://wiki.internal.company_name/page_name#item_definition</p></li><li>**URL dynamiques :** si vous créez un lien hypertexte pour plusieurs éléments de dimension ou pour tous les éléments de dimension d’une colonne de dimension, une URL dynamique est probablement plus pratique. <p>Pour rendre les URL personnalisées dynamiques, vous incluez dans l’URL des variables qui permettent à l’URL de changer dynamiquement en fonction de la valeur de la dimension elle-même ou de la valeur de la dimension de répartition.</p><p>Lors de l’utilisation de variables, tous les éléments de dimension contenant des caractères non valides dans les URL (tels que des espaces) sont encodés en URL.</p><p>Les variables suivantes sont disponibles : (**Remarque** : bien que vous puissiez utiliser ces variables dans la même URL, il est probablement plus courant de les utiliser séparément.)</p> <ul><li>**`$value`:** permet d’insérer la valeur de l’élément de dimension dans l’URL que vous spécifiez. <p>Prenons le scénario suivant comme exemple :</p><p>Supposons que vous souhaitiez créer des liens hypertexte pour tous les éléments de dimension Nom de page dans un tableau à structure libre, où la valeur de chaque élément de dimension fait partie de l’URL d’une page web. Dans ce cas, vous pouvez construire une seule URL personnalisée qui s’ajuste dynamiquement pour chaque élément de dimension. </p><p>Pour ce faire, ajoutez la variable `$value` à la fin de l’URL personnalisée que vous spécifiez. Par exemple :</p> <p>https://company-name.com/browse/product#$value</p><p>Lorsque cette URL personnalisée est appliquée à vos éléments de dimension Nom de page dont les valeurs sont « ProductY » et « ProductZ », les liens hypertexte générés se présentent comme suit : </p><p>https://company-name.com/browse/product#ProductY</p><p>et</p><p> https://company-name.com/browse/product#ProductZ </p><p>![utiliser des valeurs dans les liens hypertexte](assets/table-hyperlinks-vaule.png)</p><p>**Conseil** : si vous deviez ajouter uniquement la variable `$value` dans le champ URL personnalisée, cela équivaudrait à sélectionner l’option [!UICONTROL **Utiliser la valeur de l’élément de dimension**] lors de la création de l’URL.</p></li><li>**`$breakdown`:** permet d’insérer la valeur de l’élément de dimension de répartition dans l’URL que vous spécifiez. Cela vous permet d’utiliser une dimension avec un nom convivial dans votre rapport (comme une dimension Nom du produit) lors de la création de l’hyperlien en fonction d’une dimension de répartition qui peut être moins conviviale (comme une dimension ID de produit ou URL de page).<p>Lors du référencement d’une dimension de répartition, il est courant de n’avoir qu’un seul élément de répartition pour un élément de dimension donné. S’il existe plusieurs éléments de répartition pour un élément de dimension donné, la valeur du premier élément de répartition est utilisée dans l’URL. Si aucun élément de répartition n’est répertorié, l’URL n’est pas valide. L’ordre de tri appliqué aux éléments de répartition est le même que celui appliqué au tableau.</p><p>Vous spécifiez la dimension de répartition dans le champ [!UICONTROL **Dimension de répartition**] ci-dessous.</p> <p>Examinons l’exemple de scénario décrit pour le champ [!UICONTROL **Dimension de répartition**] ci-dessous.</p></li></ul> |
     | [!UICONTROL **Dimension Répartition (facultatif)**] | Commencez à saisir le nom de la dimension de répartition à utiliser, puis sélectionnez-la dans la liste déroulante. <p>Si vous sélectionnez une dimension de répartition dans ce champ, vous devez la référencer à l’aide de la variable `$breakdown` dans l’URL que vous spécifiez dans le champ [!UICONTROL **URL personnalisée**].</p><p>Prenons le scénario suivant comme exemple :</p><p>Supposons que vous souhaitiez créer des liens hypertexte pour tous les éléments de dimension Nom du produit dans un tableau à structure libre. Chaque élément de dimension Nom du produit contient une répartition d’une dimension ID de produit .</p></p>Dans ce cas, vous pouvez créer des liens hypertexte pour chaque dimension Nom du produit qui dirige les utilisateurs vers la page du produit à l’aide de la valeur de la dimension de répartition ID de produit . </p><p>Pour ce faire, ajoutez la variable `$breakdown` à la fin de l’URL personnalisée que vous spécifiez dans le champ [!UICONTROL **URL personnalisée**]. Par exemple :</p><p>https://company-name.com/browse/product/$breakdown</p><p>Lorsque cette URL personnalisée est appliquée aux éléments de dimension Nom du produit qui comportent des éléments de dimension de répartition dont les valeurs sont « ProductY » et « ProductZ », les liens hypertexte générés ressembleraient à ceci :</p><p>https://company-name.com/browse/product/ProductY</p><p>et</p><p>https://company-name.com/browse/product/ProductZ</p><p>Sélectionnez ensuite la dimension ID du produit dans le champ [!UICONTROL **Dimension de répartition**] </p><p>![utiliser les répartitions dans les liens hypertexte](assets/table-hyperlinks-breakdown.png)</p> |

1. Sélectionnez [!UICONTROL **Créer**].

   Les utilisateurs qui consultent le tableau à structure libre voient les éléments de dimension liés par un lien hypertexte. Lorsque les utilisateurs cliquent sur un élément de dimension, ils sont redirigés vers les pages contenant des liens hypertexte dans un onglet de navigateur distinct.

   <!-- add screenshot of a table with hyperlinks.-->

1. [Enregistrez le projet](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md) pour enregistrer vos modifications.

## Modification des liens hypertexte

Vous pouvez modifier les liens hypertexte qui ont été créés sur des dimensions ou des éléments de dimension dans un tableau à structure libre.

1. Dans un tableau à structure libre d’Analysis Workspace, effectuez l’une des opérations suivantes :

   * **Modifier un lien hypertexte pour un seul élément de dimension :** cliquez avec le bouton droit sur l’élément de dimension dans le tableau où vous souhaitez modifier le lien hypertexte.

     ![Modifier le lien hypertexte d’un seul élément de dimension](assets/hyperlink-single-edit.png)

   * **Modifier les liens hypertexte pour tous les éléments de dimension d’une colonne de dimension :** cliquez avec le bouton droit sur le nom de la dimension dans l’en-tête de la colonne de dimension.

     ![Modifier le lien hypertexte d’une dimension](assets/hyperlink-dimension-edit.png)

1. Sélectionnez [!UICONTROL **Modifier le lien hypertexte**] dans le menu contextuel.

   La boîte de dialogue [!UICONTROL **Modifier les liens hypertexte des éléments de dimension**] s’affiche.

1. Pour plus d’informations sur les options de configuration de la modification du lien hypertexte, reportez-vous à l’étape 3 de la section [Créer des liens hypertexte pour un ou plusieurs éléments de dimension](#create-hyperlinks-for-one-or-more-dimension-items) ci-dessus, puis sélectionnez [!UICONTROL **Appliquer**] lorsque vous avez terminé vos mises à jour.

1. [Enregistrez le projet](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md) pour enregistrer vos modifications.

## Supprimer les liens hypertexte

Vous pouvez supprimer des liens hypertexte créés pour des éléments de dimension dans un tableau à structure libre.

>[!NOTE]
>
>Dans un tableau à structure libre, si vous supprimez une dimension contenant des liens hypertexte, ces derniers ne sont pas conservés si vous rajoutez la même dimension au tableau à structure libre.

Pour supprimer des liens hypertexte d’éléments de dimension :

1. Dans un tableau à structure libre d’Analysis Workspace, effectuez l’une des opérations suivantes :

   * **Supprimer un lien hypertexte d’un seul élément de dimension :** cliquez avec le bouton droit sur l’élément de dimension dans le tableau où vous souhaitez supprimer le lien hypertexte.

     ![Supprimer le lien hypertexte d’un seul élément de dimension](assets/hyperlink-single-remove.png)

   * **Supprimer les liens hypertexte de tous les éléments de dimension dans une colonne de dimension :** cliquez avec le bouton droit sur le nom de la dimension dans l’en-tête de colonne de dimension.

     ![Supprimer un lien hypertexte d’une dimension](assets/hyperlink-dimension-remove.png)

1. Sélectionnez [!UICONTROL **Supprimer le lien hypertexte**] dans le menu contextuel.

   Le lien hypertexte est supprimé de l’élément de dimension unique (si vous avez sélectionné un seul élément de dimension) ou de tous les éléments de dimension (si vous avez sélectionné le nom de la dimension dans l’en-tête de colonne de dimension).

1. [Enregistrez le projet](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md) pour enregistrer vos modifications.
