---
description: valeur nulle
seo-description: valeur nulle
seo-title: Bonnes pratiques
title: Bonnes pratiques
uuid: 6 d 55 a 9 aa -030 e -4 e 4 d -963 c-ec 9 cc 38 e 1731
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Bonnes pratiques

## Préserver les références dans les visualisations Power BI {#section_7ED14FE64D974681A57EB91EF1B47CB6}

Une fois que vous créez une requête, celle-ci aura toujours la même référence dans Power BI. Mais si vous la supprimez, la référence sera utilisée par une nouvelle requête que vous créez pour la même dimension.

Si vous supprimez une requête dans votre classeur, assurez-vous qu’aucune visualisation ne pointe vers cette requête dans Power BI, sinon la visualisation sera corrompue.

* Dans la mesure du possible, ne supprimez pas les requêtes que vous avez créées dans le Créateur de rapports
* Si vous supprimez des requêtes dans le Créateur de rapports, veillez à supprimer également la visualisation correspondante dans Power BI.
* Si vous n’êtes pas sûr de vous : supprimez les requêtes dont vous n’avez plus besoin, puis republiez et accédez à Power BI pour voir quelles visualisations ont été corrompues

