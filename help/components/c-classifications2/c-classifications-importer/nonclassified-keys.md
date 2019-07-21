---
description: Les clés non classées sont regroupées dans des rapports de classification sous la forme d’un élément unique intitulé Aucun. Il peut se révéler utile de renommer Aucun en un élément plus explicite.
seo-description: Les clés non classées sont regroupées dans des rapports de classification sous la forme d’un élément unique intitulé Aucun. Il peut se révéler utile de renommer Aucun en un élément plus explicite.
seo-title: Clés non classées
solution: Analytics
subtopic: Gestionnaire
title: Clés non classées
topic: Outils d’administration
uuid: b 73 a 9161-0 c 6 f -4 c 8 d -900 b -54 ab 2 c 36147 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Clés non classées

Les clés non classées sont regroupées dans des rapports de classification sous la forme d’un élément unique intitulé Aucun. Il peut se révéler utile de renommer Aucun en un élément plus explicite.

## Non-classified keys {#concept_233E51DDF3084FF7B7EA89381C73C5FF}

Les clés non classées sont regroupées dans des rapports de classification sous la forme d’un élément unique intitulé *`None`*. It can be useful to rename *`None`* to something more descriptive.

Supposons, par exemple, que vos codes de suivi contiennent des informations qui délimitent le type de campagne mobile auquel ils sont associés. Vous avez recours à la classification (Type de campagne mobile) pour regrouper ces codes de suivi dans des catégories telles que Web mobile, Application iOS, Application Android, etc. Il se peut que certaines campagnes ne soient pas destinées aux mobiles. Elles ne sont donc pas classées avec ce type. Tous les codes de suivi non classés sont rassemblés sous *`None`* dans le rapport [!UICONTROL Type de campagne mobile].

## Renommer la clé de classification Aucun {#task_8CD595DA82AA44D08CEF002B588C3C30}

<!-- 

t_rename_classification_none.xml

 -->

Steps that describe how to rename a non-classified key that displays as *`none`* in reporting.

1. À l’aide de l’importateur, exportez des classifications vers un fichier local.
1. Add a row to the file, and type [!DNL ~none~] in the Key column.
1. Dans la ligne que vous avez ajoutée, entrez un nom plus explicite dans la ou les colonnes de classification appropriées. 

   Pour suivre l’exemple illustré dans cette documentation, vous pouvez saisir « non-mobile campaign » dans une colonne intitulée [!UICONTROL Nom de campagne mobile].

   Cette entrée renomme *`None`* dans *`non-mobile campaign`* le rapport [!UICONTROL Type] de campagne mobile.
1. [Réimportez les données](../../../components/c-classifications2/c-classifications-importer/import-file.md#concept_F88785E2BDFD448CB5D1DA3491466B0D) dans le système.
