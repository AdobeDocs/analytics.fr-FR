---
title: Gestionnaire des tâches de jeux de classifications
description: Affichez les tâches de classification actuelles et terminées générées à partir de jeux de classifications.
exl-id: 0470e131-79c6-4906-85f0-530d360ac227
feature: Classifications
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '415'
ht-degree: 49%

---

# Gestionnaire des tâches de jeux de classifications

Le gestionnaire des tâches des jeux de classifications vous permet d’afficher les tâches de classification en cours et terminées qui ont été générées à partir de jeux de classifications. Vous pouvez également utiliser cette interface pour télécharger des données ou des modèles de classification pour une tâche spécifique, ou pour charger des données supplémentaires dans une tâche.

**[!UICONTROL Composants]** > **[!UICONTROL Ensembles de classifications]** > **[!UICONTROL Tâches]**

Vous ne pouvez pas créer de tâches à partir de cette interface. Créez des tâches en chargeant des données dans un jeu de classifications (manuellement ou via un emplacement externe configuré), en demandant un fichier de téléchargement ou en demandant un fichier de modèle.

## Filtrage des jeux de classifications

Le côté gauche du gestionnaire de tâches du jeu de classifications fournit des paramètres de filtre pour localiser la tâche souhaitée. Cliquez sur l’icône de filtre pour faire apparaître les paramètres de filtre. Vous pouvez filtrer les jeux de classifications par **[!UICONTROL Jeu de classifications]**, **[!UICONTROL Heure de fin]**, **[!UICONTROL État]**, **[!UICONTROL Type de tâche]** ou **[!UICONTROL Source]**.

![Filtres de tâche de jeu de classifications](../assets/classification-set-job-filters.png)

D’autres options de filtre sont disponibles au-dessus des colonnes du gestionnaire de tâches du jeu de classifications :

* **[!UICONTROL Recherche par titre]** : recherchez des tâches par nom de fichier.
* **[!UICONTROL Charger plus]**: Le gestionnaire des tâches du jeu de classifications affiche initialement jusqu’à 1 000 tâches. S’il existe d’autres tâches, cliquez sur ce bouton pour charger 1 000 autres tâches.
* **Afficher/masquer les colonnes** : activez la visibilité de n’importe quelle colonne, à l’exception de [!UICONTROL Nom de fichier] et de [!UICONTROL Heure de fin].

## Colonnes du gestionnaire de tâches du jeu de classifications

Les colonnes suivantes sont disponibles dans le gestionnaire de tâches du jeu de classifications :

* **[!UICONTROL Nom de fichier]** : le nom du fichier à charger ou à télécharger.
* **[!UICONTROL Jeu de classifications]**: Nom du jeu de classifications auquel le fichier s’applique. Vous pouvez cliquer sur le nom du jeu de classifications pour accéder au [Paramètres](manage/settings.md).
* **[!UICONTROL Taille]** : la taille du fichier.
* **[!UICONTROL Statut]** : le statut de la tâche qui traite le fichier.
   * **[!UICONTROL Créé]** : la tâche a été envoyée.
   * **[!UICONTROL En file d’attente]** : le fichier est prêt à être traité et attend qu’un serveur de classification le traite.
   * **[!UICONTROL Validé]** : le fichier est valide et attend d’être traité.
   * **[!UICONTROL Échec de la validation]** : le fichier est mal formaté ou non valide. Le fichier n’est pas traité.
   * **[!UICONTROL Traitement]** : le fichier est en cours de traitement par Adobe.
   * **[!UICONTROL Échec du traitement]** : le traitement du fichier a échoué.
   * **[!UICONTROL Terminé]** : le traitement est terminé. Les données de classification sont visibles dans les rapports.
   * **[!UICONTROL Échec]** : échec générique non lié à la validation ou au traitement.
* **[!UICONTROL Type de tâche]**: Type de tâche.
* **[!UICONTROL Source]**: La source de la tâche.
* **[!UICONTROL Téléchargement de fichier]** : s’applique uniquement aux tâches de téléchargement, telles que le téléchargement de données de classification ou le téléchargement de modèles. Lorsqu’un téléchargement est prêt, cette colonne fournit un lien de téléchargement.
* **[!UICONTROL Lignes modifiées]**: Nombre de lignes modifiées.
* **[!UICONTROL Lignes terminées]**: Nombre de lignes terminées.
* **[!UICONTROL Heure de fin]** : la date et l’heure auxquelles la tâche s’est terminée (ou a échoué).
