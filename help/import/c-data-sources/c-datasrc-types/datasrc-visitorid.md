---
description: Les identifiants de visiteur peuvent être intégrés en sélectionnant la catégorie Générique (ID de transaction).
subtopic: Data sources
title: Identifiant visiteur
topic-fix: Developer and implementation
uuid: 4e9ce675-72c2-42a4-8f2e-25140df19539
exl-id: 940af1ba-0d12-4552-a21e-0ceb06427ab2
source-git-commit: a7a116ddc9eddc500a52111e9c002bdbee3e4a56
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 81%

---

# VisitorID

Les identifiants visiteur peuvent être intégrés en sélectionnant la variable [!UICONTROL Données du centre d’appels] catégorie.

Voir [Intégration de données hors ligne](/help/import/c-data-sources/datasrc-integrating-offline-data.md).

## Dimensions VisitorID

| Nom de la colonne | Description |
|--- |--- |
| [!UICONTROL VisitorID] | (Requis) Valeur unique qui représente un client dans les systèmes en ligne et hors ligne. |
| [!UICONTROL Date] | Utilisez le format de date suivant : `MM/DD/YYYY/hh/mm/ss` (par exemple, 07/14/2017/06/00/00) |
| [!UICONTROL Code de suivi] | Nom du code de suivi. |
| [!UICONTROL Catégorie] | Nom de la catégorie. Si vous définissez une catégorie, vous devez également sélectionner un produit. |
| [!UICONTROL Canal] | Nom du canal. |
| [!UICONTROL eVar ]*n* | Nom de la variable eVar *n*. Valeurs valides de *n* : nombre entier entre 1 et 75. |
| [!UICONTROL Product] | Nom du produit. |
| [!UICONTROL État] | Nom de l’état. |
| [!UICONTROL Zip] | Code postal. |

## Mesures d’identifiant visiteur

| Nom de la colonne | Description |
| --- | --- |
| [!UICONTROL Taux de clics] | Nombre de consultations du code de suivi. |
| [!UICONTROL Ajouts de panier] | Nombre d’ajouts de panier. |
| [!UICONTROL Ouvertures de panier] | Nombre d’ouvertures de panier. |
| [!UICONTROL Suppressions de panier] | Nombre de suppressions de panier. |
| [!UICONTROL Consultations du panier] | Nombre de consultations de panier. |
| [!UICONTROL Achats] | Nombre de passages en caisse. |
| *Événement n* | Nombre de fois pair *n* s’est produite. Valeurs valides de n : nombre entier entre 1 et 100.  Si vous spécifiez une [!UICONTROL Affichage] , vous devez également spécifier la dimension de données correspondante (eVar). Si, par exemple, vous incluez des consultations eVar2, vous devez configurer la variable eVar2. |
| [!UICONTROL Consultations eVar ]*n* | Nombre de fois où la variable eVar *n* a été consultée. Valeurs valides de *n* : nombre entier entre 1 et 75. |
| [!UICONTROL Prix] | Prix du produit. |
| [!UICONTROL Commandes] | Nombre de commandes passées. |
| [!UICONTROL Consultations produits] | Nombre de consultations de produit. |
| [!UICONTROL Quantité] | Nombre d’unités vendues. |
