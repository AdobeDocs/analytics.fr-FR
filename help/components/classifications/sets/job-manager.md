---
title: Gestionnaire de tâches du jeu de classifications
description: Affichez les tâches de classification actuelles et terminées générées à partir des jeux de classifications.
exl-id: 0470e131-79c6-4906-85f0-530d360ac227
source-git-commit: a1f199525c567bc9d7bb614ee03980f582cbbc7a
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 0%

---

# Gestionnaire des tâches du jeu de classifications

Le gestionnaire des tâches du jeu de classifications vous permet d’afficher les tâches de classification en cours et terminées qui ont été générées à partir de jeux de classifications. Vous pouvez également utiliser cette interface pour télécharger des données de classification ou des modèles pour une tâche spécifique, ou charger des données supplémentaires dans une tâche.

**[!UICONTROL Composants]** > **[!UICONTROL Jeux de classifications]** > **[!UICONTROL Tâches]**

Notez que vous ne pouvez pas créer de tâches à partir de cette interface. Vous pouvez plutôt créer des tâches en chargeant des données dans un jeu de classifications, en demandant un fichier de téléchargement ou en demandant un fichier de modèle.

## Filtrer les jeux de classifications

Le côté gauche du Gestionnaire des tâches du jeu de classifications fournit des paramètres de filtre pour localiser la tâche souhaitée. Le fait de cliquer sur l’icône Filtrer change la visibilité des paramètres de filtre. Vous pouvez filtrer les jeux de classifications par **[!UICONTROL Jeu de classifications]**, **[!UICONTROL Heure de fin]** ou **[!UICONTROL État]**.

![Filtres de tâches du jeu de classifications](../assets/classification-set-job-filters.png)

D’autres options de filtre sont disponibles au-dessus des colonnes Gestionnaire de tâches du jeu de classifications :

* **[!UICONTROL Recherche par titre]**: Recherchez des tâches par nom de fichier.
* **[!UICONTROL Charger plus]**: Le gestionnaire des tâches du jeu de classifications affiche initialement jusqu’à 1 000 tâches. Cliquez sur ce bouton pour charger 1 000 tâches supplémentaires.
* **Afficher/masquer les colonnes**: Activer/désactiver la visibilité de n’importe quelle colonne en plus de [!UICONTROL Nom du fichier] et [!UICONTROL Heure de fin].

## Colonnes Gestionnaire de tâches du jeu de classifications

Les colonnes suivantes sont disponibles dans le Gestionnaire de tâches du jeu de classifications :

* **[!UICONTROL Nom du fichier]**: Nom du fichier de téléchargement.
* **[!UICONTROL Jeu de classifications]**: Nom du jeu de classifications auquel le fichier s’applique. Vous pouvez cliquer sur le nom du jeu de classifications pour accéder aux [Paramètres](settings.md).
* **[!UICONTROL Taille]**: Taille du fichier.
* **[!UICONTROL État]**: L’état de la tâche qui traite le fichier.
   * **[!UICONTROL Créé]**: La tâche a été envoyée.
   * **[!UICONTROL En file d&#39;attente]**: Le fichier est prêt à être traité et attend qu’un serveur de classification le traite.
   * **[!UICONTROL Validé]**: Le fichier est valide et attend d’être traité.
   * **[!UICONTROL Échec de la validation]**: Le fichier n’est pas correctement formaté ou n’est pas valide. Le fichier ne passe pas par le traitement.
   * **[!UICONTROL Traitement]**: Le fichier est activement traité par Adobe.
   * **[!UICONTROL Échec du traitement]**: Le traitement du fichier a échoué.
   * **[!UICONTROL Terminer]**: Le traitement est terminé. Les données de classification sont visibles dans les rapports.
   * **[!UICONTROL En échec]**: Échec générique non lié à la validation ou au traitement.
* **[!UICONTROL Type]**: Type de tâche.
* **[!UICONTROL Téléchargement de fichier]**: S’applique uniquement aux tâches de téléchargement, telles que le téléchargement de données de classification ou le téléchargement de modèles. Lorsqu’un téléchargement est prêt, cette colonne fournit un lien de téléchargement.
* **[!UICONTROL Heure de fin]**: Date et heure auxquelles la tâche s’est terminée (ou a échoué).
