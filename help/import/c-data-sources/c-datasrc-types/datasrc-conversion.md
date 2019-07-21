---
description: Les portées de données de conversion suivantes, ainsi que les mesures pour les types de données traités comme conversion, sont prises en charge.
seo-description: Les portées de données de conversion suivantes, ainsi que les mesures pour les types de données traités comme conversion, sont prises en charge.
seo-title: Conversion
solution: Analytics
subtopic: Sources de données
title: Conversion
topic: Développeur et mise en œuvre
uuid: 5 e 7907 b 1-6 c 9 c -4073-876 b -410 f 3 a 29767 d
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

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
| Evarn | Nom evarn. Valeurs valides de n : nombre entier entre 1 et 75. |
| Produit | Nom du produit. |
| État | Nom de l’état. |
| Postal | Code postal. |

<p class="head"> <b>Mesures de conversion</b> </p>

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