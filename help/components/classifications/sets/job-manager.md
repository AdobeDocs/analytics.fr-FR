---
title: Gestionnaire des tâches des ensembles de classifications
description: Affichez les tâches de classification en cours et terminées, générées par des ensembles de classifications.
exl-id: 0470e131-79c6-4906-85f0-530d360ac227
source-git-commit: 34ba0e09cd909951a777b0ad3da080958633f97e
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 100%

---

# Gestionnaire des tâches des ensembles de classifications

Le Gestionnaire des tâches des ensembles de classifications vous permet d’afficher les tâches de classification en cours et terminées, qui ont été générées à partir d’ensembles de classifications. Vous pouvez également utiliser cette interface pour télécharger des données ou des modèles de classification pour une tâche spécifique, ou pour charger des données supplémentaires dans une tâche.

**[!UICONTROL Composants]** > **[!UICONTROL Ensembles de classifications]** > **[!UICONTROL Tâches]**

Notez que vous ne pouvez pas créer de tâches à partir de cette interface. En revanche, vous pouvez créer des tâches en chargeant des données dans un ensemble de classifications, ou en demandant un fichier de téléchargement ou un fichier modèle.

## Filtrer des ensembles de classifications

Le côté gauche du Gestionnaire des tâches des ensembles de classifications fournit des paramètres de filtre permettant de localiser la tâche souhaitée. Cliquez sur l’icône de filtre pour faire apparaître les paramètres de filtre. Vous pouvez filtrer les ensembles de classifications par **[!UICONTROL Ensemble de classifications]**, **[!UICONTROL Heure de fin]** ou **[!UICONTROL Statut]**.

![Filtres de tâches des ensembles de classifications](../assets/classification-set-job-filters.png)

Des options de filtre supplémentaires sont disponibles au-dessus des colonnes du Gestionnaire des tâches des ensembles de classifications :

* **[!UICONTROL Recherche par titre]** : recherchez des tâches par nom de fichier.
* **[!UICONTROL Charger plus]** : le Gestionnaire des tâches des ensembles de classifications affiche initialement jusqu’à 1 000 tâches. Cliquez sur ce bouton pour charger 1 000 tâches supplémentaires.
* **Afficher/masquer les colonnes** : activez la visibilité de n’importe quelle colonne, à l’exception de [!UICONTROL Nom de fichier] et de [!UICONTROL Heure de fin].

## Colonnes du Gestionnaire des tâches des ensembles de classifications

Les colonnes suivantes sont disponibles dans le Gestionnaire des tâches des ensembles de classifications :

* **[!UICONTROL Nom de fichier]** : le nom du fichier à charger ou à télécharger.
* **[!UICONTROL Ensemble de classifications]** : le nom de l’ensemble de classifications auquel le fichier s’applique. Vous pouvez cliquer sur le nom de l’ensemble de classifications pour accéder aux [paramètres](settings.md) de celui-ci.
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
* **[!UICONTROL Type]** : le type de tâche.
* **[!UICONTROL Téléchargement de fichier]** : s’applique uniquement aux tâches de téléchargement, telles que le téléchargement de données de classification ou le téléchargement de modèles. Lorsqu’un téléchargement est prêt, cette colonne fournit un lien de téléchargement.
* **[!UICONTROL Heure de fin]** : la date et l’heure auxquelles la tâche s’est terminée (ou a échoué).
