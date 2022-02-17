---
description: Les portées de données de conversion suivantes, ainsi que les mesures pour les types de données traités comme conversion, sont prises en charge.
subtopic: Data sources
title: Conversion
topic-fix: Developer and implementation
feature: Data Sources
exl-id: 00450ad4-7148-4cf1-bdba-5d1732dd0fd3
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 100%

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
| eVarn | Nom de la variable eVarn. Valeurs valides de n : nombre entier entre 1 et 250. |
| Product | Nom du produit. |
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
| Consultations d’eVarn | Nombre de fois où la variable eVar n a été consultée. Valeurs valides de n : nombre entier entre 1 et 250. |
| Prix | Prix du produit. |
| Commandes | Nombre de commandes passées. |
| Consultations de produit | Nombre de consultations de produit. |
| Quantité | Nombre d’unités vendues. |
