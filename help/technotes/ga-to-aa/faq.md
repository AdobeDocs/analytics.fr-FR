---
title: Questions fréquentes concernant la migration vers Adobe Analytics
description: Obtenez des réponses aux questions fréquentes lorsque vous passez d’une plateforme tierce à Adobe.
feature: Third-party Integration
exl-id: 1201909e-b20c-48c5-b287-393da8e22d78
source-git-commit: 58d53d6013abcd7d99f2c3cb640d6a648a4ef360
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 53%

---

# Questions fréquentes concernant la migration vers Adobe Analytics

**Comment puis-je migrer mes données historiques de ma plateforme tierce vers Adobe Analytics ?**

Chaque plateforme Analytics dispose de différentes méthodes de collecte, de gestion et de stockage des données. Plutôt que de procéder à la migration des données historiques, Adobe recommande d’établir une date de bascule claire pour commencer à collecter et à utiliser des données dans Adobe Analytics. Les dates de bascule classiques sont : le début d’une année fiscale, le début d’une année civile ou le début d’un mois civil. Si les utilisateurs souhaitent afficher des données historiques, ils peuvent se connecter à la plateforme tierce pour obtenir des rapports historiques spécifiques.

Si votre organisation est catégorique sur la nécessité de transférer les données historiques vers Adobe, contactez l’équipe chargée de votre compte Adobe. Un conseiller en implémentation peut travailler avec votre entreprise pour traduire une exportation de données Google Analytics en une source de données pouvant être assimilée par les serveurs de collecte de données d’Adobe.

Pour transférer les données historiques, il est recommandé d’utiliser [Customer Journey Analytics](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-overview) qui peut importer n’importe quelle source de données omnicanale.

**Je suis habitué à une liste déroulante de segmentation dans de nombreux de mes rapports. Comment puis-je recréer cela dans [!UICONTROL Analysis Workspace] ?**

Les filtres déroulants sont une fonctionnalité flexible et robuste d’[!UICONTROL Analysis Workspace] qui permet d’obtenir une liste déroulante de segmentation. Dans un projet Workspace :

1. Utilisez ***ctrl***+***clic*** (Windows) ou ***cmd***+***clic*** (Mac) sur les composants que vous souhaitez inclure dans le filtre déroulant. Vous ne vous limitez pas aux segments. N’importe quel composant peut être inclus dans un filtre déroulant.
2. Faites glisser le groupe de composants dans la zone de l’espace de travail intitulée *Déposez un segment ici*. Avant de lâcher prise, maintenez **[!UICONTROL Maj]**.

Les utilisateurs et utilisatrices accédant à ce projet [!UICONTROL Workspace] peuvent désormais utiliser ce filtre déroulant pour appliquer des segments ou d’autres composants au projet. Pour plus d’informations, consultez la [Présentation des panneaux](/help/analyze/analysis-workspace/c-panels/panels.md) dans le guide sur les outils Analytics.

**J’ai l’habitude de cliquer sur l’élément d’une dimension pour qu’une analyse en profondeur s’affiche. Comment puis-je recréer ce processus simple dans Analysis Workspace ?**

Les éléments de dimension dans [!UICONTROL Analysis Workspace] offrent également un processus de répartition facile. Accédez à la répartition à l’aide du menu contextuel sur un élément de dimension. Sélectionnez ensuite **[!UICONTROL Répartition]**, puis le composant de votre choix. Vous pouvez appliquer la même répartition à plusieurs éléments de dimension à l’aide des combinaisons ***ctrl***+***select*** (Windows) ou ***cmd***+***select*** (Mac) sur chaque valeur.
