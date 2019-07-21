---
description: Les identifiants de visiteur peuvent être intégrés en sélectionnant la catégorie Générique (ID de transaction).
seo-description: Les identifiants de visiteur peuvent être intégrés en sélectionnant la catégorie Générique (ID de transaction).
seo-title: Identifiant visiteur
solution: Analytics
subtopic: Sources de données
title: Visitor ID
topic: Développeur et mise en œuvre
uuid: 4 e 9 ce 675-72 c 2-42 a 4-8 f 2 e -25140 df 19539
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Identifiant visiteur

Les identifiants de visiteur peuvent être intégrés en sélectionnant la catégorie Générique (ID de transaction).

See [Integrate Offline Data](../../../import/c-data-sources/datasrc-integrating-offline-data.md#concept_B5C576220F1548B5A3A57112AA3960C6).

<p class="head"> <b>Dimensions d’identifiant visiteur</b> </p>

| Nom de la colonne | Description |
|--- |--- |
| Identifiant visiteur | (Requis) Valeur unique qui représente un client dans les systèmes en ligne et hors ligne. |
| Date | Utilisez le format de date suivant : MM/JJ/AAAA/HH/mm/SS (par exemple, 07/14/2017/06/00/00). |
| Code de suivi | Nom du code de suivi. |
| Catégorie | Nom de la catégorie.  Si vous définissez une catégorie, vous devez également sélectionner un produit. |
| Canal | Nom du canal. |
| Evarn | Nom evarn. Valeurs valides de n : nombre entier entre 1 et 75. |
| Produit | Nom du produit. |
| État | Nom de l’état. |
| Postal | Code postal. |

**Mesures d’identifiant visiteur**

| Nom de la colonne | Description |
|--- |--- |
| Taux de clics | Nombre de consultations du code de suivi. |
| Ajouts de panier | Nombre d’ajouts de panier. |
| Ouvertures de panier | Nombre d’ouvertures de panier. |
| Suppressions de panier | Nombre de suppressions de panier. |
| Consultations du panier | Nombre de consultations de panier. |
| Passage en caisse | Nombre de passages en caisse. |
| Événement n | Nombre d’occurrences de l’événement n. Valeurs valides de n : nombre entier entre 1 et 100.  Si vous définissez un événement de consultation, vous devez également définir la portée de données correspondante (eVar). Si, par exemple, vous incluez des consultations eVar2, vous devez configurer la variable eVar2. |
| Vues evarn | Nombre de fois où la variable eVar n a été consultée. Valeurs valides de n : nombre entier entre 1 et 75. |
| Prix | Prix du produit. |
| Commandes | Nombre de commandes passées. |
| Consultations produits | Nombre de consultations de produit. |
| Quantité | Nombre d’unités vendues. |