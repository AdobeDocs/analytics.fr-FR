---
description: Découvrez comment copier une feuille de calcul d’un classeur source vers un ou plusieurs classeurs cibles.
title: Copie de requêtes et de feuilles de calcul entre des classeurs
uuid: 6b2c4259-d8cb-430e-819f-38e213dd2661
feature: Report Builder
role: User, Admin
exl-id: 1a2363da-603e-4d1d-aefa-14ce71554247
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 54%

---

# Copie de requêtes et de feuilles de calcul entre des classeurs

{{legacy-arb}}

Copiez une feuille de calcul entière dans un classeur source vers une feuille de calcul dans un ou plusieurs classeurs cibles. Pour ce faire, vous devez avoir ouvert au moins deux classeurs dans la même instance d&#39;Excel :

* Le premier classeur source contient une feuille de calcul (classeur) avec des requêtes mappées sur des cellules.

* Les classeurs cibles supplémentaires sont les destinations . Pour chaque nouveau classeur cible, vous devez vous connecter à la même suite de rapports que le classeur source avant de pouvoir coller des feuilles de calcul contenant des requêtes.

>[!NOTE]
>
>Vous devez vous connecter au classeur cible à l’aide de la même suite de rapports que le classeur source. Les requêtes des deux classeurs doivent être créées à l’aide du même nom d’utilisateur de suite de rapports.

1. Cliquez avec le bouton droit sur la feuille de calcul dans le classeur source, puis sélectionnez **[!UICONTROL Copier la feuille de calcul avec les requêtes]**.
1. Cliquez avec le bouton droit sur la feuille de calcul dans le classeur de destination, puis sélectionnez **[!UICONTROL Coller la feuille de calcul avec les requêtes]**.

   La même instance d’Excel signifie qu’un seul processus Excel ([!DNL excel.exe]) est en cours d’exécution sur l’ordinateur. Si vous lancez deux instances d&#39;Excel et que vous tentez de copier une feuille de calcul d&#39;un classeur de la première instance d&#39;Excel vers un classeur de la deuxième instance d&#39;Excel, Report Builder ne présente pas l&#39;option permettant de coller une feuille de calcul dans le menu contextuel de la deuxième instance d&#39;Excel.

   Si vous vous connectez aux classeurs source et cible avec des suites de rapports différentes, les seuls résultats de l’opération de collage sont ceux qui affectent la mise en forme du classeur cible. Le Report Builder affiche un message stipulant que les informations sur les requêtes dérivées d’une suite de rapports particulière (dans le classeur source) ne sont pas disponibles dans le classeur cible. Pour révéler les requêtes collées dans le classeur cible, vous devez vous connecter au classeur cible à l’aide de la même suite de rapports que dans le classeur source.

   Vous pouvez copier et coller une ou plusieurs requêtes d’une feuille de calcul d’un classeur dans une feuille de calcul d’un autre classeur, à condition que le deuxième classeur soit ouvert sous la forme d’un autre document dans la même instance d’Excel. Les requêtes des deux classeurs doivent être créées à l’aide du même nom d’utilisateur de suite de rapports.
