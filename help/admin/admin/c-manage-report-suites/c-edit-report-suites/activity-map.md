---
description: Activez les dimensions afin qu’Activity Map puisse collecter des données.
title: Rapports d’Activity Map
feature: Admin Tools
exl-id: 9300c12e-3ade-4850-8a22-cba61b35ca67
source-git-commit: 24101efe2b860734c9d176ba8be8f17e26429442
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 3%

---

# Rapports d’Activity Map

Permet d’activer des dimensions à utiliser avec [Activity Map](/help/analyze/activity-map/overview.md).

**[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]** > Sélectionner une suite de rapports > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Rapports Activity Map]**

Cette section de la documentation porte sur l’activation des dimensions utilisées par Activity Map. Consultez [Présentation d’Activity Map](/help/analyze/activity-map/overview.md) pour plus d’informations sur le recouvrement, les variables d’implémentation et les dimensions.

Lorsque vous cliquez sur le bouton **[!UICONTROL Activer les rapports Activity Map]**, les dimensions suivantes sont créées :

* [[!UICONTROL Lien Activity Map &#x200B;]](/help/components/dimensions/activity-map-link.md) : nom du lien sur lequel l&#39;utilisateur a cliqué.
* [[!UICONTROL Région Activity Map &#x200B;]](/help/components/dimensions/activity-map-region.md) : nom de la région sur laquelle l’utilisateur a cliqué.
* [[!UICONTROL Page Activity Map &#x200B;]](/help/components/dimensions/activity-map-page.md) : nom de la page au moment où l’utilisateur a cliqué sur le lien.
* [[!UICONTROL Lien Activity Map par région &#x200B;]](/help/components/dimensions/activity-map-link-by-region.md) : valeur concaténée du lien Activity Map et de la région Activity Map.

Une fois activée, votre implémentation peut commencer à envoyer des données à ces dimensions pour les utiliser dans [Analysis Workspace](/help/analyze/analysis-workspace/home.md) et la superposition de l’extension de navigateur [Browser](/help/analyze/activity-map/overlay/overview.md).

>[!NOTE]
>
>Lorsque vous activez Activity Map pour une suite de rapports, il est activé de manière permanente sans aucun moyen de le désactiver à l’avenir.
