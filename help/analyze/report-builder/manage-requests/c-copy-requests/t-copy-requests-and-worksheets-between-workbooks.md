---
description: Vous pouvez copier une feuille de calcul entière d’un classeur source dans une feuille de calcul d’un ou de plusieurs classeurs cibles.
seo-description: Vous pouvez copier une feuille de calcul entière d’un classeur source dans une feuille de calcul d’un ou de plusieurs classeurs cibles.
seo-title: Copie de requêtes et de feuilles de calcul entre des classeurs
solution: Analytics
title: Copie de requêtes et de feuilles de calcul entre des classeurs
topic: Créateur de rapports
uuid: 6 b 2 c 4259-d 8 cb -430 e -819 f -38 e 213 dd 2661
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Copie de requêtes et de feuilles de calcul entre des classeurs

Vous pouvez copier une feuille de calcul entière d’un classeur source dans une feuille de calcul d’un ou de plusieurs classeurs cibles.

Pour ce faire, au moins deux classeurs doivent être ouverts dans la même instance d’Excel : le premier classeur source contient une feuille de calcul avec les requêtes en correspondance avec les cellules, tandis que les classeurs cibles supplémentaires sont les destinations. Pour chaque nouveau classeur cible, vous devez   vous connecter à la même suite de rapports que le classeur source avant de pouvoir coller les feuilles de calcul contenant les requêtes.
1. Cliquez avec le bouton droit sur la feuille de calcul dans le classeur source, puis sélectionnez **[!UICONTROL Copier la feuille de calcul avec les requêtes]**.
1. Cliquez avec le bouton droit sur la feuille de calcul dans le classeur de destination, puis sélectionnez **[!UICONTROL Coller la feuille de calcul avec les requêtes]**.

   La même instance d’Excel signifie qu’un seul processus Excel ([!DNL excel.exe]) est en cours d’exécution sur l’ordinateur. Si deux instances d’Excel sont en cours d’exécution et que vous tentez de copier une feuille de calcul d’un classeur de la première instance dans un classeur de la deuxième instance, l’option de collage d’une feuille de calcul du Créateur de rapports n’apparaît pas dans le menu contextuel de la deuxième instance d’Excel.

   Si vous vous connectez aux classeurs source et cible avec des suites de rapports différentes, les seuls résultats de l’opération de collage sont ceux qui affectent la mise en forme du classeur cible. Le Créateur de rapports affiche un message stipulant que les informations sur les requêtes dérivées d’une suite de rapports particulière (dans le classeur source) ne sont pas disponibles dans le classeur cible. Pour révéler les requêtes collées dans le classeur cible, vous devez vous connecter au classeur cible à l’aide de la même suite de rapports que dans le classeur source.

   Vous pouvez copier et coller une ou plusieurs requêtes d’une feuille de calcul d’un classeur dans une feuille de calcul d’un autre classeur, à condition que le deuxième classeur soit ouvert sous la forme d’un autre document dans la même instance d’Excel. Les requêtes des deux classeurs doivent être créées à l’aide du même nom d’utilisateur de suite de rapports.
