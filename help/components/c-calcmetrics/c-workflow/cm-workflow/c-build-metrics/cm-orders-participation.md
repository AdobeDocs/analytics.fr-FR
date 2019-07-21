---
description: Explique comment créer une mesure qui indique les canaux marketing aidant au pilotage des commandes. Cette procédure peut être adaptée à toute dimension ou tout événement de succès.
seo-description: Explique comment créer une mesure qui indique les canaux marketing aidant au pilotage des commandes. Cette procédure peut être adaptée à toute dimension ou tout événement de succès.
seo-title: Mesure Aide à la commande
title: Mesure Aide à la commande
uuid: 7 c 82227 a -7 fcc -486 f-bef 8-164 ea 84 af 77 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Mesure Aide à la commande

Explique comment créer une mesure qui indique les canaux marketing aidant au pilotage des commandes. Cette procédure peut être adaptée à toute dimension ou tout événement de succès.

1. Dans le créateur de mesures calculées, nommez la mesure « Commandes assistées ».
1. Dans le canevas Définition, faites glisser une mesure Commandes. Ensuite, ajustez le modèle d’attribution par le biais de l’icône engrenage des paramètres en cochant la case **[!UICONTROL Utiliser des modèles d’attribution qui ne sont pas par défaut].**

   ![](assets/attr-model.png)

1. Sélectionnez **[!UICONTROL Personnalisé]en tant que modèle d’attribution.** Changez les poids en 0 (démarrage), 100 (joueur) et 0 (le plus proche).

   ![](assets/custom-attr-model.png)

1. Enregistrez la mesure.
1. Créez un tableau à structure libre dans Analysis Workspace avec la dimension Canaux marketing, Commandes et la nouvelle mesure Commandes assistées.

   ![](assets/mktg-channel-assists.png)

C’est un moyen facile d’indiquer les canaux marketing qui ont aidé au pilotage des commandes. Vous pouvez également, dans un tableau à structure libre, cliquer avec le bouton droit sur une mesure et ajuster directement le modèle d’attribution depuis le tableau.
