---
description: Les portées de données de conversion suivantes, ainsi que les mesures pour les types de données traités comme conversion, sont prises en charge.
subtopic: Data sources
title: Conversion
topic: Developer and implementation
uuid: 5e7907b1-6c9c-4073-876b-410f3a29767d
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Conversion

Les portées de données de conversion suivantes, ainsi que les mesures pour les types de données traités comme conversion, sont prises en charge.

## Dimensions et mesures de conversion {#section_FA1731B232B246DABEDF5A5D84159084}

Si vous définissez un événement de consultation, vous devez également définir la portée de données correspondante (eVar). Si, par exemple, vous incluez des consultations eVar2, vous devez configurer la variable eVar2. Le nombre d’événements personnalisés et de consultations eVar pris en charge par une suite de rapports est contractuel et varie d’une entreprise à une autre.

<p class="head"> <b>Dimensions de conversion</b> </p>

| Nom de la colonne | Description |
|--- |--- |
| Code de suivi | Nom du code de suivi. |
| Date | Utilisez le format de date suivant : MM/JJ/AAAA/HH/mm/SS (par exemple, 01/01/2015/06/00/00). |
| Catégorie | Nom de la catégorie.  Si vous définissez une catégorie, vous devez également sélectionner un produit. |
| Canal | Nom du canal. |
| eVarn | Nom de la variable eVarn. Valeurs valides de n : nombre entier entre 1 et 75. |
| Produit | Nom du produit. |
| État | Nom de l’état. |
| Zip | Code postal. |

<p class="head"> <b>Mesures de conversion</b> </p>

| Nom de la colonne | Description |
|--- |--- |
| Taux de clics | Nombre de consultations du code de suivi. |
| Ajouts de panier | Nombre d’ajouts de panier. |
| Ouvertures de panier | Nombre d’ouvertures de panier. |
| Suppressions de panier | Nombre de suppressions de panier. |
| Consultations du panier | Nombre de consultations de panier. |
| Achats | Nombre de passages en caisse. |
| Événement n | Nombre d’occurrences de l’événement n. Valeurs valides de n : nombre entier entre 1 et 100.  Si vous définissez un événement de consultation, vous devez également définir la portée de données correspondante (eVar). Si, par exemple, vous incluez des consultations eVar2, vous devez configurer la variable eVar2. |
| Consultations d’eVarn | Nombre de fois où la variable eVar n a été consultée. Valeurs valides de n : nombre entier entre 1 et 75. |
| Prix | Prix du produit. |
| Commandes | Nombre de commandes passées. |
| Consultations produits | Nombre de consultations de produit. |
| Quantité | Nombre d’unités vendues. |
