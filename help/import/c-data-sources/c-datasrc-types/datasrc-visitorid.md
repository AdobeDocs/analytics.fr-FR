---
description: Les identifiants de visiteur peuvent être intégrés en sélectionnant la catégorie Générique (ID de transaction).
subtopic: Data sources
title: Identifiant visiteur
topic-fix: Developer and implementation
feature: Data Sources
exl-id: 940af1ba-0d12-4552-a21e-0ceb06427ab2
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 100%

---

# VisitorID

Les identifiants visiteur peuvent être intégrés en sélectionnant la catégorie [!UICONTROL Données du centre d’appels].

Consultez [Intégration des données hors ligne](/help/import/c-data-sources/datasrc-integrating-offline-data.md).

## Dimensions VisitorID

| Nom de la colonne | Description |
|--- |--- |
| [!UICONTROL VisitorID] | (Requis) Valeur unique qui représente un client dans les systèmes en ligne et hors ligne. |
| [!UICONTROL Date] | Utilisez le format de date suivant : `MM/DD/YYYY/hh/mm/ss` (par exemple, 07/14/2017/06/00/00). |
| [!UICONTROL Code de suivi] | Nom du code de suivi. |
| [!UICONTROL Catégorie] | Nom de la catégorie. Si vous définissez une catégorie, vous devez également sélectionner un produit. |
| [!UICONTROL Canal] | Nom du canal. |
| [!UICONTROL eVar ]*n* | Nom de la variable eVar *n*. Valeurs valides de *n* : nombre entier entre 1 et 75. |
| [!UICONTROL Produit] | Nom du produit. |
| [!UICONTROL État] | Nom de l’état. |
| [!UICONTROL Zip] | Code postal. |

## Mesures d’identifiant visiteur

| Nom de la colonne | Description |
| --- | --- |
| [!UICONTROL Taux de clics] | Nombre de vues du code de suivi. |
| [!UICONTROL Ajouts au panier] | Nombre d’ajouts au panier. |
| [!UICONTROL Ouvertures de panier] | Nombre d’ouvertures de panier. |
| [!UICONTROL Suppressions de panier] | Nombre de suppressions de panier. |
| [!UICONTROL Consultations du panier] | Nombre de consultations de panier. |
| [!UICONTROL Paiements] | Nombre de paiements. |
| [!UICONTROL Événement ]*n* | Nombre d’occurrences de l’événement *n*. Valeurs valides de n : nombre entier entre 1 et 100.  Si vous définissez un événement de [!UICONTROL Vue], vous devez également définir la dimension de données correspondante (eVar). Si, par exemple, vous incluez des vues eVar2, vous devez configurer la variable eVar2 avec une valeur. |
| Vues [!UICONTROL eVar ]*n* | Nombre de fois où la variable eVar *n* a été vue. Valeurs valides de *n* : nombre entier entre 1 et 75. |
| [!UICONTROL Prix] | Prix du produit. |
| [!UICONTROL Commandes] | Nombre de commandes passées. |
| [!UICONTROL Consultations produits] | Nombre de consultations de produit. |
| [!UICONTROL Quantité] | Nombre d’unités vendues. |
