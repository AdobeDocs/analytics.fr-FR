---
description: Les clés non classifiées sont regroupées dans des rapports de classification sous la forme d’un élément unique intitulé Aucun. Il peut se révéler utile de renommer Aucun en un élément plus explicite.
title: Clés non classifiées
feature: Classifications
exl-id: 37288c2d-f6f6-4343-87a1-3c3a7b56fe32
source-git-commit: ce7f953b8f7f1f7d0616074454e4401937fcc0c7
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 85%

---

# Clés non classifiées

Les clés non classifiées sont regroupées dans des rapports de classification sous la forme d’un élément unique intitulé Aucun. Il peut se révéler utile de renommer Aucun en un élément plus explicite.

## Clés non classifiées {#concept_233E51DDF3084FF7B7EA89381C73C5FF}

Les clés non classées sont regroupées dans des rapports de classification sous la forme d’un élément unique intitulé *`None`*. Il peut se révéler utile de renommer *`None`* en un élément plus explicite.

Supposons, par exemple, que vos codes de suivi contiennent des informations qui délimitent le type de campagne mobile auquel ils sont associés. Vous avez recours à la classification (Type de campagne mobile) pour regrouper ces codes de suivi dans des catégories telles que Web mobile, Application iOS, Application Android, etc. Il se peut que certaines campagnes ne soient pas destinées aux mobiles. Elles ne sont donc pas classées avec ce type. Tous les codes de suivi non classés seront regroupés sous *`None`* dans le rapport [!UICONTROL Type de campagne mobile].

## Renommer la clé de classification Aucun {#task_8CD595DA82AA44D08CEF002B588C3C30}

<!-- 

t_rename_classification_none.xml

 -->

Pour renommer une clé non classée affichée sous la forme *`none`* dans les rapports :

1. À l’aide de l’importateur, exportez les classifications vers un fichier local.
1. Ajoutez une ligne au fichier et saisissez `~none~` dans la colonne Clé.
1. Dans la ligne que vous avez ajoutée, entrez un nom plus explicite dans la ou les colonnes de classification appropriées.

   Pour suivre l’exemple illustré dans cette documentation, vous pouvez saisir « non-mobile campaign » dans une colonne intitulée [!UICONTROL Type de campagne mobile].

   Cette entrée renomme *`None`* en *`non-mobile campaign`* dans le rapport [!UICONTROL Type de campagne mobile].

   ![Exemple de clé non classifiée](/help/components/classifications/importer/assets/non-classified-key.png)

1. [Réimportez les données](/help/components/classifications/importer/import-file.md) dans le système.
