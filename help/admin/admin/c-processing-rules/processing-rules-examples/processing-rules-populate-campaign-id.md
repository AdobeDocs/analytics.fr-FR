---
description: Vous pouvez renseigner une variable à l’aide d’un paramètre de chaîne de requête.
seo-description: Vous pouvez renseigner une variable à l’aide d’un paramètre de chaîne de requête.
seo-title: Renseigner un ID de campagne à partir d’un paramètre de chaîne de requête
solution: Analytics
subtopic: Règles de traitement
title: Renseigner un ID de campagne à partir d’un paramètre de chaîne de requête
topic: Outils d’administration
uuid: 2bc61f9f-d8d2-41b7-bd39-4a9df30ff013
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

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

