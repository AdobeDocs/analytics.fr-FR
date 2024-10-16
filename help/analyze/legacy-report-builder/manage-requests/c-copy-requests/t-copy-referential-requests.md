---
description: Découvrez comment copier des requêtes référentielles.
title: Copie de requêtes référentielles
uuid: b6f64630-868f-455b-8682-471ff9fc596e
feature: Report Builder
role: User, Admin
exl-id: 3cd77325-7461-4345-a672-64c03ea1ae5b
source-git-commit: 16046af6b7a78bdc4bfaf7e5ec7d05c55f2ebc01
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 80%

---

# Copie de requêtes référentielles

Une requête référentielle utilise les valeurs des cellules comme entrée de paramètres, tel un filtre de données ou un filtre relationnel.

Pour propager ou copier-coller des requêtes référentielles dans la feuille de calcul :

* Vous devez créer au moins une requête valide dans la feuille de calcul.

* Les données générées par la requête doivent contenir une cellule dont la valeur dépend d’une requête dans une autre cellule (à l’aide d’une ventilation ou d’un filtre correspondant) ou d’un filtre qui récupère la saisie des données entrées dans une cellule.

Vous pouvez également créer des requêtes qui renvoient à des filtres d’entrée issus de requêtes de différentes feuilles de calcul, mais dans un seul classeur. Par exemple, une requête dans la Feuille 2 peut utiliser une suite de rapports d’une cellule particulière de la Feuille 1 et une plage de dates d’une cellule dans une requête de la Feuille 2. Le nouveau résultat peut être placé dans l’une des deux feuilles ou dans une nouvelle feuille du même classeur. Lorsque vous collez une requête relative, si un filtre d’entrée réside dans une feuille de calcul autre que celle sur laquelle est situé le résultat de la requête copiée, le filtre est collé en tant que filtre absolu.

>[!NOTE]
>
>Vous ne pouvez pas générer une requête unique dans plusieurs feuilles de calcul. En outre, le système ne peut pas coller certaines des requêtes copiées dans de nouveaux classeurs, car les requêtes contiennent des filtres d’entrée provenant d’autres feuilles de calcul. Les filtres d’entrée incluent des suites de rapports issues des cellules, des plages de dates des cellules, des filtres des cellules et d’autres paramètres connexes.

**Pour copier les requêtes référentielles**

1. Sélectionnez les cellules contenant les requêtes à copier, y compris la cellule d’entrée ou la cellule référencée.
1. Cliquez avec le bouton droit dans les cellules en surbrillance, puis sélectionnez **[!UICONTROL Copier les requêtes]** dans le menu contextuel.

   Après avoir sélectionné la zone où résident les requêtes et cellules d’entrée, le système surligne les cellules contenant ces éléments.
1. Sélectionnez l’une des cellules ou une plage de cellules contiguës à remplir avec les requêtes collées.

   Assurez-vous que la cellule ou plage de cellules sélectionnée ne contient aucune autre donnée ou requête.
1. Cliquez avec le bouton droit sur la cellule unique ou sur la cellule la plus en haut à gauche de la plage de cellules, puis sélectionnez **[!UICONTROL Coller les requêtes]**.

   Si vous collez des requêtes qui incluent une cellule d’entrée, le menu [!UICONTROL Coller les requêtes] comprend les options suivantes :

   **Utiliser la cellule d’entrée absolue** : colle une copie des requêtes et de la mise en forme associée aux cellules sélectionnées dans la zone de collage en surbrillance. La cellule d’entrée (cellule référencée dans l’une des requêtes d’origine) n’est pas collée. Elle reste à la même position qu’auparavant.

   **Utiliser la cellule d’entrée relative** : colle une copie des requêtes et de la mise en forme associée aux cellules sélectionnées dans la zone de collage en surbrillance, y compris une copie de la cellule d’entrée. La relation spatiale des requêtes à la cellule d’entrée est identique à celle des requêtes d’origine. Toutefois, même si les cellules nouvellement copiées possèdent désormais une copie des requêtes, elles n’ont aucun contenu. En effet, lorsque la cellule d’entrée est recréée lors de l’opération de collage, aucune donnée n’est associée à la cellule d’entrée. Vous devez saisir une valeur dans la cellule d’entrée, puis actualiser les requêtes pour afficher les données des requêtes nouvellement collées.
