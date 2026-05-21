---
title: Page d’Activity Map
description: Nom de la page lorsqu’un utilisateur a cliqué sur un lien.
feature: Dimensions
role: User, Admin
exl-id: 8dc5d5a1-ee44-4c98-80fa-13dd1cf4edf2
TQID: https://experienceleague.adobe.com/WJ0uk-LqIABwehzzy79c2o1cd3EvI-AKUJ--vmLnKRE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 189
ht-degree: 6%

---

# Page d’Activity Map

La [dimension](overview.md) « Page Activity Map » affiche la page sur laquelle se trouvait un visiteur lorsqu’il a cliqué sur un lien. Vous pouvez utiliser cette dimension pour déterminer les pages qui contiennent les liens les plus consultés. Cette dimension est également utilisée par le recouvrement Activity Map pour déterminer les liens à afficher.

## Renseigner cette dimension avec des données

Cette dimension récupère les données du `c.a.activitymap.page` [Variable de données contextuelles](/help/implement/vars/page-vars/contextdata.md). Si votre implémentation utilise [&#128279;](/help/analyze/activity-map/overview.md), cette variable de données contextuelles collecte automatiquement les données lorsque l’utilisateur clique sur les liens.

Pour un lien donné sur lequel l’utilisateur a cliqué, cette variable de données contextuelles collecte la valeur de la dimension [Page](page.md). Si la dimension Page ne contient pas de valeur, la dimension [URL de la page](page-url.md) est utilisée à la place (de manière similaire à la version de secours utilisée par la dimension Page). Les données Activity Map sont généralement envoyées lors de l’accès suivant après l’utilisation d’un lien. Cette dimension vous permet de déterminer la valeur de la page lorsque l’utilisateur a cliqué sur le lien, au lieu de la valeur de la page lors de l’envoi des données.

## Éléments de dimension

Les éléments Dimension incluent toutes les valeurs trouvées dans la dimension [Page](page.md).
