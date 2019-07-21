---
description: Le fichier d’importation et d’exportation comporte six colonnes pour chaque classification numérique 2.
seo-description: Le fichier d’importation et d’exportation comporte six colonnes pour chaque classification numérique 2.
seo-title: Importation de classifications numériques 2
solution: Analytics
subtopic: Gestionnaire
title: Importation de classifications numériques 2
topic: Outils d’administration
uuid: 82 a 3034 c-e 002-4991-900 f -22 dd 45 d 54910
translation-type: tm+mt
source-git-commit: 49e149fe57d5d66b8eda22b1bdf60e7c6200761c

---


# Importation de classifications numériques 2

>[!IMPORTANT]
>
>La possibilité d’importer des classifications numériques 2 et des classifications activées par date a été supprimée du code base. Cette modification prendra effet lors de la version de maintenance de juillet 2019. S’il y a des colonnes numériques ou des colonnes activées par date dans le fichier d’importation, ces cellules seront ignorées et les autres données de ce fichier seront importées normalement. Les classifications existantes peuvent toujours être exportées par un workflow de classification standard et continuent à être disponibles dans les rapports.

Le fichier d’importation et d’exportation comporte six colonnes pour chaque classification numérique 2.

Les définitions suivantes supposent que le nom de la classification numérique 2 est MyCost.

**~MyCost :** nom explicite de la ligne.

**~ Moncoût ^~id~:** ID de modification d'une ligne existante. Lorsque vous ajoutez une ligne, cette entrée doit être vide Un ID est automatiquement attribué lorsque vous effectuez une exportation depuis le gestionnaire de classifications.

**~MyCost^~value~: **The value for the row. Si la colonne de taux est fixe, il s’agit alors d’une valeur fixe répartie sur toute la période. Si la colonne de taux est un événement, il s’agit alors du multiplicateur de cet événement. Cette entrée ne doit pas contenir de virgules.

**~ Moncoût ^~period~:** Période à laquelle cette ligne correspond. Cette entrée doit contenir une date de début et une date de fin, séparées par un tiret. Le tiret doit être entouré d’espaces. Les définitions doivent respecter le format suivant :

AAAA/MM/JJ - AAAA/MM/JJ

**~ Moncoût ^~rate~:** Evénement à multiplier par la colonne [!UICONTROL Valeur] . Les valeurs valides sont :

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

**~ Moncoût ^~hinge~:** Evénement à utiliser pour répartir la valeur lors d'une ventilation. This value is often the same as [!UICONTROL ~MyCost^~rate~], unless you are using [!UICONTROL fixed]. The valid values for this column are identical to that of [!UICONTROL ~MyCost^~rate~], with the addition of [!UICONTROL none].
