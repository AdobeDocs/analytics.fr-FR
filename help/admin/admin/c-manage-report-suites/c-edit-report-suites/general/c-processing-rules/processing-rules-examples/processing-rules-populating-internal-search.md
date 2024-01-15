---
description: Si vous utilisez une variable courante, telle que q, pour renseigner des termes de recherche, vous pouvez utiliser des règles de traitement pour remplir la variable eVar Termes de recherche internes avec ces valeurs.
subtopic: Processing rules
title: Renseigner les termes de recherche interne à l’aide d’un paramètre de chaîne de requête
feature: Admin Tools
role: Admin
exl-id: bc7cc712-0f2a-4260-a82c-ad0e48149e73
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '116'
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
