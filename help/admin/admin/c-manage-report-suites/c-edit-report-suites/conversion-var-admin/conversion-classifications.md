---
description: Les classifications permettent de catégoriser des valeurs dans des groupes et de générer des rapports au niveau d’un groupe. Vous pouvez, par exemple, classifier toutes les campagnes de référencement payant dans une catégorie comme termes de pop music et générer des rapports sur le succès de la catégorie par rapport à des mesures de type Instances (ou clics publicitaires), ainsi que la conversion en événements de succès.
title: Classifications des conversions
feature: Classifications
exl-id: b4855000-adf3-4e3b-af36-f4803383126d
source-git-commit: 78cfb1f3c4d45fc983982a8da11b66f2b2c9ecbc
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 98%

---

# Classifications des conversions

Les classifications permettent de catégoriser des valeurs dans des groupes et de générer des rapports au niveau d’un groupe. Vous pouvez, par exemple, classifier toutes les campagnes de [!UICONTROL référencement payant] dans une catégorie comme *termes de pop music* et générer des rapports sur le succès de la catégorie par rapport à des mesures de type Instances (ou clics publicitaires), ainsi que la conversion en événements de succès. Vous pouvez ajouter jusqu’à 255 classifications à une variable.

Les classifications de conversion vous permettent de classer des variables de conversion. Une fois classé, tout rapport pouvant être généré en utilisant les données clés peut également l’être à l’aide des propriétés de données associées.

Après avoir activé les classifications, utilisez   [l’importateur de classifications](/help/components/classifications/importer/c-working-with-saint.md) pour affecter des valeurs spécifiques à la classification appropriée.

>[!WARNING]
>
>La modification d’un nom de classification peut générer des problèmes relatifs aux règles existantes créées dans le [Créateur de règles de classification](/help/components/classifications/crb/classification-rule-builder.md). Si vous renommez une classification qui comporte des règles de classification, veillez à corriger chaque règle afin qu’elle pointe vers la classification renommée.

## Descriptions des classifications de conversion

| Élément | Description |
| --- | --- |
| Nom | Nom de la classification |
| Date d’activation (Texte uniquement) | Indique si la classification de texte est une plage de dates pour les variables Campagne. |
| Options (Texte uniquement) | Crée une liste de valeurs de classification disponibles pour cette classification. Utilisez Options avec des variables de campagne afin de fournir aux utilisateurs la liste des valeurs prises en charge pour leur classification dans le Gestionnaire de campagnes. |
| Type de nombre (Numérique uniquement) | Indique le type de nombre dans la classification numérique. Les options comprennent Numérique, Pourcentage et Devise. |

## Ajout de classifications de conversion

Pour ajouter des classifications de conversion dans Admin :

1. Cliquez sur **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Sélectionnez une suite de rapports.
1. Cliquez sur **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Conversion]** > **[!UICONTROL Classifications des conversions]**.
1. Dans la liste déroulante **[!UICONTROL Choisir le type de classification]**, sélectionnez la variable qui doit contenir une classification.

   ![Infos sur l’étape](/help/admin/admin/assets/sub_class_create.png)

1. Placez le pointeur de la souris sur l’icône **[!UICONTROL Modifier la classification]**, puis sélectionnez **[!UICONTROL Ajouter une classification]**.
1. Dans le champ **[!UICONTROL Sélectionner un type]**, choisissez le type de classification à ajouter à la variable.

   Les options comprennent **[!UICONTROL Texte]** et **[!UICONTROL Numérique]**. Pour plus d’informations sur les types de classification, voir [À propos des classifications](/help/components/classifications/c-classifications.md).
1. Dans la boîte de dialogue **[!UICONTROL Classifications de texte]**, configurez la classification selon vos besoins.

1. Ajoutez ou supprimez des options dans la boîte de dialogue de liste déroulante.

   L’ajout d’options crée une liste de valeurs de classification disponibles pour cette classification. Vous pouvez utiliser cette option avec des variables de campagne afin de fournir aux utilisateurs la liste des valeurs prises en charge pour leur classification dans le gestionnaire de campagnes. Utilisez cette option pour les dimensions des classifications pour lesquelles vous avez un faible nombre de valeurs autorisées qui ne changent jamais ou rarement. Par exemple, vous pouvez exécuter différentes campagnes visant différents niveaux de fidélité des clients : Argent, Or et Platine. Vous pouvez alors utiliser la liste déroulante pour garantir que les seules valeurs qui sont acceptées sont celles qui correspondent aux trois niveaux. Si un utilisateur tente d’utiliser une valeur différente, elle est ignorée.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

## Suppression d’une classification de conversion

Vous pouvez supprimer une classification de conversion devenue inutile.

1. Ouvrez le Gestionnaire de Report Suites en cliquant sur **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** dans l’en-tête de la suite.
1. Sélectionnez une suite de rapports.
1. Cliquez sur **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Conversion]** > **[!UICONTROL Classifications des conversions]**.
1. Dans la liste déroulante **[!UICONTROL Choisir le type de classification]**, sélectionnez la variable dans laquelle vous souhaitez supprimer une classification.
1. Placez le pointeur de la souris sur l’icône **[!UICONTROL Modifier une classification]**, puis sélectionnez **[!UICONTROL Supprimer la classification]**.
1. Dans la boîte de dialogue Supprimer la classification, cliquez sur **[!UICONTROL Supprimer]**.
