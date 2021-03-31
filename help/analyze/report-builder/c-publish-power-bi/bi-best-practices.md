---
description: bonnes pratiques Power BI.
title: Bonnes pratiques
uuid: 6d55a9aa-030e-4e4d-963c-ec9cc38e1731
feature: Report Builder
role: Professionnel, Administrateur
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 95%

---


# Bonnes pratiques

## Préserver les références dans les visualisations Power BI {#section_7ED14FE64D974681A57EB91EF1B47CB6}

Une fois que vous créez une requête, celle-ci aura toujours la même référence dans Power BI. Mais si vous la supprimez, la référence sera utilisée par une nouvelle requête que vous créez pour la même dimension.

Si vous supprimez une requête dans votre classeur, assurez-vous qu’aucune visualisation ne pointe vers cette requête dans Power BI, sinon la visualisation sera corrompue.

* Dans la mesure du possible, ne supprimez pas les requêtes que vous avez créées dans le Report Builder
* Si vous supprimez des requêtes dans le Report Builder, veillez à supprimer également la visualisation correspondante dans Power BI.
* Si vous n’êtes pas sûr de vous : supprimez les requêtes dont vous n’avez plus besoin, puis republiez et accédez à Power BI pour voir quelles visualisations ont été corrompues

