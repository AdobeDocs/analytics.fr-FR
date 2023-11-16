---
description: Documentation décrivant comment filtrer et trier les tableaux dans Analysis Workspace.
title: Filtrage et tri des tableaux à structure libre
feature: Freeform Tables
role: User, Admin
exl-id: 15fea9e2-f8d8-4489-9a44-e74a351b8f36
source-git-commit: e5f67042fce223f2998e4031962193b1c0154557
workflow-type: tm+mt
source-wordcount: '938'
ht-degree: 68%

---

# Filtrage et tri des tableaux à structure libre

Les tableaux à structure libre dans Analysis Workspace sont la base de l’analyse de données interactive. Ils peuvent donc contenir des milliers de lignes d’informations. Le filtrage et le tri des données peuvent constituer des éléments essentiels à l’amélioration de l’affichage des informations les plus importantes.

## Filtrer des tableaux

Les filtres dans Analysis Workspace vous aident à afficher les informations les plus importantes.

>[!NOTE]
>
> Seuls les éléments de dimension dynamiques peuvent être filtrés comme décrit dans cette section. Les éléments de dimension statiques ne peuvent pas être filtrés. Pour plus d’informations, voir [Éléments de dimension dynamiques ou statiques dans les tableaux à structure libre](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).

## Filtrage des lignes de tableau à structure libre

Vous pouvez utiliser plusieurs méthodes pour filtrer les lignes d’un tableau à structure libre. 

- Cliquez sur le X dans la ligne
- Clic droit > Lignes sélectionnées supprimées
- Filtres de tableau
- Segmentation

Veillez à lire l’impact de chaque méthode [Totaux des tableaux à structure libre](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/build-workspace-project/workspace-totals.html).

### Exclusion rapide de lignes spécifiques d’un tableau

Vous pouvez exclure rapidement des lignes spécifiques du tableau sans avoir à ouvrir la boîte de dialogue Filtrer .

>[!NOTE]
>
>Lorsque vous excluez des lignes comme décrit dans cette section, une [!UICONTROL **Toujours exclure les éléments**] est automatiquement appliquée dans la boîte de dialogue de filtrage avancé. (Vous pouvez afficher la règle appliquée en cliquant sur l’icône Filtrer , puis [**[!UICONTROL Afficher les paramètres avancés]**](#apply-a-simple-or-advanced-filter-to-a-table).)

Pour exclure rapidement des lignes spécifiques d’un tableau à structure libre :

1. Pointez sur la ligne à exclure, puis sélectionnez l’icône x.

   Maintenez la touche Maj enfoncée pour sélectionner une plage de lignes ou maintenez la touche Commande (sur Mac) ou la touche Ctrl (sous Windows) enfoncée pour sélectionner plusieurs lignes.

### Clic droit > Supprimer les lignes sélectionnées

1. Sélectionnez une ou plusieurs lignes.
1. Cliquez avec le bouton droit et sélectionnez **[!UICONTROL Supprimer les lignes sélectionnées]**.

   Cette action supprime les lignes du tableau et applique un filtre de tableau.

### Application d’un filtre simple ou avancé à un tableau

Pour filtrer les données dans les tableaux à structure libre :

1. Pointez sur la colonne contenant les données à filtrer. <!--only some types of columns show the filter... Which? Just Dimensions?-->

1. Sélectionnez l’icône **Filtre** lorsqu’elle s’affiche.

   ![Icône Filtre dans un tableau.](assets/table-filter-icon.png)

   Les options disponibles sont les suivantes :

   | Option | Fonction |
   |---------|----------|
   | [!UICONTROL **Mot ou expression de recherche**] | Indiquez un mot ou une expression à filtrer. Seules les lignes contenant le mot ou l’expression exacte spécifié(e) sont affichées. |
   | [!UICONTROL **Inclure non spécifié (aucun)**] | Sélectionnez cette option pour afficher dans le tableau les données qui n’appartiennent à aucune des dimensions du tableau. <!--what is this?--> |

1. (Facultatif) Pour filtrer selon différents ou plusieurs critères, sélectionnez [!UICONTROL **Afficher les paramètres avancés**].

   Les options de filtrage avancées suivantes sont disponibles :

   | Option | Fonction |
   |---------|----------|
   | [!UICONTROL **Inclure non spécifié (aucun)**] | Sélectionnez cette option pour afficher dans le tableau les données qui n’appartiennent à aucune des dimensions du tableau. <!--what is this?--> |
   | [!UICONTROL **Correspond à**] | <p>Choisissez [!UICONTROL **Si tous les critères sont satisfaits**] pour afficher uniquement les données qui répondent à tous les critères que vous spécifiez. Cette option produit généralement des données plus précises.</p> <p>Choisissez [!UICONTROL **Si au moins l’un des critères est satisfait**] pour afficher les données qui répondent à l’un des critères de filtre que vous spécifiez. Cette option aboutit généralement à des données moins précises.</p> |
   | [!UICONTROL **Critères**] | <p>Sélectionnez l’une des options de filtre suivantes :</p><p>(Sélectionnez [!UICONTROL **Ajouter une ligne**] pour ajouter plusieurs critères de filtre. L’option que vous sélectionnez dans la section [!UICONTROL **Correspondance**] détermine si la totalité ou une partie des critères que vous ajoutez doit être satisfaite.)</p><ul><li><p>[!UICONTROL **Contient l’expression**] : seules les données contenant l’expression exacte que vous spécifiez sont incluses dans les résultats filtrés. Les mots doivent être dans l’ordre spécifié dans le champ [!UICONTROL **Chercher un mot ou une expression**].<p>Il s’agit du paramètre par défaut lors d’une recherche simple.</p></p></li><li><p>[!UICONTROL **Contient n’importe quel terme**] : seules les données contenant un ou plusieurs mots de l’expression que vous spécifiez sont incluses dans les résultats filtrés. </p></li><li><p>[!UICONTROL **Contient tous les termes**] : seules les données contenant tous les mots de l’expression que vous spécifiez sont incluses dans les résultats filtrés. Les mots n’ont pas nécessairement à être dans l’ordre spécifié dans le champ [!UICONTROL **Chercher un mot ou une expression**].</p></li><li><p>[!UICONTROL **Ne contient aucun terme**] : seules les données qui ne contiennent aucun des mots de l’expression que vous spécifiez sont incluses dans les résultats filtrés. </p></li><li><p>[!UICONTROL **Ne contient pas l’expression**] : seules les données qui ne contiennent pas l’expression exacte que vous spécifiez sont incluses dans les résultats filtrés. Les mots doivent être dans l’ordre spécifié dans le champ [!UICONTROL **Chercher un mot ou une expression**].</p></li><li><p>[!UICONTROL **Est égal à**] : seules les données qui correspondent exactement à l’expression que vous spécifiez sont incluses dans les résultats filtrés. </p></li><li><p>[!UICONTROL **N’est pas égal à**] : seules les données qui ne correspondent pas exactement à l’expression spécifiée sont incluses dans les résultats filtrés. </p></li><li><p>[!UICONTROL **Commence par**] : seules les données commençant par le mot ou l’expression exacte que vous spécifiez sont incluses dans les résultats filtrés. </p></li><li><p>[!UICONTROL **Se termine par**] : seules les données qui se terminent par le mot ou l’expression exacte que vous spécifiez sont incluses dans les résultats filtrés. </p></li></ul> |
   | [!UICONTROL **Toujours exclure les éléments**] | Indiquez le nom des éléments que vous souhaitez exclure des données filtrées. |

1. Sélectionnez [!UICONTROL **Appliquer**] pour filtrer les données.

   L’icône **Filtre** ![Icône de filtre bleue du tableau filtré](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) devient bleue lorsqu’un filtre est appliqué au tableau.

### Segmentation

Voir notre [Documentation sur la segmentation](https://docs.adobe.com/help/fr-FR/analytics/components/segmentation/seg-home.html) pour plus d’informations.

## Trier des tableaux

Vous pouvez trier les données d’un tableau à structure libre selon n’importe quelle colonne d’Analysis Workspace qui est une mesure.

Une icône de flèche vers le bas ![Icône de flèche vers le bas dans la colonne du tableau trié](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) est visible dans l’en-tête de la colonne par laquelle les données sont actuellement triées.

Pour trier les données d’un tableau à structure libre selon une colonne particulière :

1. Pointez sur le titre de la colonne selon laquelle vous souhaitez trier les données.

2. Sélectionnez l’icône de flèche vers le bas lorsqu’elle s’affiche.

   ![Icône de flèche vers le bas dans la colonne du tableau trié.](assets/table-sort.png)

   Les données du tableau sont triées selon la colonne sélectionnée.
