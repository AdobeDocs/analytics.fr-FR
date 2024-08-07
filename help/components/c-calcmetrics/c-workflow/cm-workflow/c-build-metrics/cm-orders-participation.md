---
description: Explique comment créer une mesure qui indique les canaux marketing aidant au pilotage des commandes. Cette procédure peut être adaptée à toute dimension ou tout événement de succès.
title: Mesure Aide à la commande
feature: Calculated Metrics
exl-id: 33cb441d-d003-408d-ba67-1bcdd0e821ff
source-git-commit: 7722a2f01ff77dfec8ce110fd04fe977f6c627c6
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 59%

---

# Créer une mesure « Aide à la commande »

Les informations suivantes expliquent comment créer une mesure qui indique les canaux marketing qui aident à piloter les commandes. Cette procédure peut être adaptée à toute dimension ou tout événement de succès.

1. Commencez à créer une mesure calculée, comme décrit dans [Créer des mesures](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md).

1. Dans le créateur de mesures calculées, nommez la mesure &quot;Commandes assistées&quot; ou quelque chose de similaire.

1. Dans le canevas Définition, faites glisser une mesure Commandes. Ensuite, ajustez le modèle d’attribution par le biais de l’icône engrenage des paramètres en cochant la case **[!UICONTROL Utiliser des modèles d’attribution qui ne sont pas par défaut]**.

   ![](assets/attr-model.png)

1. Sélectionnez **[!UICONTROL Personnalisé]** en tant que modèle d’attribution. Changez les poids en 0 (démarrage), 100 (joueur) et 0 (le plus proche).

   ![](assets/custom-attr-model.png)

1. Sélectionnez [!UICONTROL **Apply**] > [!UICONTROL **Save**].

1. Dans Analysis Workspace, créez un tableau à structure libre avec la dimension Canal marketing, Commandes et la nouvelle mesure Commandes assistées .

   ![](assets/mktg-channel-assists.png)

   C’est un moyen facile d’indiquer les canaux marketing qui ont aidé au pilotage des commandes. Vous pouvez également, dans un tableau à structure libre, cliquer avec le bouton droit sur une mesure et ajuster directement le modèle d’attribution depuis le tableau.

1. (Facultatif) Partagez la mesure avec d’autres utilisateurs de votre entreprise, comme décrit dans la section [Partager les mesures calculées](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-sharing.md).
