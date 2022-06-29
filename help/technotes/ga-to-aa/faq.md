---
title: Questions fréquentes sur la migration vers Adobe Analytics
description: Obtenez des réponses aux questions fréquentes lorsque vous passez d’une plateforme tierce à Adobe.
feature: Third-party Integration
exl-id: 1201909e-b20c-48c5-b287-393da8e22d78
source-git-commit: 1192a6a1e14e43aa2b434ac0b2675c73d249214a
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Questions fréquentes sur la migration vers Adobe Analytics

**Comment puis-je migrer mes données historiques de ma plateforme tierce vers Adobe Analytics ?**

Chaque plateforme Analytics dispose de différentes méthodes de collecte, de gestion et de stockage des données. Plutôt que de procéder à la migration des données historiques, Adobe recommande d’établir une date de bascule claire pour commencer à collecter et à utiliser des données dans Adobe Analytics. Les dates de bascule classiques sont : le début d’une année fiscale, le début d’une année civile ou le début d’un mois civil. Si les utilisateurs souhaitent afficher des données historiques, ils peuvent se connecter à la plateforme tierce pour obtenir des rapports historiques spécifiques.

Si votre entreprise insiste pour que les données historiques soient transférées à Adobe, contactez le gestionnaire de compte de votre entreprise. Un conseiller en implémentation peut travailler avec votre entreprise pour traduire une exportation de données Google Analytics en une source de données pouvant être assimilée par les serveurs de collecte de données d’Adobe.

Pour passer aux données historiques, il est recommandé d’utiliser [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=fr) qui peut importer n’importe quelle source de données omni-canal.

**Je suis habitué à une liste déroulante de segmentation dans la plupart de mes rapports. Comment puis-je recréer cela dans [!UICONTROL Analysis Workspace] ?**

Les filtres déroulants sont une fonctionnalité flexible et robuste d’[!UICONTROL Analysis Workspace] qui permet d’avoir une liste déroulante de segments. Dans un projet Workspace :

1. Utilisez ctrl+clic (Windows) ou cmd+clic (Mac) sur les composants que vous souhaitez inclure dans la liste déroulante. Vous n’êtes pas limité aux segments ; tout composant peut être inclus dans un filtre déroulant.
2. Faites glisser le groupe de composants dans la zone de l’espace de travail intitulée « Déposer un segment ici ». Avant de relâcher, maintenez la touche Maj enfoncée.

Les utilisateurs accédant à ce projet [!UICONTROL Workspace] peuvent désormais utiliser cette liste déroulante pour appliquer des segments ou d’autres composants au projet. Pour plus d’informations, consultez la [Présentation des panneaux](/help/analyze/analysis-workspace/c-panels/panels.md) dans le guide sur les outils Analytics.

**J’ai l’habitude de cliquer sur l’élément d’une dimension pour qu’une analyse en profondeur s’affiche. Comment puis-je recréer ce processus simple dans Analysis Workspace ?**

Les éléments de dimension dans [!UICONTROL Analysis Workspace] offrent également un processus de ventilation facile. Accédez-y avec un clic droit au lieu d’un clic gauche. Faites un clic droit sur un élément de dimension, cliquez sur **[!UICONTROL Ventilation], puis sélectionnez le composant de votre choix. Vous pouvez appliquer la même ventilation à plusieurs éléments de dimension en faisant ctrl+clic (Windows) ou cmd+clic (Mac) sur chaque valeur.
