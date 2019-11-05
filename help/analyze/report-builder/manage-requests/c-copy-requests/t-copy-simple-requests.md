---
description: Copiez une requête simple plutôt qu’une requête référentielle. Une requête simple ne contient aucune référence à une autre requête, ni au contenu d’une cellule.
seo-description: Copiez une requête simple plutôt qu’une requête référentielle. Une requête simple ne contient aucune référence à une autre requête, ni au contenu d’une cellule.
seo-title: Copie de requêtes simples
solution: Analytics
title: Copie de requêtes simples
topic: Créateur de rapports
uuid: ff20560a-01ee-47e7-8bd1-b73edb010456
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Copie de requêtes simples

Copiez une requête simple plutôt qu’une requête référentielle. Une requête simple ne contient aucune référence à une autre requête, ni au contenu d’une cellule.

A [referential request](/help/analyze/report-builder/manage-requests/c-copy-requests/t-copy-referential-requests.md) uses values from cells as input for parameters, such as a data filter or relational filter. Ces filtres appliquent la mise en correspondance ou les tendances et se fondent sur les résultats d’une requête antérieure ou sur le contenu d’une cellule saisi par l’utilisateur, appelé cellule d’entrée. 
1. Créez une requête valide.
1. Cliquez avec le bouton droit sur l’une des cellules où la requête est mise en correspondance ou sélectionnez une région de cellules contenant des requêtes.

   Restez cohérent lorsque vous sélectionnez une cellule à copier parmi un groupe de cellules couvert par la requête. Il est préférable de sélectionner la cellule la plus en haut à gauche du jeu de cellules et de travailler de gauche à droite. En effet, la feuille de calcul Excel contient des centaines de colonnes et des milliers de lignes extensibles vers la droite et vers le bas. Par conséquent, si vous commencez la copie d’une requête à partir de la cellule la plus à droite ou la plus basse d’un jeu de cellules associé à une requête, le système ne vous permet pas de coller la requête si les cellules à copier s’étendent au-delà de la bordure gauche ou supérieure de la feuille de calcul.
1. Select **[!UICONTROL Copy Request]**.
1. Ailleurs dans la feuille de calcul, cliquez avec le bouton droit sur une cellule vide (une cellule ne contenant aucune requête).

   Pour éviter toute perte ou altération des requêtes déjà créées, vous ne pouvez pas coller de cellules contenant des requêtes dans des cellules déjà mises en correspondance avec des requêtes. Si vous copiez ou coupez des cellules contenant des requêtes, l’option [!UICONTROL Coller les requêtes] n’est pas disponible dans le menu contextuel lorsque vous cliquez avec le bouton droit sur des cellules (ou sur le jeu de cellules) contenant les requêtes. Vous devez sélectionner une autre cellule comme destination de l’opération de collage, de sorte que les requêtes ne se chevauchent pas. Cette règle s’applique, que vous choisissiez de coller une seule ou plusieurs cellules avec des requêtes.
1. Click **[!UICONTROL Paste Request]**.

   Une copie de la requête d’origine est placée dans la ou les cellules, à un emplacement relatif à la requête d’origine.

   >[!NOTE]
   >
   >Seules les requêtes sont copiées, et non le contenu des cellules. Utilisez les commandes standard Copier et Coller d’Excel si vous possédez d’autres informations sans lien avec les requêtes, mais qui peuvent s’avérer utiles à la compréhension des données affichées dans les cellules (des en-têtes de colonne de tableau ou des identifiants de ligne, par exemple).

   Excel utilise différents Presse-papiers pour copier le contenu des cellules et les requêtes. Vous pouvez, par conséquent, copier le contenu des cellules sans requête, puis les requêtes en exécutant consécutivement les commandes Copier/Coller et Copier les requêtes/Coller les requêtes. Si, toutefois, vous appliquez une mise en forme aux requêtes dans la feuille de calcul avant de les copier/coller, le Créateur de rapports reproduit la mise en forme d’origine (bordures, polices, etc.) dans la région de collage.

   Si vous modifiez une requête copiée ou coupée dans le Presse-papiers avant de la coller, elle est retirée du Presse-papiers. Par conséquent, pour conserver la requête dans son état d’origine, ne la modifiez pas entre le moment où vous la copiez et celui où vous la collez.
