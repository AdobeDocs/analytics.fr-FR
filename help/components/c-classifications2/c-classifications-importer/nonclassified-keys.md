---
description: Les clés non classées sont regroupées dans des rapports de classification sous la forme d’un élément unique intitulé Aucun. Il peut se révéler utile de renommer Aucun en un élément plus explicite.
subtopic: Classifications
title: Clés non classifiées
topic: Admin tools
uuid: b73a9161-0c6f-4c8d-900b-54ab2c36147c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Clés non classifiées

Les clés non classées sont regroupées dans des rapports de classification sous la forme d’un élément unique intitulé Aucun. Il peut se révéler utile de renommer Aucun en un élément plus explicite.

## Clés non classifiées {#concept_233E51DDF3084FF7B7EA89381C73C5FF}

Les clés non classées sont regroupées dans des rapports de classification sous la forme d’un élément unique intitulé *`None`*. Il peut se révéler utile de renommer *`None`* en un élément plus explicite.

Supposons, par exemple, que vos codes de suivi contiennent des informations qui délimitent le type de campagne mobile auquel ils sont associés. Vous avez recours à la classification (Type de campagne mobile) pour regrouper ces codes de suivi dans des catégories telles que Web mobile, Application iOS, Application Android, etc. Il se peut que certaines campagnes ne soient pas destinées aux mobiles. Elles ne sont donc pas classées avec ce type. Tous les codes de suivi non classés sont rassemblés sous *`None`* dans le rapport [!UICONTROL Type de campagne mobile].

## Renommer la clé de classification Aucun {#task_8CD595DA82AA44D08CEF002B588C3C30}

<!-- 

t_rename_classification_none.xml

 -->

Description de la procédure de changement de nom d’une clé non classée affichée sous la forme *`none`* dans les rapports.

1. À l’aide de l’importateur, exportez des classifications vers un fichier local.
1. Ajoutez une ligne au fichier et saisissez [!DNL ~none~] dans la colonne Clé.
1. Dans la ligne que vous avez ajoutée, entrez un nom plus explicite dans la ou les colonnes de classification appropriées.

   Pour suivre l’exemple illustré dans cette documentation, vous pouvez saisir « non-mobile campaign » dans une colonne intitulée [!UICONTROL Nom de campagne mobile].

   Cette entrée renomme *`None`* en *`non-mobile campaign`* dans le rapport [!UICONTROL Type de campagne mobile].
1. [Réimportez les données](/help/components/c-classifications2/c-classifications-importer/import-file.md) dans le système.
