---
description: Bonnes pratiques relatives à Power BI.
title: Bonnes pratiques
feature: Report Builder
role: User, Admin
exl-id: 2d9447f4-77ac-465b-af93-206dc3ea80f7
source-git-commit: 12d048b42c6a61e03dbbe73acb9d34df3e37693c
workflow-type: tm+mt
source-wordcount: '139'
ht-degree: 100%

---

# Bonnes pratiques

## Préserver les références dans les visualisations Power BI

Une fois que vous créez une requête, celle-ci aura toujours la même référence dans Power BI. Mais si vous la supprimez, la référence sera utilisée par une nouvelle requête que vous créez pour la même dimension.

Si vous supprimez une requête dans votre classeur, assurez-vous qu’aucune visualisation ne pointe vers cette requête dans Power BI, sinon la visualisation sera corrompue.

* Dans la mesure du possible, ne supprimez pas les requêtes que vous avez créées dans le Report Builder
* Si vous supprimez des requêtes dans le Report Builder, veillez à supprimer également la visualisation correspondante dans Power BI.
* Si vous n’êtes pas sûr de vous : supprimez les requêtes dont vous n’avez plus besoin, puis republiez et accédez à Power BI pour voir quelles visualisations ont été corrompues
