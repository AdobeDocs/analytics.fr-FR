---
description: Vous pouvez renseigner une variable à l’aide d’un paramètre de chaîne de requête.
subtopic: Processing rules
title: Renseigner un ID de campagne à partir d’un paramètre de chaîne de requête
feature: Admin Tools
role: Admin
exl-id: 526d2727-b7f6-4b41-be86-e5f5bc5e6c2b
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 100%

---

# Renseigner un ID de campagne à partir d’un paramètre de chaîne de requête

Vous pouvez renseigner une variable à l’aide d’un paramètre de chaîne de requête.

Dans la plupart des cas, vous utilisez un module pour compléter les variables de la chaîne de requête. Si une faute de frappe ou un problème similaire vous empêche d’indiquer la valeur, vous pouvez renseigner la variable à l’aide de règles de traitement.

Avant d’écraser une valeur, vérifiez toujours si elle est vide ou si elle contient la valeur souhaitée.

| Jeu de règles | Valeur |
|---|---|
| Condition | La campagne n’est pas définie |
| Action | Remplacer la valeur de la campagne par le paramètre de chaîne de requête cpid |

Par exemple :

![](assets/set-campaign-conditionally.png)
