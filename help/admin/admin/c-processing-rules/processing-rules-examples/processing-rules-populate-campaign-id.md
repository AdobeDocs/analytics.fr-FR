---
description: Vous pouvez renseigner une variable à l’aide d’un paramètre de chaîne de requête.
subtopic: Processing rules
title: Renseigner un ID de campagne à partir d’un paramètre de chaîne de requête
feature: Admin Tools
uuid: 2bc61f9f-d8d2-41b7-bd39-4a9df30ff013
exl-id: 526d2727-b7f6-4b41-be86-e5f5bc5e6c2b
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '114'
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
