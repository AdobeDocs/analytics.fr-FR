---
title: Processus de consolidation des ensembles de classifications
description: Processus complet de consolidation des ensembles de classifications.
exl-id: f36bcbcb-0ed0-44a7-a6a9-b28fd244fb27
feature: Classifications
source-git-commit: 828f41bf45c1954c3b68ad71a7746e24626b9eed
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 0%

---

# Processus de consolidation des ensembles de classifications

Les consolidations de classification vous permettent de prendre des classifications de plusieurs jeux de données et de les combiner en un seul. Utilisez cette interface pour créer une consolidation d’ensemble de classifications du début à la fin. Cette interface est particulièrement utile pour les organisations qui passent d’une architecture de classification héritée à une architecture de jeu de classification. La plupart des organisations qui utilisent déjà l’architecture du jeu de classifications n’ont généralement pas besoin d’utiliser ce workflow de consolidation.

## Création

**[!UICONTROL Composants]** > **[!UICONTROL Jeux de classifications]** > **[!UICONTROL Consolidations]** > **[!UICONTROL Ajouter]**

Les champs suivants sont disponibles lors de la création d&#39;une consolidation :

* **[!UICONTROL Nom]** : nom de la consolidation.
* **[!UICONTROL Notifier des problèmes]** : liste, séparée par des virgules, d’adresses e-mail qui sont notifiées des problèmes liés à cette consolidation.
* **[!UICONTROL Jeu de données à faire correspondre]** : liste déroulante de tous les jeux de classifications.

Une fois que vous avez sélectionné un ensemble de classifications, un tableau à deux colonnes s’affiche :

* La colonne de droite contient tous les ensembles de classifications que vous souhaitez consolider. Elle commence par l’ensemble de classifications sélectionné à l’aide de la liste déroulante ci-dessus.
* La colonne de gauche contient tous les jeux de classifications pouvant être fusionnés avec le jeu de données sélectionné à l’origine. **Les schémas doivent correspondre exactement pour pouvoir être consolidés**. Si les schémas ne correspondent pas à l’ensemble de classifications sélectionné, ils n’apparaissent pas dans cette colonne de gauche.

Faites glisser les ensembles de classifications de votre choix de la colonne disponible à gauche vers la colonne de consolidation à droite. Une fois que la consolidation a reçu un nom et que deux ensembles de classifications ou plus se trouvent dans la colonne de droite, cliquez sur **[!UICONTROL Enregistrer et continuer]**.

## Validation

Une fois que vous avez créé une consolidation, une liste des jeux de données sources s’affiche à droite. Le bouton **[!UICONTROL Valider]** garantit que chaque ensemble de classifications individuel est valide pour cette consolidation. Vous pouvez réorganiser les étapes de classification ici pour déterminer la priorité en cas de valeurs de classification incohérentes. **L’ensemble de classifications le plus élevé de la liste remplace toutes les valeurs incohérentes dans d’autres ensembles de classifications.**

## Exécutez

Une fois la consolidation validée, vous pouvez l’exécuter. L&#39;exécution d&#39;une consolidation génère un état de similarité avec les colonnes de tableau suivantes :

* **[!UICONTROL Nom du jeu de données]** : le nom de l’ensemble de classifications.
* **[!UICONTROL Discordance]** : pourcentage de lignes dont les valeurs de clé ne correspondaient pas à l’ensemble de classifications source. Si le pourcentage d’incohérence est élevé, il est possible que les données de classification soient trop différentes. Vérifiez et assurez-vous que les ensembles de classifications sélectionnés ont des données de classification similaires.
* **[!UICONTROL Absent]** : pourcentage de lignes où les valeurs clés se trouvaient dans cet ensemble de classifications mais pas dans l’ensemble de classifications source. Toutes les lignes absentes sont ajoutées à l’ensemble de classifications consolidé.

## Approuver

Dernier appel avant de supprimer des ensembles de classifications individuels et de les remplacer par un ensemble de classifications consolidé. Vérifiez que tout est correct, puis sélectionnez **[!UICONTROL Approuver]**.

Une fois approuvé, l’ensemble de classifications consolidé est créé. Le statut est défini sur [!UICONTROL Terminé] et aucune autre action n&#39;est requise pour la consolidation.
