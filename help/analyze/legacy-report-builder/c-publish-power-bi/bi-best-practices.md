---
description: Bonnes pratiques relatives à Power BI.
title: Bonnes pratiques
feature: Report Builder
role: User, Admin
exl-id: 2d9447f4-77ac-465b-af93-206dc3ea80f7
TQID: https://experienceleague.adobe.com/WXvRDft1TRz5qM9R8Psz-Yp2qY-AL-SrrXgXWRx55N0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 139
ht-degree: 55%

---

# Bonnes pratiques

{{legacy-arb}}

## Préserver les références dans les visualisations Power BI

Une fois une demande créée, elle aura toujours la même référence dans Power BI. Cependant, si vous supprimez une demande, la référence sera utilisée par une nouvelle demande que vous créerez pour la même dimension.

Si vous supprimez une requête dans votre classeur, assurez-vous qu’aucune visualisation ne pointe vers cette requête dans Power BI, sinon la visualisation sera corrompue.

* Dans la mesure du possible, ne supprimez pas les requêtes que vous avez créées dans le Report Builder
* Si vous supprimez des requêtes dans le Report Builder, veillez à supprimer également la visualisation correspondante dans Power BI.
* En cas de doute : supprimez les requêtes dont vous n’avez plus besoin, puis republiez et accédez à Power BI pour identifier les visualisations qui ont échoué
