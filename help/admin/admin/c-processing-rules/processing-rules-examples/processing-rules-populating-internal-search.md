---
description: Si vous utilisez une variable courante, telle que q, pour renseigner des termes de recherche, vous pouvez utiliser des règles de traitement pour remplir la variable eVar Termes de recherche internes avec ces valeurs.
seo-description: Si vous utilisez une variable courante, telle que q, pour renseigner des termes de recherche, vous pouvez utiliser des règles de traitement pour remplir la variable eVar Termes de recherche internes avec ces valeurs.
seo-title: Renseigner les termes de recherche interne à l’aide d’un paramètre de chaîne de requête
solution: Analytics
subtopic: Règles de traitement
title: Renseigner les termes de recherche interne à l’aide d’un paramètre de chaîne de requête
topic: Outils d’administration
uuid: 05ae2b0a-8797-468c-8f59-643beac614c5
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Renseigner les termes de recherche interne à l’aide d’un paramètre de chaîne de requête

Si vous utilisez une variable courante, telle que q, pour renseigner des termes de recherche, vous pouvez utiliser des règles de traitement pour remplir la variable eVar Termes de recherche internes avec ces valeurs.

Les valeurs de chaîne de requête doivent être codées au format Unicode ou UTF-8 pour être lues par des règles de traitement.

| Jeu de règles | Valeur |
|---|---|
| Condition | Si le Paramètre de chaîne de requête q est défini |
| Action | Remplacer la valeur des termes de recherche interne par le paramètre de chaîne de requête q |

Par exemple :

![](assets/populate-internal-search-terms.png)

