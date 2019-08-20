---
description: Les ID de transaction peuvent être intégrés en sélectionnant la catégorie Générique (ID de transaction).
seo-description: Les ID de transaction peuvent être intégrés en sélectionnant la catégorie Générique (ID de transaction).
seo-title: ID de transaction
solution: Analytics
subtopic: Sources de données
title: ID de transaction
topic: Développeur et mise en œuvre
uuid: f 3370 bb 7-3 f 28-460 b-a 20 d-c 9 e 58 d 7301 d 4
translation-type: tm+mt
source-git-commit: e9cb3575780db9eb5c9a766ef20d596e504a20d0

---


# ID de transaction

Les ID de transaction peuvent être intégrés en sélectionnant la catégorie Générique (ID de transaction).

Voir [Intégration de données hors ligne](../../../import/c-data-sources/datasrc-integrating-offline-data.md#concept_B5C576220F1548B5A3A57112AA3960C6).

Data uploaded with *`transactionID`* automatically associates with the same marketing channel that processed the original server call that contained the *`transactionID`*.

**Dimensions de l’ID de transaction**

| Nom de la colonne | Description |
|--- |--- |
| ID de transaction | (Requis) Valeur unique qui représente une transaction en ligne qui a généré une activité hors ligne. |
| Date | Utilisez le format de date suivant : MM/JJ/AAAA/HH/mm/SS (par exemple, 01/01/2015/06/00/00). |
| Code de suivi | Nom du code de suivi. |
| Catégorie | Nom de la catégorie.  Si vous définissez une catégorie, vous devez également sélectionner un produit. |
| Canal | Nom du canal. |
| eVarN | Nom evarn. Les valeurs valides pour N sont des nombres entiers 1 à 250. |
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
| Eventn | Nombre de fois où eventn a eu lieu. Valeurs valides pour N : nombre entier 1 - 1000. Si vous définissez un événement de consultation, vous devez également définir la portée de données correspondante (eVar). Si, par exemple, vous incluez des consultations eVar2, vous devez configurer la variable eVar2. |
| Vues evarn | Nombre de fois où evarn a été visionné. Les valeurs valides pour N sont des nombres entiers 1 à 250. |
| Prix | Prix du produit. |
| Commandes | Nombre de commandes passées. |
| Consultations produits | Nombre de consultations de produit. |
| Quantité | Nombre d’unités vendues. |
