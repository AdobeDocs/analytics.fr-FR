---
description: Découvrez comment copier une feuille de calcul d’un classeur source vers un ou plusieurs classeurs cibles.
title: Copie de requêtes et de feuilles de calcul entre des classeurs
uuid: 6b2c4259-d8cb-430e-819f-38e213dd2661
feature: Report Builder
role: User, Admin
exl-id: 1a2363da-603e-4d1d-aefa-14ce71554247
TQID: https://experienceleague.adobe.com/0GVqb80fMIVJlip2dWGgzllmCGG2Hc8368WZlThzzh0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 379
ht-degree: 21%

---

# Copie de requêtes et de feuilles de calcul entre des classeurs

{{legacy-arb}}

Copiez une feuille de calcul entière dans un classeur source vers une feuille de calcul dans un ou plusieurs classeurs cibles. Pour ce faire, vous devez avoir ouvert au moins deux classeurs dans la même instance d&#39;Excel :

* Le premier classeur source contient une feuille de calcul (classeur) avec des requêtes mappées sur des cellules.

* Les classeurs cibles supplémentaires sont les destinations . Pour chaque nouveau classeur cible, vous devez vous connecter à la même suite de rapports que le classeur source avant de pouvoir coller des feuilles de calcul contenant des requêtes.

>[!NOTE]
>
>Vous devez vous connecter au classeur cible à l’aide de la même suite de rapports que le classeur source. Les requêtes des deux classeurs doivent être créées à l’aide de la même connexion à la suite de rapports.

1. Cliquez avec le bouton droit sur la feuille de calcul dans le classeur source, puis sélectionnez **[!UICONTROL Copier la feuille de calcul avec les requêtes]**.
1. Cliquez avec le bouton droit sur la feuille de calcul dans le classeur de destination, puis sélectionnez **[!UICONTROL Coller la feuille de calcul avec les requêtes]**.

   La même instance d’Excel signifie qu’un seul processus Excel ([!DNL excel.exe]) est en cours d’exécution sur l’ordinateur. Si vous lancez deux instances d&#39;Excel et que vous tentez de copier une feuille de calcul d&#39;un classeur de la première instance d&#39;Excel vers un classeur de la deuxième instance d&#39;Excel, Report Builder ne présente pas l&#39;option permettant de coller une feuille de calcul dans le menu contextuel de la deuxième instance d&#39;Excel.

   Si vous vous connectez aux classeurs source et cible à l’aide de suites de rapports différentes, les seuls résultats que vous voyez de l’opération de collage sont ceux qui affectent la mise en forme du classeur cible. Le Report Builder affiche un message stipulant que les informations sur les requêtes dérivées d’une suite de rapports particulière (dans le classeur source) ne sont pas disponibles dans le classeur cible. Pour afficher les requêtes collées dans le classeur cible, vous devez vous connecter au classeur cible à l’aide de la même suite de rapports que le classeur source.

   Vous pouvez copier et coller une ou plusieurs demandes d&#39;une feuille de calcul d&#39;un classeur vers une feuille de calcul d&#39;un autre classeur, à condition que le deuxième classeur soit ouvert comme un autre document dans la même instance d&#39;Excel. Les requêtes des deux classeurs doivent être créées à l’aide de la même connexion à la suite de rapports.
