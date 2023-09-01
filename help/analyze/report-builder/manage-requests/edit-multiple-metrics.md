---
description: Découvrez comment ajouter, supprimer ou remplacer des mesures dans une requête préexistante ou dans un groupe de requêtes.
title: Comment modifier les mesures de plusieurs demandes
feature: Report Builder
role: User, Admin
exl-id: e537b67a-aa07-4acd-a476-7497426e2f7d
source-git-commit: 66b7de0b008364e47253d319785c204ca479ab26
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 30%

---

# Modification des mesures de plusieurs demandes

Ajouter, supprimer ou remplacer des mesures dans une requête préexistante ou dans un groupe de requêtes.

## Ajouter des mesures {#section_3FBDA9668039404895059618D70FCBCD}

Lorsque vous ajoutez des mesures, tenez compte des recommandations suivantes :

* Les mesures peuvent uniquement être ajoutées à des demandes de type Disposition croisée dynamique.
Si certaines des demandes sélectionnées sont de type Disposition personnalisée, les mesures ne peuvent pas être ajoutées. Si la disposition est personnalisée, Report Builder ne sait pas où placer la nouvelle mesure dans la feuille de calcul.
* Si vous sélectionnez uniquement des requêtes de mise en page personnalisée, la variable **[!UICONTROL Ajout de mesures]** n’est pas disponible.
* L’ajout de mesures augmente la taille d’une requête et peut la faire chevaucher. Assurez-vous que la demande dispose de suffisamment d’espace pour permettre l’ajout de mesures.
* Si la mesure ajoutée est déjà présente dans l’une des requêtes sélectionnées, elle ne sera pas ajoutée à cette requête.

Pour ajouter une ou plusieurs mesures

1. Sélectionnez une ou plusieurs demandes dans Excel et cliquez avec le bouton droit pour sélectionner **[!UICONTROL Modifier les mesures]**. (Ou cliquez sur **[!UICONTROL Gérer]** > **[!UICONTROL Modifier plusieurs]** > `<choose metric>` > **[!UICONTROL Modifier le groupe]** pour sélectionner le groupe de demandes à modifier.)
1. Sélectionnez **[!UICONTROL Ajouter des mesures]** et sélectionnez les mesures à ajouter.

   ![Capture d’écran montrant l’option Modifier la requête, Ajouter des mesures sélectionnée.](assets/add_metric.png)

1. Actualisez la demande pour afficher les données réelles. Les données hors ligne s’affichent jusqu’à ce que vous les actualisiez.

## Remplacement des mesures

Lorsque vous remplacez des mesures, tenez compte des recommandations suivantes :

* Seules les substitutions 1:1 sont autorisées. 1:many ou many:1 ne sont pas autorisés.
* Si la mesure sélectionnée n’est pas présente dans l’une des requêtes sélectionnées, la requête reste inchangée.
* La nouvelle mesure est placée au même emplacement que la mesure remplacée.

   * **En mode croisé dynamique**, si une requête de disposition croisée dynamique génère la date, la visite, les visiteurs, le nombre unique quotidien et *visiteurs* est remplacé par *revenue*, la mise en page mise à jour de la requête sera : date, visite, recettes et quotidien unique.
   * **Dans une disposition personnalisée**, si la variable *visiteurs* était générée dans la cellule F11, la disposition de requête mise à jour affiche *revenue* dans la même cellule F11.

* Si une ou plusieurs opérations étaient appliquées à la mesure remplacée (moyenne, texte en préfixe, texte en suffixe, micrographique), celles-ci seront également appliquées à la nouvelle mesure.

Pour remplacer une mesure

1. Sélectionnez une ou plusieurs demandes dans Excel et cliquez avec le bouton droit pour sélectionner **[!UICONTROL Modifier les mesures]**. Vous pouvez également cliquer sur **[!UICONTROL Gérer]** > **[!UICONTROL Modifier plusieurs]** > **`<choose metric>`** > **[!UICONTROL Modifier le groupe]** pour sélectionner le groupe de requêtes à modifier.

1. Sélectionnez **[!UICONTROL Remplacer la mesure]**.

   ![Capture d’écran de l’écran Modifier le groupe avec l’option Remplacer la mesure sélectionnée.](assets/replace_metric.png)

1. Sélectionnez la mesure à remplacer et la mesure de remplacement.
1. Actualisez la demande. Les données hors ligne s’affichent jusqu’à ce que vous les actualisiez.

## Supprimer des mesures {#section_D3CD5BAC7670416593B633B2B8423C60}

Lorsque vous supprimez des mesures, tenez compte des recommandations suivantes :

* Si l’une des mesures que vous sélectionnez pour suppression n’est pas présente dans l’une des requêtes sélectionnées, la requête reste inchangée.
* Dans une disposition croisée dynamique, la suppression d’une mesure entraîne le déplacement de la disposition pour les mesures situées après la mesure supprimée. Par exemple, si une demande de mise en page croisée dynamique génère la date, les visites, les visiteurs et l’unique quotidien, et que vous supprimez *visites*, la mise en page mise à jour de la requête affiche : date, visiteurs et valeur unique quotidienne.

Pour supprimer des mesures

1. Sélectionnez une ou plusieurs demandes dans Excel et cliquez avec le bouton droit pour sélectionner **[!UICONTROL Modifier les mesures]**. Vous pouvez également cliquer sur **[!UICONTROL Gérer]** > **[!UICONTROL Modifier plusieurs]** > **`<choose metric>`** > **[!UICONTROL Modifier le groupe]** pour sélectionner le groupe de requêtes à modifier.

1. Sélectionnez **[!UICONTROL Supprimer des mesures]**.

   ![Capture d’écran montrant l’option Modifier le groupe et Supprimer les mesures sélectionnée.](assets/remove_metric.png)

1. Sélectionnez une ou plusieurs mesures à supprimer de la demande.
1. Actualisez la demande. Tant que vous n’avez pas actualisé, les données hors connexion s’affichent.
