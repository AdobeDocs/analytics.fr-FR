---
description: Découvrez comment copier une requête simple.
title: Copie de requêtes simples
uuid: ff20560a-01ee-47e7-8bd1-b73edb010456
feature: Report Builder
role: User, Admin
exl-id: ceed28d5-cb7f-4343-96fd-2ce09f5a3515
TQID: https://experienceleague.adobe.com/Zd6s6l-sW40WlEtk2Z8AFcNLkC-l4wxcmo67XajqAJs
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
source-wordcount: 527
ht-degree: 18%

---

# Copie de requêtes simples

{{legacy-arb}}

Copiez une requête simple plutôt qu’une requête référentielle. Une requête simple est une requête qui ne contient aucune référence à une autre requête ou au contenu d’une cellule.

Une [requête référentielle](/help/analyze/legacy-report-builder/manage-requests/c-copy-requests/t-copy-referential-requests.md) utilise les valeurs des cellules comme entrée de paramètres, tel un filtre de données ou un filtre relationnel. Ces filtres utilisent la correspondance ou la tendance et sont basés sur les résultats d’une requête préalable ou sur le contenu saisi par l’utilisateur dans une cellule, appelée cellule d’entrée.

Pour copier une requête simple

1. Créez une requête valide.
1. Cliquez avec le bouton droit sur l’une des cellules où la requête est mise en correspondance ou sélectionnez une région de cellules contenant des requêtes.

   Choisissez de manière cohérente une cellule à partir de laquelle effectuer une copie dans le groupe de cellules couvertes par la requête. Le choix préféré est la cellule supérieure et la cellule la plus à gauche de l’ensemble de cellules couvertes par la demande, et fonctionne de gauche à droite. En effet, la feuille de calcul Excel comporte des centaines de colonnes et des milliers de lignes disponibles pour une expansion vers la droite ou vers le bas. Si vous décidez de démarrer une copie de requête à partir de la cellule la plus à droite ou la cellule inférieure dans un ensemble de cellules associées à une requête, le système ne vous permet pas de coller la requête si les cellules à coller s’étendent au-delà de la bordure gauche ou supérieure de la feuille de calcul.
1. Sélectionnez **[!UICONTROL Copier la requête]**.
1. Ailleurs dans la feuille de calcul, cliquez avec le bouton droit sur une cellule vide (une cellule ne contenant aucune requête).

   Pour éviter de perdre ou d’altérer des requêtes que vous avez déjà créées, vous ne pouvez pas coller des cellules contenant des requêtes vers les cellules actuellement mappées avec les requêtes. Si vous copiez ou coupez des cellules contenant des requêtes, le menu contextuel ne rend pas disponible l&#39;option [!UICONTROL Coller les requêtes] lorsque vous cliquez avec le bouton droit sur les cellules (ou l&#39;ensemble de cellules) contenant des requêtes. Vous devez sélectionner une autre cellule comme destination de l’opération de collage afin que les requêtes ne se chevauchent pas. Cela s’applique que vous sélectionniez une seule cellule avec une demande de collage ou une région de cellules contenant des demandes.
1. Cliquez sur **[!UICONTROL Coller la requête]**.

   Une copie de la requête d’origine est placée dans la ou les cellules, à un emplacement relatif à la requête d’origine.

   >[!NOTE]
   >
   >Seules les requêtes sont copiées, et non le contenu des cellules. Si vous disposez d’autres informations non basées sur des requêtes, mais pertinentes pour comprendre les données affichées dans les cellules (telles que les en-têtes de colonne de tableau ou les identifiants de ligne), utilisez les commandes standard d’Excel Copier et Coller.

   Comme Excel utilise différents presse-papiers pour copier le contenu des cellules et copier les demandes, vous pouvez copier à la fois le contenu des cellules qui ne font pas l&#39;objet d&#39;une demande, puis les demandes en exécutant les opérations Copier/Coller et Copier/Coller les demandes en série. Cependant, si vous appliquez une mise en forme aux requêtes de la feuille de calcul, puis effectuez un copier-coller, Report Builder reproduit la mise en forme d’origine (bordures, polices, etc.) dans la zone de collage.

   La modification d’une requête que vous avez copiée ou coupée dans le presse-papiers avant de la coller supprime la requête du presse-papiers. Par conséquent, pour conserver la requête à son état d’origine, ne modifiez pas une requête entre le moment où vous la copiez et celui où vous la collez.
