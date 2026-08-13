---
description: Découvrez comment copier des requêtes référentielles.
title: Copie de requêtes référentielles
feature: Report Builder
role: User, Admin
exl-id: 3cd77325-7461-4345-a672-64c03ea1ae5b
TQID: https://experienceleague.adobe.com/A-ef3rd0b7WMBRqBgmxFWpa35x8R7qYF1dMkF5gx5Ec
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 533
ht-degree: 23%

---

# Copie de requêtes référentielles

{{legacy-arb}}

Une requête référentielle utilise les valeurs des cellules comme entrée de paramètres, tel un filtre de données ou un filtre relationnel.

Pour propager ou copier et coller des requêtes référentielles dans la feuille de calcul :

* Vous devez créer au moins une demande valide dans la feuille de calcul.

* Les données produites par la requête doivent contenir une cellule dont la valeur dépend soit d’une requête dans une autre cellule (à l’aide d’un filtre de répartition ou de correspondance), soit d’un filtre qui prend en compte les données saisies dans une cellule.

Vous pouvez également créer des requêtes qui référencent des filtres d’entrée à partir de requêtes dans différentes feuilles de calcul, mais pas dans différents classeurs. Par exemple, une requête de la feuille 2 peut utiliser une suite de rapports provenant d’une cellule donnée de la feuille 1 et une période provenant d’une cellule d’une requête de la feuille 2. La nouvelle sortie peut être placée dans une feuille ou dans une nouvelle feuille du même classeur. Lorsque vous collez une requête relative, si un filtre d’entrée réside sur une feuille de calcul différente de celle sur laquelle se trouve la sortie de requête copiée, le filtre est collé en tant que filtre absolu.

>[!NOTE]
>
>Vous ne pouvez pas générer une seule demande dans plusieurs feuilles de calcul. En outre, le système ne peut pas coller certaines des requêtes copiées dans de nouveaux classeurs, car les requêtes contiennent des filtres d’entrée provenant d’autres feuilles de calcul. Les filtres d’entrée incluent les suites de rapports des cellules, les périodes des cellules, les filtres des cellules et d’autres paramètres associés.

**Pour copier des requêtes référentielles**

1. Sélectionnez les cellules contenant les requêtes à copier, y compris la cellule d’entrée ou la cellule référencée.
1. Cliquez avec le bouton droit dans les cellules en surbrillance, puis sélectionnez **[!UICONTROL Copier les requêtes]** dans le menu contextuel.

   Après avoir sélectionné la zone où résident les requêtes et cellules d’entrée, le système surligne les cellules contenant ces éléments.
1. Sélectionnez l’une des cellules ou une plage de cellules contiguës à remplir avec les requêtes collées.

   Assurez-vous que la cellule ou plage de cellules sélectionnée ne contient aucune autre donnée ou requête.
1. Cliquez avec le bouton droit sur la cellule unique ou sur la cellule la plus en haut à gauche de la plage de cellules, puis sélectionnez **[!UICONTROL Coller les requêtes]**.

   Lors du collage de requêtes qui incluent une cellule d’entrée, les options disponibles sous [!UICONTROL Coller les requêtes] sont les suivantes :

   **Utiliser la cellule d’entrée absolue :** colle une copie de la ou des requêtes et de la mise en forme associées aux cellules sélectionnées dans la zone de collage que vous mettez en surbrillance. La cellule d’entrée (la cellule à laquelle fait référence l’une des requêtes d’origine) n’est pas collée. Au lieu de cela, la cellule d’entrée reste dans la même position que précédemment.

   **Utiliser la cellule d’entrée relative :** colle une copie de la ou des requêtes et de la mise en forme associées aux cellules sélectionnées dans la zone de collage que vous avez mise en surbrillance, y compris une copie de la cellule d’entrée. La relation spatiale de la ou des requêtes avec la cellule d’entrée est la même que dans la ou les requêtes d’origine. Cependant, bien que les cellules nouvellement collées disposent désormais d’une copie des requêtes, elles n’ont initialement aucun contenu. En effet, lorsque la cellule d’entrée est recréée lors de l’opération de collage, aucune donnée n’est associée à la cellule d’entrée. Pour afficher les données de la ou des requêtes nouvellement collées, vous devez saisir une valeur dans la cellule d’entrée, puis actualiser la ou les requêtes.
