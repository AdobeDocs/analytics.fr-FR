---
description: Activez les dimensions afin qu’Activity Map puisse collecter des données.
title: Rapports d’Activity Map
feature: Admin Tools
exl-id: 9300c12e-3ade-4850-8a22-cba61b35ca67
TQID: https://experienceleague.adobe.com/GiBhdUMAX5P9zxxDAVUZPcaeKpnezKvDn3MB0g95DH0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 170
ht-degree: 31%

---

# Rapports d’Activity Map

Permet d’activer des dimensions à utiliser avec [&#128279;](/help/analyze/activity-map/overview.md).

**[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]** > Sélectionner une suite de rapports > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Rapports Activity Map]**

Cette section de la documentation porte sur l’activation des dimensions utilisées par Activity Map. Consultez [Présentation d’](/help/analyze/activity-map/overview.md) pour plus d’informations sur le recouvrement, les variables d’implémentation et les dimensions.

Lorsque vous cliquez sur le bouton **[!UICONTROL Activer les rapports Activity Map]**, les dimensions suivantes sont créées :

* [[!UICONTROL Lien Activity Map]](/help/components/dimensions/activity-map-link.md) : nom du lien sur lequel la personne a cliqué.
* [[!UICONTROL Région Activity Map]](/help/components/dimensions/activity-map-region.md) : nom de la région sur laquelle la personne a cliqué.
* [[!UICONTROL Page Activity Map]](/help/components/dimensions/activity-map-page.md) : nom de la page au moment où la personne a cliqué sur le lien.
* [[!UICONTROL Lien Activity Map par région]](/help/components/dimensions/activity-map-link-by-region.md) : valeur concaténée du lien Activity Map et de la région Activity Map.

Une fois activée, votre implémentation peut commencer à envoyer des données à ces dimensions pour les utiliser dans [&#128279;](/help/analyze/analysis-workspace/home.md) et la superposition de l’extension de navigateur [Browser](/help/analyze/activity-map/overlay/overview.md).

>[!NOTE]
>
>Lorsque vous activez Activity Map pour une suite de rapports, il est activé de manière permanente sans aucun moyen de le désactiver à l’avenir.
