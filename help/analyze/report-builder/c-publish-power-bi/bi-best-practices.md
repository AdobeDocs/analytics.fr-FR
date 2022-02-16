---
description: Bonnes pratiques relatives aux Power BI.
title: Bonnes pratiques
feature: Report Builder
role: User, Admin
exl-id: 2d9447f4-77ac-465b-af93-206dc3ea80f7
source-git-commit: 1ee50c6a2231795b2ad0015a79e09b7c1c74d850
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 97%

---

# Bonnes pratiques

## Préserver les références dans les visualisations Power BI {#section_7ED14FE64D974681A57EB91EF1B47CB6}

Une fois que vous créez une requête, celle-ci aura toujours la même référence dans Power BI. Mais si vous la supprimez, la référence sera utilisée par une nouvelle requête que vous créez pour la même dimension.

Si vous supprimez une requête dans votre classeur, assurez-vous qu’aucune visualisation ne pointe vers cette requête dans Power BI, sinon la visualisation sera corrompue.

* Dans la mesure du possible, ne supprimez pas les requêtes que vous avez créées dans le Report Builder
* Si vous supprimez des requêtes dans le Report Builder, veillez à supprimer également la visualisation correspondante dans Power BI.
* Si vous n’êtes pas sûr de vous : supprimez les requêtes dont vous n’avez plus besoin, puis republiez et accédez à Power BI pour voir quelles visualisations ont été corrompues
