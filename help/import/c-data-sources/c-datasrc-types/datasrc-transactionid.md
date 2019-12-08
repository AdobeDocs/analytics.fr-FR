---
description: Les ID de transaction peuvent être intégrés en sélectionnant la catégorie Générique (ID de transaction).
subtopic: Data sources
title: ID de transaction
topic: Developer and implementation
uuid: f3370bb7-3f28-460b-a20d-c9e58d7301d4
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# ID de transaction

Les ID de transaction peuvent être intégrés en sélectionnant la catégorie Générique (ID de transaction).

See [Integrating Offline Data](/help/import/c-data-sources/datasrc-integrating-offline-data.md).

Data uploaded with *`transactionID`* automatically associates with the same marketing channel that processed the original server call that contained the *`transactionID`*.

**Dimensions de l’ID de transaction**

| Nom de la colonne | Description |
|--- |--- |
| ID de transaction | (Requis) Valeur unique qui représente une transaction en ligne qui a généré une activité hors ligne. |
| Date | Utilisez le format de date suivant : MM/JJ/AAAA/HH/mm/SS (par exemple, 01/01/2015/06/00/00). |
| Code de suivi | Nom du code de suivi. |
| Catégorie | Nom de la catégorie.  Si vous définissez une catégorie, vous devez également sélectionner un produit. |
| Canal | Nom du canal. |
| eVarN | Nom eVarN. Les valeurs valides pour N sont les nombres entiers 1 à 250. |
| Produit | Nom du produit. |
| État | Nom de l’état. |
| Zip | Code postal. |

<p class="head"> <b>Mesures d’ID de transaction</b> </p>



| Nom de la colonne | Description |
|--- |--- |
| Taux de clics | Nombre de consultations du code de suivi. |
| Ajouts de panier | Nombre d’ajouts de panier. |
| Ouvertures de panier | Nombre d’ouvertures de panier. |
| Suppressions de panier | Nombre de suppressions de panier. |
| Consultations du panier | Nombre de consultations de panier. |
| Achats | Nombre de passages en caisse. |
| EventN | Nombre de fois où eventN s’est produit. Les valeurs valides pour N sont les nombres entiers 1 à 1 000.  Si vous définissez un événement de consultation, vous devez également définir la portée de données correspondante (eVar). Si, par exemple, vous incluez des consultations eVar2, vous devez configurer la variable eVar2. |
| Vues eVarN | Nombre de fois où eVarN a été consultée. Les valeurs valides pour N sont les nombres entiers 1 à 250. |
| Prix | Prix du produit. |
| Commandes | Nombre de commandes passées. |
| Consultations produits | Nombre de consultations de produit. |
| Quantité | Nombre d’unités vendues. |
