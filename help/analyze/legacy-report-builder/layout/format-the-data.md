---
description: Découvrez comment appliquer une mise en forme standard et limitée aux plages de cellules.
title: Comment formater la date dans Report Builder
uuid: 5211db30-07b3-4413-97c3-e40e6ff223cd
feature: Report Builder
role: User, Admin
exl-id: 9b251b09-9156-40b5-8e1f-fb6594a25c26
TQID: https://experienceleague.adobe.com/8FuosvmSvi-bRNaG5QbwUExuDffOIXbrkuiQLh0NZXM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 271
ht-degree: 23%

---

# Mise en forme de la date

{{legacy-arb}}

Outre les choix de mise en forme de cellule standard disponibles dans la fonction Format > Cellules (Ctrl+1) d&#39;Excel, vous pouvez appliquer une mise en forme limitée aux plages de cellules à l&#39;aide de Report Builder. Ces choix de mise en forme dépendent de la mesure que vous avez choisie.

Après avoir [ajouté des dimensions](/help/analyze/legacy-report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) à la grille Libellés de lignes, cliquez sur **[!UICONTROL Format]**.

Dans le menu **[!UICONTROL Format]**, cliquez sur **[!UICONTROL Format personnalisé]** pour appliquer des formats personnalisés aux dates ; de la même manière que la fonction d’ajout de texte en préfixe ou suffixe. Par exemple, vous pouvez saisir du texte qui se produit toujours après la date (tel que A.D. B.C.E. A.H., etc.). Vous pouvez ajouter du texte avant la date, par exemple [!UICONTROL Date de début] et [!UICONTROL Date de début et de fin]. En outre, vous pouvez créer une expression de date personnalisée à partir des abréviations jour, mois et année, et utiliser un séparateur personnalisé entre les parties de la date. Tous les formats de date doivent être composés de trois abréviations uniquement comprises entre crochets.

Le tableau suivant décrit l’utilisation d’abréviations de date dans le champ [!UICONTROL Format personnalisé] :

| Abréviation | Signification | Exemple avec le mercredi 14 mars 2012 |
|--- |--- |--- |
| jj/MM/aaa | Date numérique complète | 03/14/2012 |
| M | Nombre de mois | 3 |
| MM | Nombre de mois avec 0 marge intérieure pour les mois &lt; 10 | 03 |
| MMM | Nom abrégé du mois | Mar |
| MMMM | Nom long du mois | Mars |
| D | Nom long de la date | jeudi 14 mars 2012 |
| j | Nombre de jours | 14 |
| jj | Nombre de jours avec une marge intérieure de 0 pour les jours &lt; 10 | 01 - 09 |
| jjj | Nom abrégé du jour | Mer. |
| jjjj | Nom long du jour | Mercredi |
| aa | année à 2 chiffres | 10 |
| aaaa | Année complète à 4 chiffres | 2012 |
