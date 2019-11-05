---
description: Les identifiants de visiteur peuvent être intégrés en sélectionnant la catégorie Générique (ID de transaction).
seo-description: Les identifiants de visiteur peuvent être intégrés en sélectionnant la catégorie Générique (ID de transaction).
seo-title: Identifiant visiteur
solution: Analytics
subtopic: Sources de données
title: Identifiant visiteur
topic: Développeur et mise en œuvre
uuid: 4e9ce675-72c2-42a4-8f2e-25140df19539
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Identifiant visiteur

Les identifiants de visiteur peuvent être intégrés en sélectionnant la catégorie Générique (ID de transaction).

Voir [Intégration des données](/help/import/c-data-sources/datasrc-integrating-offline-data.md)hors connexion.

<p class="head"> <b>Dimensions d’identifiant visiteur</b> </p>

| Nom de la colonne | Description |
|--- |--- |
| Identifiant visiteur | (Requis) Valeur unique qui représente un client dans les systèmes en ligne et hors ligne. |
| Date | Utilisez le format de date suivant : MM/JJ/AAAA/HH/mm/SS (par exemple, 07/14/2017/06/00/00). |
| Code de suivi | Nom du code de suivi. |
| Catégorie | Nom de la catégorie.  Si vous définissez une catégorie, vous devez également sélectionner un produit. |
| Canal | Nom du canal. |
| eVarn | Nom eVarn. Valeurs valides de n : nombre entier entre 1 et 75. |
| Produit | Nom du produit. |
| État | Nom de l’état. |
| Zip | Code postal. |

**Mesures d’identifiant visiteur**

| Nom de la colonne | Description |
|--- |--- |
| Taux de clics | Nombre de consultations du code de suivi. |
| Ajouts de panier | Nombre d’ajouts de panier. |
| Ouvertures de panier | Nombre d’ouvertures de panier. |
| Suppressions de panier | Nombre de suppressions de panier. |
| Consultations du panier | Nombre de consultations de panier. |
| Achats | Nombre de passages en caisse. |
| Événement n | Nombre d’occurrences de l’événement n. Valeurs valides de n : nombre entier entre 1 et 100.  Si vous définissez un événement de consultation, vous devez également définir la portée de données correspondante (eVar). Si, par exemple, vous incluez des consultations eVar2, vous devez configurer la variable eVar2. |
| Vues eVarn | Nombre de fois où la variable eVar n a été consultée. Valeurs valides de n : nombre entier entre 1 et 75. |
| Prix | Prix du produit. |
| Commandes | Nombre de commandes passées. |
| Consultations produits | Nombre de consultations de produit. |
| Quantité | Nombre d’unités vendues. |
