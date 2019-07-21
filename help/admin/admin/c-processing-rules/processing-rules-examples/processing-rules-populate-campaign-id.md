---
description: Vous pouvez renseigner une variable à l’aide d’un paramètre de chaîne de requête.
seo-description: Vous pouvez renseigner une variable à l’aide d’un paramètre de chaîne de requête.
seo-title: Renseigner un identifiant de campagne à partir d'un paramètre de chaîne de requête
solution: Analytics
subtopic: Règles de traitement
title: Renseigner un identifiant de campagne à partir d'un paramètre de chaîne de requête
topic: Outils d’administration
uuid: 2 bc 61 f 9 f-d 8 d 2-41 b 7-bd 39-4 a 9 df 30 ff 013
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Renseigner un identifiant de campagne à partir d'un paramètre de chaîne de requête

Vous pouvez renseigner une variable à l’aide d’un paramètre de chaîne de requête.

Dans la plupart des cas, vous utilisez un module pour compléter les variables de la chaîne de requête. Si une faute de frappe ou un problème similaire vous empêche d’indiquer la valeur, vous pouvez renseigner la variable à l’aide de règles de traitement.

Avant d’écraser une valeur, vérifiez toujours si elle est vide ou si elle contient la valeur souhaitée.

| Jeu de règles | Valeur |
|---|---|
| Condition | La campagne n’est pas définie |
| Action | Remplacer la valeur de la campagne par le paramètre de chaîne de requête cpid |

Par exemple :

![](assets/set-campaign-conditionally.png)

