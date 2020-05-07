---
title: Questions fréquentes
description: Obtenez des réponses aux questions fréquentes lorsque vous passez d’une plateforme tierce à Adobe.
translation-type: tm+mt
source-git-commit: 3211598c2ff43493b329a9be4fb6877ae29cf08b
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 75%

---


# Questions fréquentes

**Comment puis-je migrer mes données historiques de ma plateforme tierce vers Adobe Analytics ?**

Chaque plateforme Analytics dispose de différentes méthodes de collecte, de gestion et de stockage des données. Plutôt que de procéder à la migration des données historiques, Adobe recommande d’établir une date de bascule claire pour commencer à collecter et à utiliser des données dans Adobe Analytics. Les dates de bascule classiques sont : le début d’une année fiscale, le début d’une année civile ou le début d’un mois civil. Si les utilisateurs souhaitent afficher des données historiques, ils peuvent se connecter à la plateforme tierce pour obtenir des rapports historiques spécifiques.

Si votre entreprise insiste pour que les données historiques soient transférées à Adobe, contactez le gestionnaire de compte de votre entreprise. Un conseiller en implémentation peut travailler avec votre entreprise pour traduire une exportation de données Google Analytics en une source de données pouvant être assimilée par les serveurs de collecte de données d’Adobe.

Adobe déconseille de transférer des données historiques, car il s’agit d’un processus complexe avec un coût prohibitif pour votre entreprise. L’identification des visiteurs est également impossible à transférer facilement vers Adobe, car les informations sur les visiteurs sont stockées dans différents cookies et dans différents formats entre plateformes.

**Je suis habitué à une liste déroulante de segmentation dans la plupart de mes rapports. How can I recreate that in[!UICONTROL Analysis Workspace]?**

Dropdown filters are a flexible and robust feature in [!UICONTROL Analysis Workspace] that allows a segmentation dropdown. Dans un projet Workspace :

1. Utilisez ctrl+clic (Windows) ou cmd+clic (Mac) sur les composants que vous souhaitez inclure dans la liste déroulante. Vous n’êtes pas limité aux segments ; tout composant peut être inclus dans un filtre déroulant.
2. Faites glisser le groupe de composants dans la zone de l’espace de travail intitulée « Déposer un segment ici ». Avant de relâcher, maintenez la touche Maj enfoncée.

Users accessing this [!UICONTROL Workspace] project can now use this dropdown to apply segments or other components to the project. See [Panels Overview](/help/analyze/analysis-workspace/c-panels/panels.md) in the Adobe Analytics Tools guide for more information.

**J’ai l’habitude de cliquer sur la valeur d’une dimension pour qu’une analyse en profondeur s’affiche. Comment puis-je recréer ce processus simple dans Analysis Workspace ?**

Les valeurs de dimension dans [!UICONTROL Analyse Workspace] ont également un processus de ventilation facile. Accédez-y en cliquant avec le bouton droit au lieu de cliquer avec le bouton gauche. Right-click on a dimension value, click **[!UICONTROL Breakdown], then select the desired component. Vous pouvez appliquer la même répartition pour plusieurs valeurs de dimension en faisant ctrl+clic (Windows) ou cmd+clic (Mac) sur chaque valeur.
