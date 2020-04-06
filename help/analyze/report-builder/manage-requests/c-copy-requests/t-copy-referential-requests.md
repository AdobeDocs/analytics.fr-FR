---
description: Une requête référentielle utilise les valeurs des cellules comme entrée de paramètres, tel un filtre de données ou un filtre relationnel.
title: Copie de requêtes référentielles
topic: Report builder
uuid: b6f64630-868f-455b-8682-471ff9fc596e
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Copie de requêtes référentielles

Une requête référentielle utilise les valeurs des cellules comme entrée de paramètres, tel un filtre de données ou un filtre relationnel.

Pour propager ou copier et coller des requêtes référentielles dans la feuille de calcul, vous devez avoir créé au moins une requête valide dans la feuille de calcul. En outre, les données générées par la requête doivent contenir une cellule dont la valeur dépend d’une requête dans une autre cellule (à l’aide d’une ventilation ou d’un filtre correspondant) ou d’un filtre qui prend l’entrée des données saisies dans une cellule.

Vous pouvez également créer des requêtes qui référencent des d’entrée à partir de requêtes dans différentes feuilles de calcul, mais pas dans des classeurs différents. Par exemple, une requête de la feuille 2 peut utiliser une suite de rapports d’une cellule donnée de la feuille 1 et une plage de dates d’une cellule d’une requête de la feuille 2. La nouvelle sortie peut être placée dans une feuille ou dans une nouvelle feuille du même classeur. Lorsque vous collez une requête relative, si un filtre d’entrée réside dans une feuille de calcul différente de celle sur laquelle se trouve la sortie de la requête copiée, le filtre est collé en tant que filtre absolu.

>[!NOTE] Vous ne pouvez pas générer les résultats d’une requête dans plusieurs feuilles de calcul. En outre, le système ne peut pas coller certaines des requêtes copiées dans de nouveaux classeurs, car elles contiennent des  d’entrée provenant d’autres feuilles de calcul. Les  d’entrée comprennent les suites de rapports des cellules, les plages de dates des cellules, les  des cellules et d’autres paramètres connexes.

**Pour copier des requêtes référentes**

1. Sélectionnez les cellules contenant les requêtes à copier, y compris la cellule d’entrée ou la cellule référencée.
1. Right-click within the highlighted cells and select **[!UICONTROL Copy Requests]** from the shortcut menu.

   Après avoir sélectionné la zone où résident les requêtes et cellules d’entrée, le système surligne les cellules contenant ces éléments.
1. Sélectionnez l’une des cellules ou une plage de cellules contiguës à remplir avec les requêtes collées.

   Assurez-vous que la cellule ou plage de cellules sélectionnée ne contient aucune autre donnée ou requête.
1. Right-click the single cell or the top left-most cell in the range of cells and select **[!UICONTROL Paste Requests]**.

   Lors du collage de requêtes qui incluent une cellule d’entrée, les options sous [!UICONTROL Paste Requests] incluent :

   **Utiliser la cellule d’entrée absolue :** Colle une copie des requêtes et du formatage associé aux cellules sélectionnées dans la zone de collage en surbrillance. La cellule d’entrée (cellule référencée dans l’une des requêtes d’origine) n’est pas collée. La cellule d’entrée reste dans la même position qu’auparavant.

   **Utiliser la cellule d’entrée relative :** Colle une copie des requêtes et du formatage associés aux cellules sélectionnées dans la zone de collage en surbrillance, y compris une copie de la cellule d’entrée. La relation spatiale des requêtes avec la cellule d’entrée est la même que dans la ou les requêtes d’origine. Toutefois, bien que les cellules nouvellement collées aient désormais une copie des requêtes, elles n’ont pas de contenu au départ. En effet, lorsque la cellule d’entrée est recréée dans l’opération de collage, aucune donnée n’est associée à la cellule d’entrée. Pour afficher les données des requêtes nouvellement collées, vous devez saisir une valeur dans la cellule d’entrée, puis actualiser la ou les requêtes.
