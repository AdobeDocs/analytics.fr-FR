---
title: Processus de consolidation des jeux de classifications
description: Processus complet de consolidation des jeux de classifications.
source-git-commit: 496b4891d447ed9dd091a6498a792146a2d5aceb
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 0%

---

# Processus de consolidation des jeux de classifications

Utilisez cette interface pour créer une consolidation de jeu de classifications du début à la fin.

## Création

**[!UICONTROL Composants]** > **[!UICONTROL Jeux de classifications]** > **[!UICONTROL Consolidation]** > **[!UICONTROL Ajouter]**

Les champs suivants sont disponibles lors de la création d&#39;une consolidation :

* **[!UICONTROL Nom]**: Nom de la consolidation.
* **[!UICONTROL Notification des problèmes]**: Liste, délimitée par des virgules, des adresses électroniques qui sont informées des problèmes liés à cette consolidation.
* **[!UICONTROL Jeu de données à faire correspondre]**: Liste déroulante de tous les jeux de classifications.

Une fois que vous avez sélectionné un jeu de classifications, un tableau comportant deux colonnes s’affiche :

* La colonne de droite contient tous les jeux de classifications que vous souhaitez consolider. Elle commence par le jeu de classifications sélectionné à l’aide de la liste déroulante ci-dessus.
* La colonne de gauche contient tous les jeux de classifications pouvant être fusionnés avec le jeu de données sélectionné d’origine. **Les schémas doivent correspondre exactement à pour être éligibles à la consolidation.**. Si les schémas ne correspondent pas au jeu de classifications sélectionné, ils n’apparaissent pas dans cette colonne de gauche.

Faites glisser les jeux de classifications de votre choix de la colonne disponible à gauche vers la colonne de consolidation à droite. Une fois que la consolidation a un nom et que deux jeux de classifications ou plus sont dans la colonne de droite, cliquez sur **[!UICONTROL Enregistrer et continuer]**.

## Validation

Une fois que vous avez créé une consolidation, une liste de jeux de données source s’affiche à droite. Le **[!UICONTROL Valider]** s’assure que chaque jeu de classifications individuel est valide pour cette consolidation. Vous pouvez réorganiser les étapes de classification ici pour déterminer la priorité en cas de valeurs de classification incohérentes. **Le jeu de classifications le plus élevé de la liste remplace toutes les valeurs non correspondantes dans d’autres jeux de classifications.**

## Exécutez

Une fois une consolidation validée, vous pouvez l&#39;exécuter. L’exécution d’une consolidation fournit un rapport de similarité avec les colonnes de tableau suivantes :

* **[!UICONTROL Nom du jeu de données]**: Nom du jeu de classifications.
* **[!UICONTROL Discordance]**: Pourcentage des lignes où les valeurs clés ne correspondaient pas au jeu de classifications source. Si le pourcentage d’incohérence est élevé, il est possible que les données de classification soient trop différentes. Vérifiez et assurez-vous que les jeux de classifications sélectionnés possèdent des données de classification similaires.
* **[!UICONTROL Absent]**: Pourcentage de lignes où des valeurs clés se trouvaient dans ce jeu de classifications, mais pas dans le jeu de classifications source. Toutes les lignes absentes sont ajoutées au jeu de classifications consolidé.

## Approuver

Agit comme dernier appel avant de supprimer des jeux de classifications individuels et de créer un jeu de classifications consolidé. Assurez-vous que tout est correct, puis cliquez sur **[!UICONTROL Approuver]**.

Une fois approuvé, le jeu de classifications consolidé est créé. L’état est défini sur [!UICONTROL Terminer], et aucune autre action n’est requise pour la consolidation.
