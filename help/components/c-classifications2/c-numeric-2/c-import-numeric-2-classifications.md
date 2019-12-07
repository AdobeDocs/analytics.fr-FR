---
description: Le fichier d’importation et d’exportation comporte six colonnes pour chaque classification numérique 2.
subtopic: Classifications
title: Importation de classifications numériques 2
topic: Admin tools
uuid: 82a3034c-e002-4991-900f-22dd45d54910
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Importation de classifications numériques 2

>[!IMPORTANT]
>
>La possibilité d’importer des classifications numériques 2 et des classifications activées par date a été supprimée du code base. Cette modification prendra effet lors de la version de maintenance de juillet 2019. S’il y a des colonnes numériques ou des colonnes activées par date dans le fichier d’importation, ces cellules seront ignorées et les autres données de ce fichier seront importées normalement. Les classifications existantes peuvent toujours être exportées par un workflow de classification standard et continuent à être disponibles dans les rapports.

Le fichier d’importation et d’exportation comporte six colonnes pour chaque classification numérique 2.

Les définitions suivantes supposent que le nom de la classification numérique 2 est MyCost.

**~MyCost :** nom explicite de la ligne.

**~MyCost^~id~ :** ID pour la modification d’une ligne existante. Lorsque vous ajoutez une ligne, cette entrée doit être vide Un ID est automatiquement attribué lorsque vous effectuez une exportation depuis le gestionnaire de classifications.

**~MyCost^~value~ :** valeur de la ligne. Si la colonne de taux est fixe, il s’agit alors d’une valeur fixe répartie sur toute la période. Si la colonne de taux est un événement, il s’agit alors du multiplicateur de cet événement. Cette entrée ne doit pas contenir de virgules.

**~MyCost^~period~ :** période à laquelle correspond cette ligne. Cette entrée doit contenir une date de début et une date de fin, séparées par un tiret. Le tiret doit être entouré d’espaces. Les définitions doivent respecter le format suivant :

AAAA/MM/JJ - AAAA/MM/JJ

**~MyCost^~rate~ :** événement par lequel multiplier la colonne [!UICONTROL Valeur]. Les valeurs valides sont :

* fixed - utilisée pour indiquer que cette valeur est une valeur fixe à répartir sur la période.
* revenue
* order
* unit
* scopen
* scviews
* instance
* click
* checkout
* scadd
* scremove
* event 1
* event2
* etc

**~MyCost^~hinge~ :** événement à utiliser pour répartir la valeur lors d’une ventilation. Cette valeur est souvent identique à [!UICONTROL ~MyCost^~rate~], sauf si vous utilisez [!UICONTROL fixed]. Les valeurs valides pour cette colonne sont identiques à celles de [!UICONTROL ~MyCost^~rate~], avec la valeur [!UICONTROL none] en plus.
