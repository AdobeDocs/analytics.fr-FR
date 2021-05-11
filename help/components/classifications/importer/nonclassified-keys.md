---
description: Les clés non classifiées sont regroupées dans les rapports de classification sous la forme d’un élément unique intitulé Aucun. Il peut se révéler utile de renommer Aucun en un élément plus explicite.
subtopic: Classifications
title: Clés non classifiées
feature: Outils d’administration
uuid: b73a9161-0c6f-4c8d-900b-54ab2c36147c
exl-id: 37288c2d-f6f6-4343-87a1-3c3a7b56fe32
translation-type: tm+mt
source-git-commit: f52baf97efe20b209f51108995a0620b6c19bec0
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 62%

---

# Clés non classifiées

Clés non classifiées sont regroupées dans des rapports de classification sous la forme d’un élément unique intitulé Aucun. Il peut se révéler utile de renommer Aucun en un élément plus explicite.

## Clés non classifiées {#concept_233E51DDF3084FF7B7EA89381C73C5FF}

Les clés non classifiées sont regroupées dans des rapports de classification sous la forme d&#39;une seule ligne intitulée *`None`*. Il peut se révéler utile de renommer *`None`* en un élément plus explicite.

Supposons, par exemple, que vos codes de suivi contiennent des informations qui délimitent le type de campagne mobile auquel le code de suivi est associé. Vous avez recours à la classification (Type de campagne mobile) pour regrouper ces codes de suivi dans des catégories telles que Web mobile, Application iOS, Application Android, etc. Il se peut que certaines campagnes ne soient pas destinées aux mobiles. Elles ne sont donc pas classées avec ce type. Tous les codes de suivi non classés sont rassemblés sous *`None`* dans le rapport [!UICONTROL Type de campagne mobile].

## Renommer la clé de classification Aucun {#task_8CD595DA82AA44D08CEF002B588C3C30}

<!-- 

t_rename_classification_none.xml

 -->

Description de la procédure de changement de nom d’une clé non classée affichée sous la forme *`none`* dans les rapports.

1. À l’aide de l’importateur, exportez des classifications vers un fichier local.
1. Ajoutez une ligne au fichier et saisissez `~none~` dans la colonne Clé.
1. Dans la ligne que vous avez ajoutée, entrez un nom plus explicite dans la ou les colonnes de classification appropriées.

   Pour suivre l&#39;exemple de cette documentation, vous pouvez taper &quot;non-mobile campaign&quot; dans une colonne nommée [!UICONTROL Mobile Campaign Type].

   Cette entrée renomme *`None`* en *`non-mobile campaign`* dans le rapport [!UICONTROL Type de Campaign mobile].

   ![Exemple de clé non classée](/help/components/classifications/importer/assets/non-classified-key.png)

1. [Réimportez les données](/help/components/classifications/importer/import-file.md) dans le système.
