---
description: Si vous utilisez une variable courante, telle que q, pour renseigner des termes de recherche, vous pouvez utiliser des règles de traitement pour remplir la variable eVar Termes de recherche internes avec ces valeurs.
subtopic: Processing rules
title: Renseigner les termes de recherche interne à l’aide d’un paramètre de chaîne de requête
feature: Admin Tools
uuid: 05ae2b0a-8797-468c-8f59-643beac614c5
exl-id: bc7cc712-0f2a-4260-a82c-ad0e48149e73
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 100%

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
